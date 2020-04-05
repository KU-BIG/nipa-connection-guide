
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

### 1. Linux


### 2. Windows

#### 2-1. Windows10
- Window10의 경우 Window OpenSSH Client 사용
- [Window OpenSSH Client 사용하기](https://archwin.net/402)   

**접속방법**
1. cmd 실행
2. ssh 접속

cmd를 실행하시면 아래와 같이 입력하시면 됩니다.   

        ssh ubuntu@[ip address] -p [ssh number]   
        
예시
        
        C:\Users\starl>ssh ubuntu@12.34.56.789 -p 12345
        
성공적으로 마치면 아래와 같이 password를 입력하라고 뜹니다.

       ubuntu@[ip address]'s password:    
       
password를 입력하시면 됩니다.   


성공적이면 아래와 같은 화면이 뜹니다.   

#### 2-2. Other Windows
- 다른 Window 버전의 경우putty사용
- [Putty 다운로드](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)



---

## Setup

---
