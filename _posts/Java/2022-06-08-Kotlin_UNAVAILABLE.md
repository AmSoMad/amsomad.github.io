---
title: "[Android-Kotlin] 통신오류 UNAVAILABLE 뜰때"
excerpt: "통신결과 UNAVAILABLE 뜰경우"

categories:
  - 자바
  
tags:
  - [자바, Kotlin, Android, gRPC]

permalink: 

toc: true
toc_sticky: true
 
date: 2022-06-08
last_modified_at: 2022-06-08
---

## 😬 Kotlin 통신시 UNAVAILABLE 에러발생할경우 🏭👩‍🏭👨‍🏭
---

```js
manifest.AndroidManifest.xml 에 추가하자.


    <uses-permission android:name="android.permission.INTERNET"/>  <-추가

    <application>... </application>

```


<br>



**Note:** `만들고나니 내것이 아니었다.` 