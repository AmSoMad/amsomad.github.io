---
title: "[gRPC] Proto 에러 목록 및 해결법"
excerpt: "계속 추가중"

categories:
  - gRPC
  
tags:
  - [gRPC, HTTP2, .NET]

permalink: 

toc: true
toc_sticky: true
 
date: 2022-06-17
last_modified_at: 2022-06-17
---

## 😬 Proto 파일 에러
```java
Grpc.AspNetCore.Server.Internal.ServerCallHandlerFactory: Information: Service '패키지명' is unimplemented.
``` 

해당오류는 패키지명이 서버와 클라이언트간 불일치로인한 에러 

```js
ex)
//클라이언트 프로토파일
package CenterSvc; <-- 

//서버 프로토파일
package Center; <-- 

일치해야한다.
```

<br>




**Note:** `만들고나니 내것이 아니었다.` 