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
endpoint에 서비스를 선언했는지 확인

endpoints.MapGrpcService<GreeterService>();


protoBuf 파일확인

greeter.proto ->
package greeter; 
클라이언트와 서비스부분에 페키지명이 일치하여야 한다.

계속...
```


<br>



**Note:** `만들고나니 내것이 아니었다.` 