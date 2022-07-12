---
title: "[gRPC-Web] Blazor를 이용하여 gRPC 서비스 클라이언트 호출 방법 22-07-12"
excerpt: "C# Blazor를 활용하여 Web에서 gRPC통신하기"

categories:
  - C#
  
tags:
  - [C#, gRPC, HTTP2, Blazor]

permalink: 

toc: true
toc_sticky: true
 
date: 2022-06-27
last_modified_at: 2022-07-12
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
> 1. ***ConfigureServices*** 에서  ***service.addCors();*** 추가 <br>
> 2. ***Configure*** 에서 ***app.UseGrpcWeb();*** , ***app.UseCors();*** 를 추가한다. <br>
>> ***app.UseRouting();*** 과 ***app.UseEndpoints()*** 사이에 추가해야한다. <br>
> 3. ***EndPoints*** 에 endpoints.MapGrpcService<GreeterService>().EnableGrpcWeb(); <br>
>> 서비스부분에 ***EnableGrpcWeb()*** 추가 <br>

.Net6
> Program.cs 추가 <br>
> app.UseRouting(); 다음에 <br>
> app.UseGrpcWeb(); 를 추가한다.<br>

![K-007](https://user-images.githubusercontent.com/57971757/176347618-2193efeb-3ddb-451e-a551-36c175c201e5.jpg)

---

## 2. NuGet 패키지 다운로드

![K-002](https://user-images.githubusercontent.com/57971757/176347546-6543d907-ea7e-4772-9aa4-ae2a2a91e2ac.jpg)

> Google.Protobuf <br>
> Grpc.Net.Client <br>
> Grpc.Tools <br>

** 22.07.12 최근 패치에서 변경된 사항이 있다. 
> Grpc.Net.Client.Web 을 추가해야한다. <br>

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

> Proto buffer를 생성을 해주고 전체빌드를 한다.

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
```js
@using System.Threading.Tasks
@using Grpc.Net.Client
@using Grpc.Net.Client.Web
@using Mes.CostCenterProto
@inject IJSRuntime JSRuntime
@using System.Text.Json;
@using System.Text.Json.Serialization;
@using Newtonsoft.Json

@code {

    private string result = "";

    private async void gRpc_Test()
    {
        var channel = GrpcChannel.ForAddress("http://192.168.0.35:5215", new GrpcChannelOptions
            {
                HttpHandler = new GrpcWebHandler(new HttpClientHandler()),

            });

        var client = new CostCenter8.CostCenter8Client(channel);

        var reply = client.CostCenterList(new CostCenterRequest
            {
                CenterType = 1
            }
        );
        result = reply.JsonResult;

        string json = JsonConvert.SerializeObject(result);

        await JSRuntime.InvokeVoidAsync("console.log", "CostCenterList 결과 :", json);
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

![K-009](https://user-images.githubusercontent.com/57971757/176359416-b9b2fd79-a0c4-49e8-bb3b-a119ba211b33.jpg)

성공!!!
<br>



**Note:** `만들고나니 내것이 아니었다.` 