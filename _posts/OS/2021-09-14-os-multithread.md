---
title:  "멀티 쓰레드"
excerpt: "멀티쓰레드의 개념"

categories:
  - OS
tags:
  - [운영체제, 쓰레드]

toc: true
toc_sticky: true
 
date: 2021-09-14
last_modified_at: 2021-09-14
---
## 쓰레드의 종류
![image](https://user-images.githubusercontent.com/70308853/133248348-d05728e9-e708-4a82-b2c2-52a6b9de0b15.png)

* user thread 
* kernel thread
  * 운영체제가 직접 관리하는 쓰레드

## 유저쓰레드와 커널쓰레드의 관계
* Many-to-One Model(기본적인 모델)


  ![image](https://user-images.githubusercontent.com/70308853/133248642-fe88c492-57f9-48e0-8d16-aeca0f880393.png)

* One-to-One Model

  ![image](https://user-images.githubusercontent.com/70308853/133248926-d30c5011-ca91-4471-94e9-5b87a158d4da.png)

* Many-to-Many Model 

  ![image](https://user-images.githubusercontent.com/70308853/133249018-3308b20e-dccd-4786-837f-70012987b573.png)

## 쓰레드 라이브러리
* 쓰레드를 생성하고 관리하는 API
* 요즘 많이 사용하는 쓰레드 라이브러리
  * POSIX Pthreads(Linux, Unix 계열)
  * Windows thread(Window)
  * Java thread(JVM위에서 작동하기 때문에 OS에 따라 달라짐 -> ex) 리눅스에서 Pthread사용)
    * cf) Grand Central Dispatch(Apple)

## Pthreads
* POSIX가 정한 표준
* 쓰레드가 해야할 동작을 정의한 것, 구현X(하지만 Linux, Unix 계열에서 구현을 해놨기 때문에 일반적으로 Pthreads라 함은 구현체를 의미)

## 문제
### 1.
![image](https://user-images.githubusercontent.com/70308853/133251648-14da23a6-1147-48a7-97d1-f5d4c114f773.png)

![image](https://user-images.githubusercontent.com/70308853/133251752-9387af6f-2cf1-4a03-b491-240d536d4618.png)


![image](https://user-images.githubusercontent.com/70308853/133252256-0541cf7d-e40a-493d-be46-b19cb52fa7ef.png)

> 6, 2(메인 쓰레드까지 하면 8개)

## 2.
![image](https://user-images.githubusercontent.com/70308853/133253415-f91b96a1-74cd-4796-a800-b3003fad20d0.png)

![image](https://user-images.githubusercontent.com/70308853/133253447-22e0e6e7-2371-4f84-aeae-c8691421d558.png)

  > C : 5, P : 0

## Implict Threading(암묵적 쓰레딩)
* 동시적이고 병렬적인 애플리케이션을 디자인하는 것은 멀티코어 시스템에서의 멀티쓰레딩을 디자인하는 것과 같음
* 개발자가 직접 쓰레드를 관리하는 것은 매우 어려움 - > 컴파일러 또는 라이브러리에게 맡김

* 방법 4가지
  * Thread Pools
    * 필요한 여러개의 쓰레드를 쓰레드풀에다 저장하고 필요할 때마다 쓰레드풀에서 꺼내서 사용,반납
  
  * Fork & Join
    * explicit threading - > implicit threading 으로 만듬
    * 메인 쓰레드가 여러개의 자식쓰레드들을 만들고(fork) 자식 쓰레드들이 일을 마치고 다시 합쳐지는(join) 형태이다. 
  
  * OpenMP
    * 컴파일러에게 지시어를 줘서 OpenMP runtime library가 병렬처리를 하게함(C, C++의 API)
    * 쓰레딩을 language 수준에서 미리 기술하는 방법. parallel regions를 미리 정하는 형태로 동작하는데, 주로 #progma 코드를 이용하여 parallel regions를 정의해준다.
  ![image](https://user-images.githubusercontent.com/70308853/133256603-2e87be44-e3d4-4b66-80f8-eae821b2e06f.png)
  ![image](https://user-images.githubusercontent.com/70308853/133256799-507ec054-bf98-48f5-bade-bfb0d91b3569.png)
  ![image](https://user-images.githubusercontent.com/70308853/133257288-b085dba0-d036-4d81-9c14-77c327a616d0.png)
  ![image](https://user-images.githubusercontent.com/70308853/133256864-bc12fd9c-d270-4c77-8a47-ed5d0dc1d303.png)
  ![image](https://user-images.githubusercontent.com/70308853/133257483-030a6e3f-08b4-4f56-b1ba-6cdc8dc5a476.png)


  * Grand Central Dispatch(GCD)
    * Apple(masOS, iOS)에서 사용