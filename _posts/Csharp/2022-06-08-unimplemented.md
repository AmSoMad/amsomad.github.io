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

```


<br>



**Note:** `만들고나니 내것이 아니었다.` 