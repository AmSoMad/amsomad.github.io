---
title: "[gRPC-Web] gRPC-Web 브라우져에서 사용하기"
excerpt: "gRPC-web 구현"

categories:
  - gRPC
  
tags:
  - [Web, gRPC, HTTP2, protoc]

permalink: 

toc: true
toc_sticky: true
 
date: 2022-06-21
last_modified_at: 2022-06-22
---

---

# gRPC-Web javascript

 - Node.js 나 .NET의 Blazor를 쓰면 편하다. 허나 해보려한다.

## 🤷🏻‍♀️ Web에서 gRPC 통신방법

> 해당글은 proto 파일을 js파일로 컴파일하여 <br>
> javascript로 gRPC통신을 한다. <br>
> 단 gRPC-Service 는 구현되어 있는 상태여야 한다.<br>

### 준비물 2개

Doc를 먼저 본 후 진행하자. **[https://github.com/grpc/grpc-web#code-generator-plugin](https://github.com/grpc/grpc-web#code-generator-plugin)** <br>
해당링크에서 다운을 받자. <br>

> 1. protoc 컴파일러 다운로드
>> **[https://github.com/protocolbuffers/protobuf/releases](https://github.com/protocolbuffers/protobuf/releases)** 
>> 다운을 받고 환경 변수도 등록해주자. <br>
>> ex) C:\protoc\protoc-3.20.1-win64\bin <br>
> 2. protoc-gen-grpc-web 다운로드
>> **[https://github.com/grpc/grpc-web/releases](https://github.com/grpc/grpc-web/releases)**  <br>
>> 여기서 컴파일러를 다운받고 <br>
>> 다운을 받고 환경 변수도 등록해주자.  <br>
>> ** 귀찮다면 컴파일러 옆에 같이두자.  <br>
> 3. 버전확인 (확인)
>> ```js
>> protoc --version 을 쳐서 버전확인을 해본다.
>> ```
> 4. proto파일 위치에 이동하여 컴파일을 한다.
>> ```js
>> // 프로토파일 위치에서 CMD키자.
>> // require 형태
>> protoc 프로토파일명.proto --js_out=import_style=commonjs:. --grpc-web_out=import_style=commonjs,mode=grpcwebtext:.
>> ```
>> ```js
>> //혹시나 googole closure 형태로도 반출을한다.
>> protoc 프로토파일명.proto --js_out=import_style=closure:. --grpc-web_out=import_style=closure,mode=grpcwebtext:.
>> ```
>> ```js
>> //문서에는 테스트목적으로 TypeScript 와 d.ts 타입으로도 반환해주고있다. 
>> protoc 프로토파일명.proto --js_out=import_style=closure:. --grpc-web_out=import_style=commonjs+dts,mode=grpcwebtext:.
>> protoc 프로토파일명.proto --js_out=import_style=closure:. --grpc-web_out=import_style=typescript,mode=grpcwebtext:.
>> // 단 js_out은 고정이다. CommonJS 형태 아니면 closure형태
>> ```
>> ```js
>> // 또한 맨 마지막
>> mode=grpcwebtext:. // Content-type : application/grpc-web-text 형태
>> // base64로 인코딩되고 서버 스트리밍호출도 지원
>> mode=grpcweb:. // Content-type : application/grpc-web+proto 형태
>> // protobuf 형태인데 unary만 지원중
>> ```
> 5. 결과
>> 아무런 말없이 바로 나온다면 정상적으로 완료된것이다.  <br>
>> 해당폴더에 가면   <br>
>> 프로토파일명_grpc_web_pb.js 과  <br>
>> 프로토파일명_pb.js  <br>
>> 이렇게 2개의 js파일이 나온다  <br>
>> Closure로 컴파일했을경우   <br>
>> pb.js가 서비스명Request 및 서비스명Response 파일 2개로 나눠져서 나왔을것이다.  <br>


---

<h1>이제 Web페이지로 이동해보자.</h1>

### [오류]😬 --grpc-web_out: protoc-gen-grpc-web: Plugin failed with status code 1.

```js
--grpc-web_out: protoc-gen-grpc-web: Plugin failed with status code 1.
``` 

해당오류는 다른오류가 있을 수는 있으나.

```js
protoc-gen-grpc-web-1.3.1-windows-x86_64.exe
해당 파일명을
protoc-gen-grpc-web.exe 로 수정하자.
```

---

## 🤷🏻‍♀️ 순수 자바스크립트로 grpc통신 해보기(Only JS)

---

> Git 허브를 보면 CDN으로 링크 붙이다보면 되겠다~   <br>
> 싶어서 삽질한 친구들 많더라.  <br>
> 나도 해봤으나 ...........  <br>
> 일단 안된다.  <br>
> 그 이유들은 너무나도 많다.  <br>

> 해보려는 사람들에게 내가했던 삽질을 공유한다.  <br>

```js
// proto 컴파일
"protoc 프로토파일명.proto --js_out=import_style=closure:. --grpc-web_out=import_style=closure,mode=grpcwebtext:."


// google-protobuf 포함 라이브러리
"google-protobuf.min.js"
"arith.js"
"constants"
"decoder.js"
"encoder.js"
"map.js"
"message.js"
"reader.js"
"utils.js"
"writer.js"
//protobuf가 돌려면 필요하다.  https://github.com/protocolbuffers/protobuf-javascript

// 이 3개를 추가를 하고 html를 실행하면
"서비스명request.js"
"서비스명response.js"
"프로토파일명_grpc_web_pb.js"

// 에러가날것이다. 
 "프로토파일명_grpc_web_pb.js:90 Uncaught ReferenceError: grpc is not defined"

// 해당오류를 쫒아가면
"grpc.web.MethodDescriptor()" // 이함수가 없어서 발생하는것이다.

//grpc-web.js 파일이 있다. 
// https://www.jsdelivr.com/package/npm/grpc-web
// https://github.com/grpc/grpc-web/
// 파일을보면 index.d.ts 파일이있다. 해당 파일안에
// grpc.web.MethodDescriptor 이 있다. 

// 필자는 더이상 진행하기엔 스트레스를 너무받았다..
// 이것만 해결하면 될거같은데...
// module is not defined 과
// exports is not defined 에 진절머리가난다..
```

## 🤷🏻‍♀️ 결론

> Ndoe.Js 를 이용해서 TypeScript를 쓰면 브라우저에서 쉽게 가능하다.   <br>
> 단 프로토파일이 변경되면 수시로 컴파일해야한다. 그것도 싫다면..  <br>
> Blazor를 쓰자 빌드할때 다 컴파일되어서   <br>
> ```csharp
> @using Grpc.Net.Client
> @using Grpc.Net.Client.Web
> @using "csharp_namespace명";
> ```
> 이렇게 추가하고 Request Message 담고 요청하면 되더라...



**Note:** `만들고나니 내것이 아니었다.` 