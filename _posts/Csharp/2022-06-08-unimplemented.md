---
title: "[C#-gRPC] Unimplemented Service Error λ°κ²½μ°"
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

## π¬ gRPC ν΅μ μ UNIMPLEMENTED SERVICE ERROR λ°μν κ²½μ° π­π©βπ­π¨βπ­
---

```js

1. endpointμ μλΉμ€λ₯Ό μ μΈνλμ§ νμΈ

startup.cs -> endpoints.MapGrpcService<GreeterService>();
Program.cs -> app.MapGrpcService<GreeterService>();


2. protoBuf νμΌνμΈ

greeter.proto ->
package greeter; 
ν΄λΌμ΄μΈνΈμ μλΉμ€λΆλΆμ ν¨ν€μ§λͺμ΄ μΌμΉνμ¬μΌ νλ€.

κ³μ...
```


<br>



**Note:** `λ§λ€κ³ λλ λ΄κ²μ΄ μλμλ€.` 