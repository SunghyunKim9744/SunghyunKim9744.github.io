---
title:  "운영체제 역할과 구조"
excerpt: "운영체제가 하는 일과 구조"

categories:
  - OS
tags:
  - [운영체제, 구조, 역할]

toc: true
toc_sticky: true
 
date: 2021-08-09
last_modified_at: 2021-08-10
---

## 컴퓨터의 구조

![image](https://user-images.githubusercontent.com/70308853/128698225-ad204dda-6e5e-46d2-8786-071b6067c9ad.png)
* 하드웨어
* 운영체제
* Application Program
* User

___
## 운영체제

* 보편적인 정의X
* 항상 켜져있는 프로그램 - > 커널(Kernel)이라 불림
* System & Application Programs

___
## 전통적인 컴퓨터
![image](https://user-images.githubusercontent.com/70308853/128699329-143b728d-2a6b-45bb-9969-7459bd7ec434.png)

* 1개 이상의 CPU
* BUS를 통해 많은 device 컨트롤러들이 연결

___
## 부트스트랩 프로그램
* 컴퓨터의 전원을 킬 시, ROM이 HDD에 있는 OS - > 메인메모리로 로드

___
## Interrupts(인터럽트)
![image](https://user-images.githubusercontent.com/70308853/128701017-b1f25463-5f25-48ad-b21d-e2aa04bb8083.png)

* BUS를 통해 하드웨어는 CPU에게 신호를 보냄으로써 Interrupt 발생

___
## 메모리 구조
![image](https://user-images.githubusercontent.com/70308853/128702003-4f959ad0-183f-4303-b068-87bc0691dd57.png)

* 위로 갈수록 빠르고 저장 공간이 적음

___
## I/O 구조
![image](https://user-images.githubusercontent.com/70308853/128702396-3a868313-7fc9-4846-b490-b0d65261d158.png)

* DMA(Direct Memory Access)

___
## 컴퓨터 시스템의 구조
* SMP(Symmetric multiprocessing)

    
    ![image](https://user-images.githubusercontent.com/70308853/128702842-bcafb44f-4b6a-42e1-9ae8-bd5f973bb2d6.png)
    * 한개의 메모리에 여러 개의 CPU


* Multi-core design

    ![image](https://user-images.githubusercontent.com/70308853/128703161-ca66d50d-6a4a-41bf-b5b0-fa3f7b2623c7.png)

    * 한개의 CPU에 여러개의 core

___
## 운영체제의 작업

* Multiprogramming

    ![image](https://user-images.githubusercontent.com/70308853/128703543-4c46bff3-3dd4-4cd7-ae15-60f033b31d16.png)

    * 한 개의 메모리에 여러개의 프로그램을 올리는 것
    * CPU의 사용효율을 높임

* Multitasking(=multiprocessing)
    
    * Multiprogramming의 논리적 확장
    * 여러 작업을 처리
    * CPU scheduling
        * 다음으로 어떤 프로세스를 처리할 것인지

___
## 운영체제 Mode

![image](https://user-images.githubusercontent.com/70308853/128705111-7a850f7b-040f-490f-a77d-bb229ea1e8fd.png)

* User mode
    * 다른 프로그램 작업을 방해하는 것을 막기 위함

* Kernel mode
    * 직접적인 하드웨어를 제어하는 모드
        * System Call - > O/S에게 서비스를 요청하는 것

___
## Virtualization(가상화)
![image](https://user-images.githubusercontent.com/70308853/128854281-c3f17766-7c60-4bfa-b826-ea99be4631b7.png)

* VMM(virtual machine manager)를 통해 여러 운영체제 사용

        ex) VMM - > VMware, XEN, WSL

___
## 컴퓨터 환경
* 전통적인 컴퓨터
* 모바일 컴퓨터
* Client-Server 컴퓨터
![image](https://user-images.githubusercontent.com/70308853/128857634-4c52fe73-8ff4-436c-b222-23b464d81ab5.png)

* Peer-to-Perr 컴퓨터
![image](https://user-images.githubusercontent.com/70308853/128857705-a406a070-1e5b-4271-8505-43740f2f94bb.png)

* Cloud 컴퓨터
![image](https://user-images.githubusercontent.com/70308853/128858280-38ad08d9-6043-4b4c-adc2-00869cfc62b4.png)

* Real-Time Embedded Systems

___
## 운영체제의 역할
* 프로그램이 실행될 수 있는 환경 제공

    * UI
    * 프로그램 실행
    * I/O 작업
    * File
    * 통신
    * Error 발견
    * 자원 할당
    * Logging
    * 보안 & 보호

![image](https://user-images.githubusercontent.com/70308853/128859214-8a767f92-42a6-483b-a59c-1e30e39337d6.png)

___
## 사용자와 OS의 인터페이스
* CLI
* GUI
* Touch-Screen

___
## 응용프로그램과 OS의 인터페이스
* System calls (= API)

![image](https://user-images.githubusercontent.com/70308853/128859709-3e06ec85-1c85-4bbd-a0e6-3edc8f849632.png)

![image](https://user-images.githubusercontent.com/70308853/128860132-633cbf01-a4b1-4b59-944f-38aabf513c41.png)

![image](https://user-images.githubusercontent.com/70308853/128860268-e77753c9-8baf-479f-8f83-9250f128248c.png)

* System calls 예시

![image](https://user-images.githubusercontent.com/70308853/128860403-9333b2f4-3644-43b7-bda2-3ac3ecccd631.png)




