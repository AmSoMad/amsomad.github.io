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
 
date: 2022-06-20
last_modified_at: 2022-06-20
---

---

# gRPC-Web javascript

## 🤷🏻‍♀️ Web에서 gRPC 통신방법

> 해당글은 proto 파일을 js파일로 컴파일하여 <br>
> javascript로 gRPC통신을 한다. <br>
> 단 gRPC-Service 는 구현되어 있는 상태여야 한다.<br>

### 준비물 2개

Doc를 먼저 본 후 진행하자. **[https://github.com/grpc/grpc-web#code-generator-plugin](https://github.com/grpc/grpc-web#code-generator-plugin)** <br>
해당링크에서 다운을 받자. <br>

> 1. protoc 컴파일러 다운로드
>> **[https://github.com/protocolbuffers/protobuf/releases](https://github.com/protocolbuffers/protobuf/releases)** 
>> 다운을 받고 환경 변수도 등록해주자.
>> ex) C:\protoc\protoc-3.20.1-win64\bin
> 2. protoc-gen-grpc-web 다운로드
>> **[https://github.com/grpc/grpc-web/releases](https://github.com/grpc/grpc-web/releases)** 여기서 컴파일러를 다운받고
>> 다운을 받고 환경 변수도 등록해주자.
>> ** 귀찮다면 컴파일러 옆에 같이두자.
> 3. 버전확인 (확인)
>> ```js
>> protoc --version 을 쳐서 버전확인을 해본다.
>> ```
> 4. proto파일 위치에 이동하여 컴파일을 한다.
>> ```js
>> //프로토파일 위치에서 CMD키자.
>> protoc 프로토파일명.proto --js_out=import_style=commonjs:. --grpc-web_out=import_style=commonjs,mode=grpcwebtext:.
>> ```
> 5. 결과
>> 아무런 말없이 바로 나온다면 정상적으로 완료된것이다.
>> 해당폴더에 가면 
>> 프로토파일명_grpc_web_pb.js 과
>> 프로토파일명_pb.js
>> 이렇게 2개의 js파일이 나온다


---

이제 Web페이지로 이동해보자.

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

### 🤷🏻‍♀️ Html 추가



**Note:** `만들고나니 내것이 아니었다.` 