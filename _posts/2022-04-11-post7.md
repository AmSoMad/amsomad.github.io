---
title: "우분투 USB 부팅디스크 설치 20.04.4"
excerpt: "슬슬 열받을법 할때 보이는 글"

categories:
  - 서버
  
tags:
  - [서버,Rufus, ubuntu, HP, Hewlett Packard Enterprise]

permalink: 

toc: true
toc_sticky: true
 
date: 2022-04-11
last_modified_at: 2022-04-12
---

## 🤷🏻‍♀️ 우분투를 서버에 설치하라.

군대에서랑 교육 이때 이후로는 해본적이 없으나. <br>
할때 분명 여러 문제가 있었는데. 어김없이 삽질할거같아서 적는다.<br>

## 🤷🏻‍♀️ 우분투 다운로드

버전은 20.04.4로 선정했다.<br>
[Ubuntu](https://releases.ubuntu.com/focal/)<br>
![K-008](https://user-images.githubusercontent.com/57971757/162679430-f7046c06-de33-4bb8-bca7-cfc91b1e0515.jpg)


## 🤷🏻‍♀️ Rufus로 부팅디스크 생성

[Rufus](https://rufus.ie/ko/)가 생소한 사람도있을터<br>
간편하게 부팅 USB드라이브 만드는 프로그램이다.<br>

설정만 5번하고 usb에 포멧만 5번하고 재설치했다.. 그냥<br>
이렇게 설정하자.<br>
![K-007](https://user-images.githubusercontent.com/57971757/162679437-68f61ed1-26c4-448b-ab99-df877dff130e.jpg)


## 🤷🏻‍♀️ 부팅설정

F12 혹은 F11에 Boot menu 란에서<br>
부팅순서를 변경한다.<br>

그후 과감히 재부팅한다.<br>
다시 부팅메뉴로 가서 usb선택시 <br>
Ubuntu와 Ubuntu (Safe Graphics) 등등<br>
있다. 글쓴이는 그냥 Ubuntu눌렀다.<br>

## 🤷🏻‍♀️ 아직 안끝났더라...

booting embedded lom 1 port 1 ~&ㅛ@%$%@#^&# <br>
뜨면서 무한 리부팅을 하시시작..<br>


## 🤷🏻‍♀️ 부팅오류발생

```cs
>> Booting Embedded LOM 1 Port 1 : HPE Ethernet 1GB 4-port 331i Adaper - NTC 1%^#$%@#$%
```
이러더니???

```cs
No bootable devices were detected.
Please attach a UEFI bootable device.
System will automatically retry the UEFI boot Order in 3 seconds.
```
이렇게 오류가뜨면서... <br>
또다시 오랫동안 부팅을 또 기달렷다..<br>

기기는 HP Proliant Gen9 시리즈이다. <br>

```js
System Configuration -> BIOS/Platform Configuration (RBSU)
System Options -> SATA Controller Options -> Embedded SATA Configuration
Enable Dynamic Smart Array RAID Support -> Enable SATA AHCI Support 로 변경
다시 뒤돌아가서

NetWork Options -> Network Boot Options
Embedded LOM 1 Port 1 -> NetWork boot 
Embedded LOM 1 Port 2 -> NetWork boot 
Embedded LOM 1 Port 3 -> NetWork boot 
Embedded LOM 1 Port 4 -> NetWork boot 
으로 일괄변경함..
단 네트워크 부팅을 할일없다 하면 전부 끄자

Embedded LOM 1 Port 1 -> Disabled 
Embedded LOM 1 Port 2 -> Disabled 
Embedded LOM 1 Port 3 -> Disabled 
Embedded LOM 1 Port 4 -> Disabled 

Enable SATA AHCI Support 이 설정이 중요해보인다..
```
[참고영상](https://www.youtube.com/watch?v=6FybL-klOx8)

## 🤷🏻‍♀️ 마무리

처음해본사람은 솔찍히 몇번 해봐야안다..<br>
safe graphics가 뭔지 궁금하다면..[링크](https://askubuntu.com/questions/1138137/what-is-safe-graphics-mode)<br>

그리고 윈도우서버도 Rufus를 이용하면 동일한 방법으로 가능하다. <br>

단 필히 Rufus에서 파일시스템을 윈도우에서는 NTFS로 바꾸자 <br>
![K-009](https://user-images.githubusercontent.com/57971757/162694816-ba6e572f-b159-4c2a-b743-b2bfe332172d.jpg)<br>

3번째 만든다... 잘보고만들자..<br>


## 🤷🏻‍♀️ 아직 한발더 남았다...

[hp proliant DL380 G6](https://support.hpe.com/hpesc/public/docDisplay?docId=emr_na-c01714639) 해당모델도 설치하라하신다..
오지게느리네 이거.... <br>

설치가 재대로안되서 또설치하고 또설치한다...<br>

또한 혹시나 다른OS가 깔려있는데 설치해야할 경우 걱정말자.<br>
ubuntu설치할때 디스크 포맷후 설치하기 조건이 있다. <br>




**참고) [Rufus](https://rufus.ie/ko/), [Ubuntu](https://releases.ubuntu.com/focal/)**

<br>



**Note:** `만들고나니 내것이 아니었다.` 