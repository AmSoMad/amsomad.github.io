---
title: "[gRPC-Web] Blazor를 이용하여 gRPC 서비스 클라이언트 호출 방법"
excerpt: "C# Blazor를 활용하여 Web에서 gRPC통신하기"

categories:
  - C#
  
tags:
  - [C#, gRPC, HTTP2, Blazor]

permalink: 

toc: true
toc_sticky: true
 
date: 2022-06-27
last_modified_at: 2022-06-27
---

## 😬 [Blazor] gRPC-WEB 활용하기 🏭👩‍🏭👨‍🏭
---

> 순서
> 1. Blazor 앱 생성
> 2. NuGet 패키지 다운로드
> 3. Protos 폴더생성 및 Protocol Buffer 추가
> 4. 전체 빌드를 하여 proto파일 컴파일
> 5. blazor 페이지에 코드 구현
> 6. 통신결과
<br>
---

## 1. Blazor 앱 생성

---

![K-001](https://user-images.githubusercontent.com/57971757/176347481-5d8fb27a-d4dc-4e44-8f30-c7d5e65e34a5.jpg)

<br>

.Net5
> Startup.cs 추가
> 1. ***ConfigureServices*** 에서  ***service.addCors();*** 추가
> 2. ***Configure*** 에서 ***app.UseGrpcWeb();*** , ***app.UseCors();*** 를 추가한다.
>> ***app.UseRouting();*** 과 ***app.UseEndpoints()*** 사이에 추가해야한다.
> 3. ***EndPoints*** 에 endpoints.MapGrpcService<GreeterService>().EnableGrpcWeb();
>> 서비스부분에 ***EnableGrpcWeb()*** 추가

.Net6
> Program.cs 추가
> app.UseRouting(); 다음에
> app.UseGrpcWeb(); 를 추가한다.

![K-007](https://user-images.githubusercontent.com/57971757/176347618-2193efeb-3ddb-451e-a551-36c175c201e5.jpg)

---

## 2. NuGet 패키지 다운로드

![K-002](https://user-images.githubusercontent.com/57971757/176347546-6543d907-ea7e-4772-9aa4-ae2a2a91e2ac.jpg)



---

## 3. Protos 폴더생성 및 Protocol Buffer 추가

```js
//폴더위치 
//Protos/CostCenter.proto 

syntax = "proto3";
option csharp_namespace = "CostCenterProto";

import "google/protobuf/timestamp.proto";

package CostCenterSvc;

message CostCenterRequest{
  int32 CenterType = 1;
}

message GrpcDecimal {
  int64 units = 1;
  sfixed32 nanos = 2;
}

message CostCenterResponse{
  string jsonResult = 1;
}

service CostCenter8 {
  rpc CostCenterList(CostCenterRequest) returns (CostCenterResponse);
}

```

> Proto buffer를 생성을 해주고 빌드를 한다.

## 4. 전체 빌드를 하여 proto파일 컴파일

> 프로젝트를 빌드하고 나면 
> 프로젝트명.csproj 에서 GrpcServices = "Client" 를 추가한다.

```xml
	<ItemGroup>
		<Protobuf Include="Protos\MesExample.proto" GrpcServices="Client" />
	</ItemGroup>

```

![K-006](https://user-images.githubusercontent.com/57971757/176347621-a85e2e70-e9ac-4deb-821d-10ecf4d63ec6.jpg)

## 5. blazor 페이지에 코드 구현
<button class="btn btn-primary" @onclick="gRpc_Test">Click me</button>
```java
@inject IJSRuntime JSRuntime
@code {
    private int currentCount = 0;

    private void IncrementCount()
    {
        currentCount++;
    }

    private async void gRpc_Test()
    {
        var channel = GrpcChannel.ForAddress("http://localhost:50051", new GrpcChannelOptions
            {
                HttpHandler = new GrpcWebHandler(new HttpClientHandler()),

            });

        var client = new Greet.Greeter.GreeterClient(channel);

        var ExampleRequest = new com.example.ExampleService.ExampleServiceClient(channel);

        var grpcUnaryCall= ExampleRequest.UnaryCall(new com.example.ExampleRequest
            {
                PageIndex = 1,
                PageSize = 1,
                IsDescending = true
            }); 
        

        var reply = client.SayHello(new Greet.HelloRequest 
            { 
                Name = "블레이저에서 요청" 
            }
        );

        await JSRuntime.InvokeVoidAsync("console.log", "UnaryCall 결과 :", grpcUnaryCall.Result);
        await JSRuntime.InvokeVoidAsync("console.log", "SayHello 결과 :", reply.Message);

    }

}
```

Console 출력부분
![화면](https://user-images.githubusercontent.com/57971757/172742533-afbeb97d-aac0-41ef-a9b9-ce030155226e.png)

---

Service 출력부분
```js
Microsoft.AspNetCore.Routing.EndpointMiddleware: Information: Executed endpoint 'gRPC - /greet.Greeter/SayHello'
Microsoft.AspNetCore.Hosting.Diagnostics: Information: Request finished HTTP/2 POST http://localhost:50051/greet.Greeter/SayHello application/grpc-web - - 200 - application/grpc-web 7.0985ms
```

---

성공!!!
<br>



**Note:** `만들고나니 내것이 아니었다.` 