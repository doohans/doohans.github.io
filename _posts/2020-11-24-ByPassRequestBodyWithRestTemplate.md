---
title: "bypass request body with RestTemplate"
tags: [spring, resttemplate]
comments: true
published : false
---

RestTemplate을 이용한 Upstream으로 Request Bypass와 Response Bypass

Reverse Proxy를 위한 RestTemplate을 사용한 대용량 파일처리 구현

# Request ByPass

## 서비스 코드 : Request의 InputStream을 그대로 HttpEntity body에 넣어 bypass 해준다.

```java
InputStreamResource stream = new InputStreamResource(request.getInputStream());
HttpEntity<InputStreamResource> requestEntity new HttpEntity<>(stream, headers);

long start = System.currentTimeMillis();
ResponseEntity<Resource> exchange = restTemplate.exchange(uri, mehtod, reuqestEntity, Resource.class);
logger.info("{} : {} ms", uri, System.currentTimeMillis()-start);
```

## RestTemplate 생성 코드

```java
HttpComponentsClientHttpRequestFactory factory = new HttpComponentsClientHttpRequestFactory(HttpClientBuilder.create().build());
//기타 추가적인 factory 설정. timeout 등등
factory.setBufferRequestBody(false);
resttemplate = new RestTemplate(factory);
```

SimpleClientHttpRequestFactory 나 HttpComponentsClientHttpRequestFactory 사용해서 ClientHttpRequestFactory 생성시
`setBufferRequestBody(false)` 설정을 해준다

```
setBufferRequestBody
public void setBufferRequestBody(boolean bufferRequestBody)
Indicates whether this request factory should buffer the request body internally.
Default is true. When sending large amounts of data via POST or PUT, it is recommended to change this property to false, so as not to run out of memory.
```

# Response ByPass

메모리 점유 없이 Response를 ByPass 하려면 다음과 같이 구현할 수 있다.
출처 : https://stackoverflow.com/a/45444645

```java
restTemplate.execute(uri, method,
  requestCallback -> {
    requestCallback.getHeaders().addAll(headers);
    //여기서는 reqeust의 필요항목이 header 뿐이지만 body항목이 더 필요하면 body도 셋팅 필요.
  },
  responseExtractor -> {
    response.setStatus(responseExtractor.getRawStatusCode());
    responseExtractor.getHeaders().forEach((key, values) -> {
      for (String value : values) {
        response.setHeader(key, value);
      }
    });
    IOUtils.copy(responseExtractor.getBody(), response.getOutputStream());
    return null;
  });
```


