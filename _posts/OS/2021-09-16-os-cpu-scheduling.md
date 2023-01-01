---
title:  "CPU Scheduling"
excerpt: "CPU scheduling"

categories:
  - OS
tags:
  - [운영체제, 쓰레드]

toc: true
toc_sticky: true
 
date: 2021-09-16
last_modified_at: 2021-09-16
---
## CPU Scheduling
* 멀티프로그래밍된 OS에서 필수
      
      멀티프로그래밍

      * 동시에 여러 프로세스들이 실행되는 것
      * CPU 효율을 극대화하기 위해

* 프로세스 관점에서의 상태
![image](https://user-images.githubusercontent.com/70308853/133604245-4643e2cc-5ea0-42b6-91b0-e3bee78ad5ff.png)
      
      CPU burst : CPU를 사용하는 상태(running)
      I/O burst : I/O 대기 상태(waiting)

* CPU burst 빈도
![image](https://user-images.githubusercontent.com/70308853/133604599-afa0c793-00a7-4e9b-93bb-dc2c5aa50fd6.png)

  * 일반적으로 I/O burst가 더 많음 - > CPU Scheduling 중요함

        CPU bound : CPU burst가 많은것
        I/O bound : I/O burst가 많은것

## CPU Scheduler
* ready 상태에 있는 프로세스들 중 어떤 프로세스에게 CPU를 할당해줄지 선택

* 다음 프로세스를 선택하는 방법
  * Linked List
  * Binary Tree
  * FIFO Queue
  * Priority Queue

* 프로세스를 선택하고 난 후
  * Preemptive scheduling(선점)
    * 강제적으로 사용중인 프로세스의 CPU할당을 해제시킴
    * 스케쥴러가 강제적으로 사용중인 프로세스의 CPU할당을 해제

  * Non-preemptive scheduling(비선점)
    * 사용중인 프로세스의 CPU할당을 해제시키지 못함
    * 사용중인 프로세스가 자발적으로 CPU할당을 해제할때까지 terminating 또는 switching 못함

=====================================
* CPU-scheduling할 때 의사결정
  1. 프로세스가 running - > waiting 상태가 될 때
  2. 프로세스가 running - > ready 상태가 될 때
  3. 프로세스가 waiting - > ready 상태가 될 때
  4. 프로세스가 종료될 때

      cf) 
      
      1,4 = > non-preemptive

      2,3 = > preemptive or non-preemptive
      
       = > 현대적인 OS는 preemptive(더 효율적임)

      
      