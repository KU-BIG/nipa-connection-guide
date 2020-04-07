
# Connection guide to NIPA server

> For KU-BIG Members

> DO NOT add any security informations such as IP, password in this repository

> It will be posted via another private channel

---

## Table of Contents


- [NIPA server](#nipa-server)
- [GPU Server Connection](#gpu-server-connection)
- [Setup](#setup)

---

## NIPA server

- [NIPA server 소개](https://ai-korea.kr/hpc/selectHpc.do)

### 서버 스펙

- OS: Ubuntu 16.04 LTS(Linux)
- GPU 할당량: 40 TFLOPS
- GPU 카드 유형: V100

### 자원 할당 정보

- 서비스 기간: 2020.03.30 ~ 2021.01.31
- CSP 업체: KT Cloud


---

## GPU Server Connection

## 0. 계저 관련

아래의 [username], [ip], [port]느 본 가이드에 포함되어 있지 않으며, 개별적으로 공지될 예정입니다.

## 1. MacOs, Ubuntu

**ssh 접속**

Terminal을 열고, bash에서 아래와 같이 입력하시면 됩니다.
```bash
$ ssh [username]@[ip] -p [port] 
```
접속이 되시면 password를 입력하시고 접속하시면 됩니다.



## 2. Windows

### 2-1. Windows10
- Window10의 경우 Window OpenSSH Client 사용
- [Window OpenSSH Client 사용하기](https://archwin.net/402)   

**접속방법**
1. cmd 실행
2. ssh 접속

cmd를 실행하시면 아래와 같이 입력하시면 됩니다.   

        ssh [username]@[ip] -p [port]   
        
예시
        
        C:\Users\starl>ssh user@12.34.56.789 -p 12345
        
성공적으로 마치면 아래와 같이 password를 입력하라고 뜹니다.

       [username]@[ip]'s password:    
       
password를 입력하시면 됩니다. (입력하는 비밀번호는 화면상에 나타나지 않습니다.)   


성공적이면 아래와 같은 화면이 뜹니다.   

![nipa_success](https://user-images.githubusercontent.com/49232148/78502609-ee030400-779c-11ea-9ee8-0369dd27f685.png)


### 2-2. Other Windows
- 다른 Window 버전의 경우putty사용
- [Putty 다운로드](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)

 
 
**PuTTY 다운로드**    

본인의 PC 사양에 맞는 PuTTY 버전을 설치    


**PuTTY 실행**   

putty.exe 실행하기    
![putty](https://user-images.githubusercontent.com/49232148/78502825-01629f00-779e-11ea-879e-63857a84a558.png)


**PuTTY terminal 접속** 


        login as: [username]   
        [username]u@[ip]'s password: GPU 서버 암호 입력하기 (입력하는 비밀번호는 화면상에 나타나지 않음)   



---

## Setup

---

## 사용량 모니터링
```bash
# gpu
watch -n 1 -d nvidia-smi
# cpu, ram
htop
```
---
