---
title: "bypass request body with RestTemplate"
tags: [spring, resttemplate]
comments: true
published : false
---

```
InputStreamResource stream = new InputStreamResource(request.getInputStream());
HttpEntity<InputStreamResource> requestEntity new HttpEntity<>(stream, headers);

long start = System.currentTimeMillis();
ResponseEntity<Resource> exchange = restTemplate.exchange(uri, mehtod, reuqestEntity, Resource.class);
logger.info("{} : {} ms", uri, System.currentTimeMillis()-start);
```

```
HttpComponentsClientHttpRequestFactory factory = new HttpComponentsClientHttpRequestFactory(HttpClientBuilder.create().build());
factory.set~~~
factory.setBufferRequestBody(false);
resttemplate = new RestTemplate(factory);
```
