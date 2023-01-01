---
title:  "프로세스의 생성"
excerpt: "프로세스의 생성 과정"

categories:
  - OS
tags:
  - [운영체제, 프로세스]

toc: true
toc_sticky: true
 
date: 2021-08-12
last_modified_at: 2021-08-12
---
## UNIX O/S
* fork() System call - > process 생성
* 자식 프로세스는 부모 프로세스의 주소 공간을 복사해서 생성
* fork()의 반환 값이 0이면 자식, 프로세스 아이디 값이면 부모

___
## fork()
* 부모 프로세스
    1. 실행
    2. 자식 프로세스가 종료될 떄까지 ready queue에서 wati queue로 이동 - > wait() System call

![image](https://user-images.githubusercontent.com/70308853/129194058-15771eef-5d8a-4308-b473-d4e9e0f3a432.png)

-> 5

![image](https://user-images.githubusercontent.com/70308853/129193976-a53c9d2f-b827-4113-b0f2-05dc928118e9.png)

-> 8

![image](https://user-images.githubusercontent.com/70308853/129194366-05963937-745d-4953-bb97-5bd955588b88.png)

-> 16

![image](https://user-images.githubusercontent.com/70308853/129195074-ddf58208-3bf5-4470-864e-0fc8b07ebae2.png)

-> Child Complete

        execlp() - > 메모리를 덮어씀
        ls로 덮어쓰기

![image](https://user-images.githubusercontent.com/70308853/129195864-7df65e87-c9aa-4457-9c5f-22d4eb414f32.png)

-> B = C

            getpid() - > 자신의 프로세스 아이디 반환
