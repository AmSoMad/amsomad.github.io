---
title: "우분투 20.04.4 로그인오류"
excerpt: "무한로그인"

categories:
  - 서버
  
tags:
  - [서버, ubuntu, 개떡같다, 무한로그인]

permalink: 

toc: true
toc_sticky: true
 
date: 2022-04-12
last_modified_at: 2022-04-21
---

## 🤷🏻‍♀️ 우분투를 로그인 하려는데...

기가차는 상황이 발생을 했다.<br>
로그인을하니 정말 얇밉다<br>

```js
"Oh no! Something went wrong"
```

이러면서 로그아웃하고 다시 시도하란다... <br>

내가뭘 잘못한것도없고 설치하란거 다했는데 이거원.. <br>

어김없이 삽질할거같아서 적는다.<br>

재설치만 4번째하는데 검색을해보니 다들 기본적으로 겪는상황이란다. <br>

[Ask ubuntu](https://askubuntu.com/)에보면 많은 글들이있는데
나는 [이 글](https://askubuntu.com/questions/1239025/after-upgrade-to-ubuntu-20-04-oh-no-something-went-wrong)을 찾았다.

```cs
Ctrl + Alt + F2, F3, F4 키를 눌르면 tty2,3,4 로 이동하면서 터미널모드가 나온다.

Login : 

```

하면서 아이디와 패스워드를 입력하는데 무한로그인이 발생했다...

login incorrect <br>

화딱지 재대로난다.


```js
sudo apt-get update && sudo apt-get dist-upgrade 

clear

sudo apt-get clean && sudo apt-get autoremove && sudo reboot

```

..이렇게 하라는데 아니 터미널에서도 로그인이안되는데??

## 🤷🏻‍♀️ 또 재설치...

첫 설치후 root 계정도 안만들어지기에 답답함이 앞서고
어김없이 재설치를 한다.


## 🤷🏻‍♀️ 로그인문제 해결

설치를 할때 Name과 P/W를 입력하는데 <br>
ID에 대문자를 섞어서 만들었을경우 <br>
로그인할때에는 소문자로 입력해야 된다. <br>
계속 대문자 입력을하니 로그인이 안되는 것이였다 .. <br>


## 🤷🏻‍♀️ 그외 문제 확인이력

서버에 설치를 할경우 환경마다 다르나. <br>
여러개의 HDD를 1개로 사용하는 경우가 다수 있는데 <br>
나같은 경우는 설치를 했는데 3개중 가운데 HDD에 노란불이 들어오면서 <br>
문제가 있었는데 이 HDD의 문제로 설치가 재대로 이루어지지 않았었다. <br>

**참고) [Ubuntu](https://releases.ubuntu.com/focal/)**

<br>



**Note:** `만들고나니 내것이 아니었다.` 