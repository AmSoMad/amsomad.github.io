---
title: "[Blazor]Web Development With Blazor - (22.07.06 ~ ing)"
excerpt: "Papago와 함께 Jimmy Engstrom의 Blazor에 대한 이야기"

categories:
  - C#
  
tags:
  - [C#, Web, Blazor, WebAssembly]

permalink: 

toc: true
toc_sticky: true
 
date: 2022-07-06
last_modified_at: 2022-07-10
---

# 🦝 들어가며

## 🦝 감사의 말

![KakaoTalk_20220706_133601347](https://user-images.githubusercontent.com/57971757/177484773-b612597d-56fa-49d2-895d-e42339571795.jpg) <br>


현재 한국에는 C# 즉 .NET 개발자가 많이 없다. <br>
그만큼 문서도 찾기 어렵고 전문서적도 구하기가 어렵다 <br>
물론 영어는 엄청많다 <br>
최근 Blazor를 보면서 MSDN의 번역본을 읽는것도 한계가왔다 <br>
서점에가서 책을 사보려 했는데 1권도 국내에 없더라 <br>
생각도 못했다. <br>
진짜 없더라.... <br>
설마 번역본도 없을꺼라곤.... <br>
이 책을 읽는데 많은 어려움이 있었으나 <br>
강제로 영어공부도 되고 쉽게 읽을 수 있는 시대를 <br>
만들어준 모든 감사함을 Papago에게 표하며 <br>
이런 책을 내주셔서 감사합니다. Thank you. Jimmy Engstrom <br>

---

저의 이 블로그는 영어를 잘 모르는 사람이 읽고 <br>
Blazor를 많은 사람들이 이용할 수 있도록 <br>
도움이 되고자 작성 되었습니다.<br>


# 🦝 이 책이 다루고 있는 것

> 총 3가지의 Section 으로 구성되어있다. <br>
> Basics 부분은 Chapter 1, 2이고<br>
> 애플리케이션 구축부분은 Chapter 3.. 11 이다.<br>
> 마지막으로 Debug와 Test 그리고 운영관련 내용은 <br>
> Chapter 12, 13, 14, 15에 있다.<br>

## 🦝 Chapter 1. Hello Blazor 
첫번째장에서는 Server-Side Blazor와 Client-Side Blazor의 차이를 설명하고자 한다. <br>
또한 기술이 어떻게 작동하는지에 대한 개요와 Blazor의 유래에 대한 역사를 간략히 볼 수 있다. <br>
해당 기술을 이해하는데에는 호스팅 모델 간의 구조와 차이점을 알고 있는것이 필수적이다. <br>
**[Blazor 앱 호스팅 모델](https://docs.microsoft.com/ko-kr/dotnet/architecture/blazor-for-web-forms-developers/hosting-models)** <br>
**[ASP.NET Core Blazor 호스팅 모델](https://docs.microsoft.com/ko-kr/aspnet/core/blazor/hosting-models?view=aspnetcore-6.0)** <br>

## 🦝 Chapter 2. Blazor App 만들기
개발 환경을 구축을 하고 기본적인 설정을 하는 방법을 이해를 하며, <br>
Blazor App(Server-side & Client-side)을 만들고 프로젝트 템플릿의 구조를 배우게 됩니다.<br>

## 🦝 Chapter 3. Entity Freamework Core 소개
Entity Framework Core 소개에서는 데이터를 저장할 <br>
데이터베이스를 만드는방법을 설명합니다. <br>
(Blog Post, categories, and tags) <br>
그리고 .NET Tool 을 사용하여 새로운 프로젝트를 만들게 됩니다. <br>

## 🦝 Chapter 4. Blazor 기본 구성요소
Blazor의 구성요소, LifeCycle Event, <br>
매개변수 추가 및 구성요소간 매개 변수 공유에 설명합니다. <br>
또한 Reusable 즉 재사용 구성요소도 만듭니다.

## 🦝 Chapter 5. Blazor 고급 구성요소
Blazor의 고급 구성요소는 하위 구성요소, <br>
계단식 매개 변수 및 값과 같은 기능을 추가하고 <br>
작업 및 콜백 사용 방법을 다루게 됩니다. <br>

## 🦝 Chapter 6. 유효성 검사
Validation이 포함된 Form을 만들고, Form의 검증방법과 <br>
자체 Validation Mechanism을 구축하는 방법을 살펴봅니다. <br>
또한 이번 Chapter에서는 확인란을 선택할 때 파일 업로드, 텍스트, <br>
숫자 및 "trigger" 코드로 처리할때 가장 일반적인 사용 사례를 설명합니다. <br>

## 🦝 Chapter 7. API 만들기
Blazor WebAssembly를 사용할때 데이터를 얻기위해 API가 필요로합니다. <br>
해당 Chapter에서는 API를 만드는 방법에대해 살펴봅니다. <br>

## 🦝 Chapter 8. 인증과 권한부여
Blazor에 인증(Authentication) 및 권한(Authorization)을 추가하고 <br>
로그인 페이지로 리다이렉션(Redirect)과 같은 네비게이션이 예상대로 작동하는지 확인합니다. <br>

## 🦝 Chapter 9. 코드 및 리소스 공유
공유 라이브러리에 필요한 모든 항목을 추가하여, <br>
클라이언트와 서버에서 코드를 공유하는 방법을 살펴봅니다. <br>
그리고 이번 장에서는 NuGet 패키지로 다른 사용자와  <br>
공유할 수 있는 라이브러리를 구축합니다. <br>

## 🦝 Chapter 10. JavaScript Interop
Blazor를 사용할때 JavaScript의 라이브러리를 활용하고 <br>
C#에서 JavaScript로 호출할 수 있는 방법을 살펴봅니다. <br>
또한 JavaScript가 Blazor 앱에서 C# 함수를 호출할 수 있는 방법 또한 살펴봅니다. <br>
**[ASP.NET Core Blazor의 .NET 메서드에서 JavaScript 함수 호출](https://docs.microsoft.com/ko-kr/aspnet/core/blazor/javascript-interoperability/call-javascript-from-dotnet?view=aspnetcore-6.0)** <br>
**[ASP.NET Core Blazor의 JavaScript 함수에서 .NET 메서드 호출](https://docs.microsoft.com/ko-kr/aspnet/core/blazor/javascript-interoperability/call-dotnet-from-javascript?view=aspnetcore-6.0)** <br>

## 🦝 Chapter 11. 상태 관리
LocalStorage를 사용하거나, 종속성 주입을 사용하여 <br>
데이터를 메모리에 보관하는것과 같은 다양한 상태 <br>
관리방법(지속 데이터 - persisting data)을 살펴봅니다. <br>
그리고 데이터베이스의 영구적인 데이터뿐만 아니라 <br>
여러 프로젝트 유형에 대한 종속성 주입의 작동 바식도 다룰 수 있습니다. <br>
**[ASP.NET Core Blazor 종속성 주입](https://docs.microsoft.com/ko-kr/aspnet/core/blazor/fundamentals/dependency-injection?view=aspnetcore-6.0)** <br>

## 🦝 Chapter 12. Debugging
응용프로그램을 디버깅하고 확장된 Logging을 추가하여 <br>
문제점을 파악하는 방법을 살펴봅니다. <br>
또한 웹 브라우저내에서 직접 C# 코드를 디버깅할 수도 있습니다. <br>
**[ASP.NET Core Blazor 로깅](https://docs.microsoft.com/ko-kr/aspnet/core/blazor/fundamentals/logging?view=aspnetcore-6.0)** <br>

## 🦝 Chapter 13. Testing
구성요소가 제대로 작동하는지(계속 작동하는지) 확인할 수 있도록 자동화된 테스트를 살펴봅니다. <br>
Blazor 애플리케이션을 테스트하는 기본 방법은 현재 없습니다. <br>
허나 bUnit 이라는 커뮤니티 프로젝트가 존재합니다. <br>
**[ASP.NET Core Razor에서 Blazor 구성 요소 테스트](https://docs.microsoft.com/ko-kr/aspnet/core/blazor/test?view=aspnetcore-6.0)** <br>
**[bUnit](https://github.com/bUnit-dev/bUnit)** <br>
**[Playwright for .NET](https://playwright.dev/dotnet/)** <br>

## 🦝 Chapter 14. 운영 단계
운영환경에서 Blazor를 실행할 때 고려해야 할 다양한 사항을 살펴봅니다. <br>

## 🦝 Chapter 15. Where to Go from Here
실전에서 사용할수있는 몇가지 자료, 그리고 이 책을 끝맽는 짧은 마지막 챕터 입니다. 

---

## 🦝 책을 읽기전 개발환경 요구사항

개발 환경 <br>
> 1. Visual Studio 2019 이상, Mac용 Visual Studio For Mac, Visual Studio Code
> 2. Windown 10 이상, MacOS 또는 Linux
> 3. 책에서 사용하는 ASP.NET Core 5이다
>> 허나 나는 ASP.NET core 6.0 를 쓸 것이다. 

글쓴이의 요구사항 <br>
> 1. Tweet plz me @EngstromJimmy <br>
> 2. I hope you have as much fun reading this book as i had writing it.
>> 내가 책을 쓴만큼 너도 재미있게 읽어주길 바란다.
>> 이미 재미있다.
> 3. **[https://github.com/EngstromJimmy](https://github.com/EngstromJimmy)** 그의 Github <br>
> 4. 예제 코드 **[https://github.com/PacktPublishing/Web-Development-with-Blazor](https://github.com/PacktPublishing/Web-Development-with-Blazor)** <br>
>> 다른 풍부한 책과 영상 카탈로그의 번들코드도 포함되어 있으니 참고하자.
> 5. 컬러이미지는 **[ColorImages.pdf](https://static.packt-cdn.com/downloads/9781800208728_ColorImages.pdf)**

---

# 🦝 Chapter 1
## 🦝 Introducting Blazor (Blazor의 탄생)

Blazor는 오픈 소스 웹 UI SPA 프레임워크이다. <br>
> SPA - Single Page Application <br>
> UI - User Interface <br>
> PROGRAMMING LANGUAGE - C# <br>
> WEB FRAMEWORK - Blazor <br>

쉽게 말을하자면 Bindings, Event, Forms and validation, <br>
Injection, debugging 등등 많은 기능을 완벽하게 지원을 한다. <br>
즉 HTML, CSS 및 C#을 사용하여 대화형 SPA 웹 애플리케이션을 <br>
만들수 있단 뜻이다. <br>

때는 **[2017년 NDC 오슬로에서 열린 개발자 콘퍼런스](https://www.youtube.com/watch?v=MiLAE6HMr10&list=PL03Lrmd9CiGewi0lbnahxEpisoP5WZocX&index=145)** 에서 Steve Sanderson가 발표했다. <br>
제목이 'Web Apps can't really do *that*, can they?' <br>
번역을해보면 웹앱은 할수없잖아 그치? 란다..<br>

그는 Microsoft의 ASP.NET Team에 있을때다. <br>
하지만 스티브는 데모를 보여주고 싶었고, 생각을 해낸 것이 <br>
웹어셈블리에서 C#을 실행하는게 가능할까? 였다 한다.<br>
Github에서 'Dot Net Anywhere' 라고 불리는 오래된 inactive 프로젝트를 <br>
발견을 했고 그것은 C 로 작성이 되었으며 C코드를 웹어셈블리로 컴파일 하기위해 <br>
(방금 우리가 한거처럼 유사한 형태로) 도구를 사용을 했다. <br>

그는 브라우저 안에서 간단한 콘솔앱을 실행했다. <br>
이미 이것만으로도 엄청난 데모였지만 더 나아가서 <br>
" 이 위에 간단한 프레임워크를 만들 수 있을까? " 라고 생각을했고, <br>
Tolling 작업도 알아보았다. <br>

Session이 시작되면 작업 샘플을 사용하여 새로운 프로젝트를 만들고, <br>
Tooling 지원이 뛰어난 Todo-list를 만들고, <br>
브라우저 내에서 프로젝트를 실행하였습니다. <br>

Damaian Edwards, David Fowler (둘다 .NET team) 이라는 이름의 팀원들이 <br>
스티브가 시범을 보이려는것을 보여줫고, 머리가 터지고, 턱이빠지는것을 묘사했다. <br>
그리고 그렇게 Blazor의 원형이 탄생한 것이다. <br>

Blazor라는 이름은 브라우저(Browser)와 Razor(combine code와 HTML을 결합하는 기술)의 <br>
합성어에서 유래됬으며, L을 차가하면 더 좋게 들리지만 그외에 실질적인 약어는 없다. <br>

각각 Blazor Server, including Blazor WebAssembly, WebWindow, and Moblie Bindings. <br>
얘들은 몇가지 다른 형태가 있다. <br>

---

## 🦝 Blazor Server

Blazor Server는 아래의 다이어그램처럼 SignalR을 사용하여 Client와 Server간 통신을 합니다. <br>

![K-006](https://user-images.githubusercontent.com/57971757/178135596-98e6bb50-27e7-4f7b-b8c4-07051c34f938.png) <br>
> Blazor Server 개요 <br>

SignalR은 다양한 데이터 전송 수단을 사용할 수 있으며, Server 및 Client 기능에따라 <br>
최적의 전송 프로토콜을 자동으로 선택을 합니다. <br>
**[ASP.NET Core 개요SignalR](https://docs.microsoft.com/ko-kr/aspnet/core/signalr/introduction?view=aspnetcore-6.0)** <br>

SignalR은 항상 HTML에 내장된 전송 프로토콜인 WebSockets을 사용하려합니다. <br>
WebSocket이 활성화 되지 않다면 다른 포로토콜로 정상적으로 폴백(fall Back)이 됩니다. <br>
(알아서 다른 프로토콜을 찾는다는 것이다.) <br>

Blazor는 Componets(컴포넌트)라 불리는 재사용 가능한 UI요소를 사용하여 구축됩니다. (3장 Entity Framework Core에서 소개된다.) <br>
각 구성요소는 C# 코드, 마크업을 포함하여 다른 구성요소를 포함할 수 있습니다. <br>
Razor 문법을 사용하여 마크업과 C#코드를 혼합하거나 원하는 경우 C#의 모든 작업을 수행할 수도 있다. <br>
구성요소의 경우 사용자의 상호작용(버튼클릭 혹은 트리거 등)을 통하여 업데이트 할 수 있습니다. <br>

각 구성요소는 객체 상태와 모든 속성 및 값을 포함하는 DOM의 이진표현인 render tree로 렌더링됩니다. <br>

render tree는 이전 render tree와 비교하여 변경된 사항을 추적한 다음 <br>
DOM을 업데이트를 하기위해 이진 형식을 사용하여 SignalR을 통해 변경된 사항만 전송을 합니다. <br>

Client 측면에서는 JavaScript의 변경된 사항을 수신하고 해당 페이지를 업데이트합니다. <br>
이걸 기존의 ASP.NET 과 비교를해보면, 전체 페이지가 아닌 구성요소 자체만 렌더링하고 <br> 
전체 페이지가 아닌 실제 변경 사항만 DOM으로 전송을 합니다. <br>

물론 Blazor Server에는 단점도 존재를 합니다. <br>
> 1. 렌더링 작업은 서버에서 수행되기에 항성 서버에 연결이 되어야 한다. <br>
> 인터넷 연결이 잘못된 경우 사이트가 작동하지 않을 수 있다. <br>
> 또한 Blazor Server를 사용하지않는 사이트와 큰차이로는 <br>
> 페이지를 전송을 한 후 다른 페이지가 요청이 있을때 까지 연결을 끊을 수 있는데, <br>
> Blazor를 사용하면 해당 연결(SignalR)이 항상 연결되있어야 한다. <br>
> 2. 연결이 되있어야 하니 offline/PWA 모드는 없다. <br>
> 3. 모든 클릭, 페이지 업데이트는 서버로 왕복해야 하므로 대기 시간이 길어질 수 있다. <br>
> Blazor Server는 변경된 데이터만 전송을 한다. <br>
> 느린 응답 시간을 경험해 본 적이 없다. 라고 작자는 말한다. <br>
> 4. 서버에 연결해야 하기에 해당 서버의 로드가 증가하여 확장이 어렵다. <br>
> 이 문제를 해결하기 위해 Azure SignalR 허브를 사용하면 지속적인 연결을 <br>
> 처리하고, 서버가 콘텐츠 전송에 집중할 수 있다. <br>
>  **[Azure SignalR Service란?](https://docs.microsoft.com/ko-kr/azure/azure-signalr/signalr-overview)** <br>
>  **[ASP.NET Core용 SignalR에서 허브 사용](https://docs.microsoft.com/ko-kr/aspnet/core/signalr/hubs?view=aspnetcore-6.0)** <br>
> 5. 실행 할 수 있으려면 ASP.NET Core를 지원하는 서버여야 한다. 

허나 Blazoer Server에는 다음과 같은 장점도 있다.
> 1. 클라이언트가 다운받는 형태가 아주 작은형태로 전송된다 물론 충분히 코드가 포함되어 있다. <br>
> 2. 서버에서 실행중이므로 앱은 서버의 기능을 최대한 활용 할 수 있다. <br>
> 3. 사이트가 WebAssembly를 지원하지 않는 이전 웹브라우저에도 작동한다. <br>
> 4. 코드가 서버에서 실행되며 서버에 남아 있으므로 코드를 디컴파일 할 수 없다. <br>
> 5. 코드는 서버(또는 클라우드)에서 실행되므로 조직 내의 서비스 및 데이터베이스에 직접 호출 할수 있다. <br>

작자의 회사에는 이미 큰사이트가 준비되어 있기에 프로젝트에 Blazor Server를 사용하기로 결정했다. <br>
고객 포털과 내부 CRM 툴이 있었다. <br>
우리의 접근 방식은 한번에 하나의 구성요소를 가져와서 Blazor Component를 변경하는 것이었다 . <br>
대부분의 경우 ASP.NET MVC위에 기능을 추가하는것보다 Blazor에서 Component를 <br>
리메이크(수정)하는게 훨신 빠르다는걸 금세 알게 되었다. <br>

변환을 통해 최종적으로 사용자환경(UX)는 더욱 향상되었습니다. <br>
페이지 로딩속도가 빨라지면 전체 페이지를 대신 필요에따라 페이지의 일부를 다시 로드할 수도 있습니다. <br>
오히려 Blazor 때문에 새로운 이슈가 발생을 했다. 그건 너무 빠르다는것 <br>

아무 일도 일어나지 않았기 때문에 사용자들은 데이터가 저장되었는지 이해를 하지 못했습니다. <br>
일이 일어났지만 사용자가 알아채기에는 너무 빨랐기 때문이지요. <br>
갑자기, 우리는 UX와 사용자에게 무언가가 바뀌었다는 것을 어떻게 알려야 하는지에 대해 <br>
생각을 해야 했습니다. 물론 작자의 생각에는 Blazor의 매우 큰장점으로 인한 부작용이다 라고 <br>
생각한다. <br>

Blazor Server만이 Blazor를 실행할 수 있는 유일한 방법은 아니다. WebAssembly를 통하여 <br>
Client에서 실행을 할 수도 있습니다.

---

## 🦝 Blazor WebAssembly

서버에서 Blazor를 실행하는 방식이 아닌. WebAssembly를 사용하여 웹 브라우저 내에서 <br>
실행할 수 있습니다. <br>

현재 C#을 WebAssembly로 컴파일을 할 방법이 없다. <br>
대신 Microsoft에서는 모노 런타임(C로 작성된)을 가져와서 WebAssembly로 컴파일 했다<br>

Blazor의 WebAssembly 버전은 다음 그림처럼 서버 버전과 매우 비슷하게 움직입니다.  <br>
모든항목을 서버에서 WebAssembly로(브라우져) 옮기고 웹브라우저에서 실행을 합니다. <br>
..Fihure 1.3.. <br>

render tree는 WebAssembly에서도 생성되고 서버에서 razor pages를 실행하는대신<br>
웹브라우져 내에서 실행이된다. <br>

SignalR 대신에 WebAssembly는 직접 DOM에 Access(접근)이 불가하기에 <br>
Blazor 는 직접 Javascript Interop으로 DOM을 생성하고 업데이트합니다. <br>
여기서 WebAssembly로 컴파일이되는 mono runtime을 dotnet.wasm이라고 합니다. <br>
페이지에서는 dotnet.wasm을 로드하는 javascript가 포함이 되어있습니다. <br>

컴파일이 된 후 그다음에는 Blazor.boot.Json 파일을 다운로드 받습니다. <br>
해당파일은 응용프로그램을 실행하는 데 필요한 모든 파일과 응용프로그램의 <br>
진입점을 포함하는 JSON파일 입니다. <br>

Visual Studio에서 새로운 Blazor 프로젝트를 생성을하면 <br>
시작할때 생성되는 기본 샘플 사이트내부에. Blazor.boot.json 파일이있다. <br>
해당 파일에는 다운로드해야 하는 63개가 dependencides되어 있다. <br>

.NET DLLs가 실행이 된다는 것은
프로그램이 브라우져내에서 .NET Framework가 동작하기위해서 필요한 요소들을 <br>
쓰기위해 .Net DLLs 가 작동이된다. <br>
















# 🦝 작업을 하면서..
## 🦝 필수 사전지식

**[ASP.NET Core의 Razor Pages 소개](https://docs.microsoft.com/ko-kr/aspnet/core/razor-pages/?view=aspnetcore-6.0&tabs=visual-studio)** <br>

**[ASP.NET Core용 Razor 구문 참조](https://docs.microsoft.com/ko-kr/aspnet/core/mvc/views/razor?view=aspnetcore-6.0)** <br>
> Razor는 웹 페이지에 .NET 기반 코드를 포함하는 태그 구문입니다. Razor 구문은 <br>
> Razor 태그, C# 및 HTML로 구성됩니다. Razor를 포함하는 파일의 확장명은 <br>
> 일반적으로 .cshtml입니다. Razor는 Razor 구성 요소 파일(.razor)에도 있습니다. <br>



**Note:** `만들고나니 내것이 아니었다.` 