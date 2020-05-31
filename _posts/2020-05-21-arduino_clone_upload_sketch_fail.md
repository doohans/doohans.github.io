---
title: "아두이노 클론 스케치 업로드 실패 해결"
tags: [아두이노,스케치]
comments: true
published : true
---

개인적으로 arduino pro mini를 가장 많이 사용한다. 작은사이즈가 여러모로 활용도가 좋긴 때문이다.

그동안 여러 브랜드의 아두이노 클론을 사용해왔지만 핀배치가 조금씩 다른 것 말고는 큰 문제가 없었다.

아래의 녀석을 만나기 전까지는...

The simple이라고 마킹되어 있는 아두이노다.
![image](https://i.stack.imgur.com/vRb0Y.jpg)

![image](https://i.stack.imgur.com/ZFngy.jpg)

[출처] https://arduino.stackexchange.com/questions/8511/how-to-identify-arduino-mini-pro-5v-vs-3-3v


문제는 이 아두이노에 스케치를 업로드하면 업로드가 되다 안되다 한다. 거의 실패하고 실패 메시지는 아래와 같다. 

```
avrdude: stk500_recv(): programmer is not responding
avrdude: stk500_getsync() attempt 1 of 10: not in sync: resp=0x2b
avrdude: stk500_recv(): programmer is not responding
avrdude: stk500_getsync() attempt 2 of 10: not in sync: resp=0x2b
avrdude: stk500_recv(): programmer is not responding
avrdude: stk500_getsync() attempt 3 of 10: not in sync: resp=0x2b
avrdude: stk500_recv(): programmer is not responding
avrdude: stk500_getsync() attempt 4 of 10: not in sync: resp=0x2b
avrdude: stk500_recv(): programmer is not responding
avrdude: stk500_getsync() attempt 5 of 10: not in sync: resp=0x2b
avrdude: stk500_recv(): programmer is not responding
avrdude: stk500_getsync() attempt 6 of 10: not in sync: resp=0x2b
avrdude: stk500_recv(): programmer is not responding
avrdude: stk500_getsync() attempt 7 of 10: not in sync: resp=0x2b
avrdude: stk500_recv(): programmer is not responding
avrdude: stk500_getsync() attempt 8 of 10: not in sync: resp=0x2b
avrdude: stk500_recv(): programmer is not responding
avrdude: stk500_getsync() attempt 9 of 10: not in sync: resp=0x2b
avrdude: stk500_recv(): programmer is not responding
avrdude: stk500_getsync() attempt 10 of 10: not in sync: resp=0x2b
```

이 메시지로 구글링 하면 엄청난 양의 글이 나오지만 대부분 DTR 핀이 없는 USB2Serial을 사용하여 Auto Reset이 되지 않는 문제를 언급한다. 수동으로 Reset 하는 가이드를 한다. 나의 경우에도 수동으로 reset 버튼을 누르면 업로드가 성공한다. 

하지만! 나의 FTDI 모듈은 DTR 핀이 있고 다른 아두이노 프로 미니는 전부 정상적으로 Auto Reset 이 작동하여 정상적으로 스케지가 업로드 된다. 오직 "The Simple"이라고 마킹된 아두이노에서만 이 현상이 발생한다. 

해결은 아래와 같이 rst 핀에 10k옴 저항을 gnd로 연결하는 것이다. 몇일을 삽질하다 얻어걸린 해결책이다. 혹시나 동일한 문제로 스트레스 받고 있는 분은 이 방법으로 시도해 보시길 바란다. 물론 FTDI는 DTR 핀이 있고 아두이노와 연결되어 있어야 한다.

![image](https://user-images.githubusercontent.com/19382541/83353325-c25f5d00-a38c-11ea-9bee-b33465becbb1.png)
