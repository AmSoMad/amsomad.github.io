---
title: "[Blazor] Blazor를 이용하여 브라우저 Console.log 찍는방법"
excerpt: "jsruntime 추가해야한다."

categories:
  - C#
  
tags:
  - [C#, gRPC, HTTP2, Blazor]

permalink: 

toc: true
toc_sticky: true
 
date: 2022-06-09
last_modified_at: 2022-06-09
---

## 😬 Blazor를 이용하여 console.log 찍기 🏭👩‍🏭👨‍🏭
---


상단에 런타임 인터페이스를 추가해주고
```java
@inject IJSRuntime JSRuntime 
```

출력할 함수 안에

```js
await JSRuntime.InvokeVoidAsync("console.log", "콘솔로그 결과 : ", Result.toString());
```

검색해서 보이는

```csharp
Console.WriteLine("로그"); 
```

이건 서비스가 돌고있는 콘솔창에 찍힌다.
<br>




**Note:** `만들고나니 내것이 아니었다.` 