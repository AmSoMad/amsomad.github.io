---
title: "[C#-gRPC] Unimplemented Service Error 뜰경우"
excerpt: "Unimplemented"

categories:
  - C#
  
tags:
  - [C#,gRPC,HTTP2]

permalink: 

toc: true
toc_sticky: true
 
date: 2022-06-08
last_modified_at: 2022-06-08
---

## 😬 gRPC 통신시 UNIMPLEMENTED SERVICE ERROR 발생할경우 🏭👩‍🏭👨‍🏭
---

```js

1. endpoint에 서비스를 선언했는지 확인

startup.cs -> endpoints.MapGrpcService<GreeterService>();
Program.cs -> app.MapGrpcService<GreeterService>();


2. protoBuf 파일확인

greeter.proto ->
package greeter; 
클라이언트와 서비스부분에 패키지명이 일치하여야 한다.

계속...
```


<br>



**Note:** `만들고나니 내것이 아니었다.` 