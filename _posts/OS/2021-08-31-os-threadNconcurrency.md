---
title:  "쓰레드의 개념과 이해"
excerpt: "쓰레드의 개념"

categories:
  - OS
tags:
  - [운영체제, 쓰레드]

toc: true
toc_sticky: true
 
date: 2021-08-31
last_modified_at: 2021-09-01
---
## 쓰레드
* LWP(lightweight process)
* CPU를 점유하는 기본 단위

![image](https://user-images.githubusercontent.com/70308853/131498330-06826488-f4e8-4b35-86aa-8f4c2b8d2eab.png)

## 멀티쓰레드의 장점
![image](https://user-images.githubusercontent.com/70308853/131498717-d3672d86-809c-47be-9dff-52f61ca2d514.png)

* responsiveness : 응답을 기다리지 않아도 실행 가능
* Resource Sharing : 공유 메모리 or 메시지 패싱보다 쉬움
* Economy : context switching 보다 thread switching이 저렴
* Scalability : 멀티프로세서에서 확장의 이점이 있음

## 멀티쓰레드의 구현
* JAVA
  * 부모 쓰레드의 대기 - > join - > wait (X)

    ![image](https://user-images.githubusercontent.com/70308853/131666142-fc7a4474-3638-4e7e-bf30-2c1f7e971868.png)

  * 쓰레드의 종료 - > interrupt - > stop (X) 동기화의 문제로 안쓰임

    ![image](https://user-images.githubusercontent.com/70308853/131666312-e9a2c033-4102-4f40-9f49-417d0f316a18.png)

## 멀티코어 시스템에서의 멀티쓰레드
* 멀티코어 시스템에선 동시성이 향상됨
* 4개의 쓰레드가 있다고 가정할 때,
  * single-core : 쓰레드가 시간에 따라 interleaved - > 시분할
  ![image](https://user-images.githubusercontent.com/70308853/131667358-feebd736-7e23-4cf1-bac3-d879ca8d6f86.png)

  * multiple-cores : 쓰레드들이 병렬적으로 실행될 수 있음 - > 시분할 + 병렬
  ![image](https://user-images.githubusercontent.com/70308853/131667537-db7f8cc1-6d5a-4bbb-97d6-8e2fd4e855c8.png)

## 멀티코어 시스템에서 고려할 점
* Identifying tasks : 나눠서 작업해야할 영역인지 고민해야함(어떤 작업을 병렬처리할 것인지)
* Balance : 작업의 양을 적절하게 나눠야함
* Data splitting : 분리된 코어에서 실행할 작업의 데이터를 올바르게 나눠야함
* Data dependency : 실행할 작업들의 데이터 동기화에 대해 고민해야함
* Testing and debugging : 싱글 쓰레드일때보다 어려워짐

  ![image](https://user-images.githubusercontent.com/70308853/131669086-ec7a51cc-eba2-4290-a7da-f15125c196cb.png)

      cf) 기술이 많이 발전하여 요즘엔 분산 시스템 이용하여 분산 처리 ex)Hadoop

  ## Amdahl's Law(암달의 법칙)
  * 코어는 많을수록 좋은가? X (병렬처리가 안되는 작업이 많을수록 효율이 떨어짐)

    ![image](https://user-images.githubusercontent.com/70308853/131669742-a7fe4653-7607-4cff-a6a6-7d22bf059d9b.png)

    S : 병렬처리할 수 없는 작업


    N : 코어의 수

    ![image](https://user-images.githubusercontent.com/70308853/131669872-4acad183-8bc1-40e0-bc23-2fb204680e40.png)

    ![image](https://user-images.githubusercontent.com/70308853/131669924-4a59a426-08f3-47ac-a24d-e4e2e52ae9aa.png)





