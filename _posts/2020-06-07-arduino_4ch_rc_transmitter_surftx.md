---
title: "diy arduino 4ch rc transmitter. surfTX"
tags: [아두이노,diy,rc,tx,surftx]
comments: true
published : true
---


# 발단

중국산 1/24 rc가 하나 있었다. mini-z clone이라 집에서 종종 재미있게 드리프트 하면서 가지고 놀았다. 

그런데 이 송신기가 기능은 엄청 많은데 버그가 있다. 모델 메모리 기능이 있으나 배터리를 분리하면 싹 지워진다. 

아마도 rom이 아닌 ram에만 데이터를 저장하는 듯 하다. 이게 은근히 짜증난다. 그렇다고 배터리를 계속 연결해두면 전원이 off 되어 있어도 배터리가 1주일이면 다 소모된다.

말도 안되는 현상이나, 중국산이니 그러려니 하고 쓰다가(처박아두다가) 다음의 프로젝트를 발견하고는 이녀석의 내장을 통째로 다 드러내기로 결심했다.

https://www.rcgroups.com/forums/showthread.php?2959179-Arduino-radio-for-HK-T6A-or-Flysky-FS-CT6B-%28ArduTX-rebirth%29


# 컨셉

위의 링크된 프로젝트는 비행기 등을 사용하는 스틱 조정기가 베이스다. 하지만 나는 자동차에 적용하고 싶어서 소스코드를 많이 수정하였다.

기존 6ch -> 4ch 로 수정하고(사실 6ch 유지도 가능하지만 사용하지 않을 듯 하여 4ch로 변경함.) 기존 프로젝트에는 없는 모델명 저장이나 저장 가능한 차량 메모리 수량을 대폭 늘렸다.

EPA나 EXPO 기능도 추가하고 전체적인 컨셉을 자동차에 적합하도록 로직을 수정하였다.

기존 송신기에서 사용한것이라곤 껍데기 쉘과 트리거, 휠, 버튼 정도이다. 기판은 통째로 다 드러냈고 대신 아두이노 기반으로 자작한 회로를 넣었다.

배터리도 주워놓은 1s 휴대폰 배터리를 사용하도록 했다. 

위 링크된 프로젝트와 동일하게 ppm 신호 output만 가능하기에 별도의 통신모듈이 필요했다. 나는 4 in 1 multiprotocol을 사용했고 기타 다른 ppm 지원 모듈을 사용해도 된다.

4 in 1 multiprotocol은 몇 가지 오픈된 수신기의 코드를 이용하려 일부러 선택하였다.


# 소스코드

깃헙 레파지토리에 전체 소스를 공유해두었다. 관심있으신 분은 아래에 링크에서 전체 소스 및 회로도를 다운받으실 수 있다.

https://github.com/doohans/arduino_surface_TX_4ch

<이슈나 버그리포트 환영합니다.>


# 동작화면샘플

![Screen01](https://github.com/doohans/arduino_surface_TX_4ch/blob/master/Images/screen01.jpg)
![Screen02](https://github.com/doohans/arduino_surface_TX_4ch/blob/master/Images/screen02.jpg)
![Screen03](https://github.com/doohans/arduino_surface_TX_4ch/blob/master/Images/screen03.jpg)
![Screen04](https://github.com/doohans/arduino_surface_TX_4ch/blob/master/Images/screen04.jpg)
![Screen05](https://github.com/doohans/arduino_surface_TX_4ch/blob/master/Images/screen05.jpg)
![Screen06](https://github.com/doohans/arduino_surface_TX_4ch/blob/master/Images/screen06.jpg)
![Screen07](https://github.com/doohans/arduino_surface_TX_4ch/blob/master/Images/screen07.jpg)
![Screen08](https://github.com/doohans/arduino_surface_TX_4ch/blob/master/Images/screen08.jpg)
![Screen09](https://github.com/doohans/arduino_surface_TX_4ch/blob/master/Images/screen09.jpg)
![Screen10](https://github.com/doohans/arduino_surface_TX_4ch/blob/master/Images/screen10.jpg)

![20200517_204824](https://user-images.githubusercontent.com/19382541/83968577-2d68e080-a905-11ea-9083-0f48a997c4a3.jpg)


# 내부사진

![20200419_144131_HDR](https://user-images.githubusercontent.com/19382541/83968525-d95dfc00-a904-11ea-9c2e-6f05f56b4290.jpg)
![20200419_211326_HDR](https://user-images.githubusercontent.com/19382541/83968527-d9f69280-a904-11ea-8a05-08d593a25c4e.jpg)


# 경과

현재는 직접 실 사용하면서 버그가 있는지 확인하고 있다. 멀티프로토콜 모듈과의 조합이 좋다. 송신거리도 100m 이상 문제없이 동작한다.

개인적으로 입맛에 맞게 송신기 기능을 변경할 수 있는게 마음에 들어서 이 송신기를 주력으로 사용하고 있다.

오픈된 수신기 코드를 이용하여 수신기도 자작하여 만들어 사용한다.

