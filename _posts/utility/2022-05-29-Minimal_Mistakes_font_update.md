---
title: "[Minimal Mistakes] Font 글꼴 수정하는 방법"
excerpt: "너무 이상한건 하지말자. "

categories:
  - 유틸리티
  
tags:
  - [Web, 고장]

permalink: 

toc: true
toc_sticky: true
 
date: 2022-05-29
last_modified_at: 2022-05-29
---

# 🐐 Minimal Mistakes 글꼴 원하는걸로 바꾸기

---

## 글꼴부터 찾자

> 글꼴은 **[https://noonnu.cc/](https://noonnu.cc/)** 에서 찾아보자. <br>
> 원하는 형태의 글꼴을 찾아서 아래와 같이 설정하자.


## 글꼴 추가하기

```js
// 추가된 폰트를 _sass/assets/main.scss 에 추가해준다.

@font-face {
  font-family: 'D2Coding';
  src: url('https://cdn.jsdelivr.net/gh/projectnoonnu/noonfonts_three@1.0/D2Coding.woff') format('woff');
  font-weight: normal;
  font-style: normal;
}
```

---

## 글꼴 적용하기


```js
// _sass/minimal-mistakes/_variables.scss 에서 변수에 담아주고

//메인 폰트 설정
$customFontStyle : 'D2Coding';

//처럼 3개의 폰트의 제일 앞에 추가해준다.
/* system typefaces */
$serif: $customFontStyle,Georgia, Times, serif !default;
$sans-serif: $customFontStyle,-apple-system, BlinkMacSystemFont, "Roboto", "Segoe UI",
  "Helvetica Neue", "Lucida Grande", Arial, sans-serif !default;
$monospace: $customFontStyle, Monaco, Consolas, "Lucida Console", monospace !default;

```

---


**Note:** `만들고나니 내것이 아니었다.` 