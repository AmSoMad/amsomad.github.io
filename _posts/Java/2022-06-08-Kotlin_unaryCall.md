---
title: "[Android-Kotlin] 안드로이드 gRPC 통신하는 예제"
excerpt: "프로토파일 생성부터"

categories:
  - 자바
  
tags:
  - [자바, Kotlin, Android]

permalink: 

toc: true
toc_sticky: true
 
date: 2022-06-10
last_modified_at: 2022-06-10
---


## 😬 안드로이드 App을 통한 gRPC 통신방법 🏭👩‍🏭👨‍🏭

---

# 1. build.Gradle(Project & Module) 추가

Project 부분에 


```js
buildscript {
    ext.grpcVersion = '1.40.1'

    dependencies {
        classpath "com.google.protobuf:protobuf-gradle-plugin:0.8.17"
        ...

    }
}

```

그리고 Moduel 부분에

```java
android {
  ...

    sourceSets {
        main {
            proto {
                srcDir 'src/main/kotlin'
            }
        }
    }

    ...
}

dependencies {
    implementation "io.grpc:grpc-stub:$grpcVersion"
    implementation "io.grpc:grpc-protobuf:$grpcVersion"
    implementation "io.grpc:grpc-okhttp:$grpcVersion"
    implementation "io.grpc:grpc-netty-shaded:$grpcVersion"
    implementation "io.grpc:grpc-auth:$grpcVersion"
}

protobuf {
    protoc {
        artifact = "com.google.protobuf:protoc:3.17.3"
    }
    plugins {
        grpc {
            artifact = "io.grpc:protoc-gen-grpc-java:$grpcVersion"
        }
        grpckt {
            artifact = "io.grpc:protoc-gen-grpc-kotlin:0.1.5"
        }
    }
    generateProtoTasks {
        all().each { task ->
            task.plugins {
                java { option 'lite' }
                grpc { option 'lite' }
                grpckt { option 'lite' }
            }
        }
    }
}

```
# 2. AndroidManifest 수정
```js
manifest.AndroidManifest.xml 에 추가하자.


    <uses-permission android:name="android.permission.INTERNET"/>  <-추가

    <application>... </application>

```

---

# 3. proto파일 추가
```js
Create Directory Folder
src/main/kotlin  -> Example.proto 생성
```
```js
syntax = "proto3";
option java_multiple_files = true;
option java_outer_classname = "EventProto";
option java_package = "com.example"; 

java_packge는 자동 생성으로 만들어진 코드들을 
Activity에서 import 할때 쓰는 경로
```
```js
package com.grpc.Example; 패키지명이 중요하다. 
기존 패키지명과 같을경우 충돌난다.
```
```js
message ExampleRequest {
  int32 pageIndex = 1;
  int32 pageSize = 2;
  bool isDescending = 3;
}

message ExampleResponse {
  string result = 1;
}

message GrpcDecimal {
  int64 units = 1;
  sfixed32 nanos = 2;
}
service ExampleService {
  rpc UnaryCall(ExampleRequest) returns (ExampleResponse)  {}
}

grpc 프로토파일을 생성해주고  
```


# 4. Make Project

망치를 눌러 Build를 하면 Java 폴더 하나가 generated 되면서 생성된다.<br>


# 5. 통신 실행

서비스 선언
```java
private val exampleService by lazy { ExampleServiceGrpcKt.ExampleServiceCoroutineStub(channel())}
```
```java
        val buttonUnary = findViewById<Button>(R.id.buttonUnary)

        buttonUnary.setOnClickListener {
            unaryCall()
        }

    private fun channel(): ManagedChannel {
        val url = URL("http://10.0.2.2:50051")
        val port = if (url.port == -1) url.defaultPort else url.port

        val builder = ManagedChannelBuilder.forAddress(url.host, port)
        if (url.protocol == "https") {
            builder.useTransportSecurity()
        } else {
            builder.usePlaintext()
        }
        return builder.executor(Dispatchers.Default.asExecutor()).build()
    }

    fun unaryCall() = runBlocking {
        try {
            val request = ExampleRequest
                .newBuilder()
                .setPageIndex(1)
                .setPageSize(1)
                .setIsDescending(true)
                .build()
            val response = exampleService.unaryCall(request)
            responseText.text = "msg: "+ response.result
            Log.i("message:", "result " + response.result)
        } catch (e: Exception){
            responseText.text = "error: " + e.message
            Log.w("error", " unaryCall -> " +  e.message)
        }
    }

```


안드로이드 App ->  .NET6 gRPC Service와 gRPC 통신 성공!


<br>



**Note:** `만들고나니 내것이 아니었다.` 