---
title: "diy arduino 4ch rc transmitter. surfTX"
tags: [아두이노,diy,rc,tx,surftx]
comments: true
published : true
---


재활용장에서 보지 말아야 것을 보았습니다.

```"전자렌지"```

요즘은 다들 링코어로 스폿용접기를 만드시는게 추세인것을 알지만,

삽질인것을 알면서도 저것으로 작은 크기로 만들어 보고 싶더군요.

처음 만들어보는거라 시행착오도 많았네요.

  

![](https://cafefiles.pstatic.net/MjAyMDA2MTNfMjMw/MDAxNTkyMDI2MTY5OTE4.uvebnNM1c03bFwZu_oB_0texy2J4P1K7Ru9hUZ_A_Xwg.lSKxOvsu58AWEpt_Rhuv81N5kH_yTdzgtaFmFauY65Yg.JPEG/20200526_233826_HDR.jpg)

카페 정보를 이용하여 25sq 용접선 피복 벗기고 수축튜브 쒸우고 감았습니다.

한바퀴당 약 0.9v 씩 올라갔습니다. 7바퀴 6.2v로 마무리 했습니다.

6바퀴째에 이미 진이 빠졌는데 전압이 5.4v라 조금 낮은듯 하여 욕심이 좀 더 생겨 한바퀴 더 감았습니다.

wd40 뿌리면서 고무망치로 치고 밀며 당기며 땀흘리고 있으니 와이프가 뭐하냐는 눈빛으로 바라보네요..

  

![](https://cafefiles.pstatic.net/MjAyMDA2MTNfNDEg/MDAxNTkyMDI2MTcwODkx.aN4tN59tpb9QRdeNh3jIdIX1tnjqJYoSkhup7lOuVHIg.Y2TYS7RwrEW5ijgTXdnSW1JVZqnOiY2D07FYQGpfj3Mg.JPEG/20200526_234425.jpg)

  

![](https://cafefiles.pstatic.net/MjAyMDA2MTNfOTcg/MDAxNTkyMDI2MTcxNjA5.dv03fH7ruClI8biYl_9vPCykGYSqkMSFK0g2s42sVYkg.JIgxPwmvYsiRjH7HYZLaL2voQCHyLKj6VTgTd4m61wQg.JPEG/20200604_232745.jpg)

가조립 해봅니다.

전자렌지 트랜스가 약하다고 하니 모든 연결은 직결했습니다.

스위치도 생략하고 배선차단기로 스위치 역할을 합니다.

용접봉은 청계천에서 직경 6mm짜리 1m 사다가 잘랐는데.

이렇게 안잘릴줄 몰랐습니다.ㅠㅠ(80cm 남았네요 처분해야겠어요)

쇠톱으로 열심히 자르고 80방 사포로 손으로 그리고 드릴에 끼워 연필모양으로 연마했네요.

25sq 슬리브에 용접선 반 넣고 토치로 굽듯이 가열하여 납먹였습니다.

나머지 슬리브 반 길이만큼 용접봉 넣어 또 토치로 납먹였습니다. 할줄 몰라 용접봉이 다 탓네요 ㅎㅎㅎ

  

회로는 "용인후니파파" 님이 공유하신 스케치 및 회로([https://mindeater.tistory.com/2332](https://mindeater.tistory.com/2332))를

조금 변경하여 만능기판에 구성했습니다.

오토스폿이 잘 안되었는데 용인후니파파님께 문의하여 잘 해결하였습니다.(용인후니파파님 감사드려요!)

전자렌지 트랜스는 1차측 전압이 포토커플러를 동작시킬 만큼의 전압이 거의 안나옵니다.

스버너 캐패시터를 좀더 늘려서 포토커플러가 간당간당 동작할 정도로 올리고(0.3uf),

포토커플러 앞단 저항도 최대한 낮추어(33k옴) 일정한 신호를 획득하였습니다.

기존 링코어하고 용접봉 오픈 신호 패턴이 상이(노이즈가 많습니다.)하여 아두이노 스케치도 일부 수정하였습니다.

LCD는 집에 있는게 1602 뿐이라 1602 대응으로 수정하였고,

부저를 패시브 부저로 잘못구매하는 바람에 부저 로직도 살짝 수정하였습니다.

(야매로 펄스를 만들었네요.)

뭔가 패시브 부저 사용이 억울하여 오토 감지시 삐삑 하는 멜로디를 살짝 넣었습니다.

부저음이 듣기 싫을때도 있으니 토글스위치 하나 달아서 끌수 있게 했습니다.

{% include youtubeplayer.html id="fnji2yeavow" %}

  
![](https://cafefiles.pstatic.net/MjAyMDA2MTNfMTc0/MDAxNTkyMDI2MTcyMzI4.G7Hc_axfFNBofdmc2OmyYD-1gvshBann7KMQDUfsioog.QwR-50xBCTZWw7uDkUHsvC0fdDjURxHRSIJO9SeXBqwg.JPEG/20200607_203849.jpg)

케이스가 가장 고민되는데

15x11 정도 되는 케이스가 작고 적당할것 같은데 잘 못찾겠더라구요.

다이소 가서 제일 비슷한 녀석을 가져다가 넣어봤는데 너무 약해요 ㅎㅎㅎ

그래도 크기는 아주 작은게 제 작은 책상에 부담없이 올려놓을 수 있겠네요.

차단기도 안쪽에 넣으려다가 뚜껑 여는게 불편할것 같아서 그냥 밖에 달았습니다.

    
수동 모드를 위해 주워다 놓은 3.5파이 단자도 달아줍니다.

미니 재봉틀 발판스위치가 있는데 이녀석이 3.5파이 스테레오 단자라 재활용합니다.

![](https://cafefiles.pstatic.net/MjAyMDA2MTRfMjYz/MDAxNTkyMTI4NTUyNzI1.lUnp9gE6WMV-W940UqHj35J4W1rbGtIDHLiGaLpRaFsg.ILJrO_zsJyX772TroZzrFdj1jiaX9eJH576E-GLFiTQg.JPEG/20200614_185022_HDR.jpg)  

  

  

  

![](https://cafefiles.pstatic.net/MjAyMDA2MTNfMTMx/MDAxNTkyMDI2MTcyODg2.D8UXx75VvOYQDsnNk9sEdfKmpcGe6NqtTgh87meSR0Ig.TDJIgYdLQ54YZTbi8SY1ro0OGzGEq-Jxktf1jFUR4V4g.JPEG/20200607_204251.jpg)

  

  

  

![](https://cafefiles.pstatic.net/MjAyMDA2MTNfMTc5/MDAxNTkyMDI2MTczNDAw.Gkj_9GHhgEEnNcOVa57loNrk95h0GwTsUNZAye8X5Ikg.RGYapxzsLXZ6QfTRr5tyTs31ReX98P4KWNVOW3D4doEg.JPEG/20200607_215622_HDR.jpg)

  

용접봉 연마하는게 쉬울줄 알았는데 힘들었습니다.

6mm 크롬동봉으로 갈고 자르고 하는 노력이 너무 많이 들어가더라구요.

끝에만 어떻게는 동그랗게 연마하고 마무리...

그냥 까페 분양하시는 잘 연마된 얇은 교체용 동봉을 구매할걸 하는 후회가..ㅠㅠ

  

  

![](https://cafefiles.pstatic.net/MjAyMDA2MTNfMjY0/MDAxNTkyMDI2MjM4MTE4.Ccj7Py6RmrafOGCTBvgc8SzwvG_3nEJgMlxrOlKo9fsg.a57Xmsq0ZkX751-0vWitN9JzkZDPQX6dAdkefGuPQI8g.JPEG/20200612_222609.jpg)

  

적당한 철판이 없어서 다 쓴 알카라인 건전지(`리튬아닙니다. 리튬배터리에 하시면 안됩니다.`) 옆구리에 연습해보았습니다.

처음 스폿을 쳐본거라 어떻게 하는지도 모르고 빵꾸도 내고 식겁했네요.

하다 보니 아래 두가지 요령으로 하면 잘 되더군요.

  

**1. 용접봉은 너무 있는 힘껏 꾹 누르지 않는다. 지긋이 눌러준다

2. 용접봉 간격이 너무 좁지 않게 한다. 너무 가까우면 열화가 쉽게 된다.**

  

순니켈이 크롬동봉 용접봉에 잘 들러붙더니만 도금니켈은 안붙더군요. 대신 스파크 파팍!!

0.1t 순니켈은 6ms,

0.15t 도금니켈은 10ms, 0.2t 도금니켈은 17ms에서 잘 붙습니다.

  

이상 혹시나 시작하시는 분들에게 도움이 될까 허접하지만 글을 남겨보았습니다.~