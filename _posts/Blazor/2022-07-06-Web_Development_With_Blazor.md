---
title: "[Blazor]Web Development With Blazor - 22.07.06"
excerpt: "Papago와 함께 Jimmy Engstrom의 Blazor에 대한 이야기"

categories:
  - C#
  
tags:
  - [C#, Web, Blazor, WebAssembly]

permalink: 

toc: true
toc_sticky: true
 
date: 2022-07-06
last_modified_at: 2022-07-06
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
Blazor 애플리케이션을 테스트하는 기본 방법은 현재 없습니다. 
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







**Note:** `만들고나니 내것이 아니었다.` 