
# Connection guide to NIPA server

> For KU-BIG Members

> DO NOT add any security informations such as IP, password in this repository

> It will be posted via another private channel

---

## Table of Contents


- [NIPA server](#nipa-server)
- [Server Connection](#server-connection)
- [Setup](#setup)
- [Pyenv Guide](#pyenv-guide)
- [Error Guide](#error)
- [사용량 모니터링](#사용량-모니터링)
- [Contact](#contact)
- [Server Guide for Administrators](#server-guide-for-administrators)

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
- 열심히 사용하지 않을 경우 다시 회수당할 수 있으므로 모두 많이 사용해 주시길 바랍니다!


---

## Server Connection

## 0. 계정 관련

아래의 [username], [ip], [port]느 본 가이드에 포함되어 있지 않으며, 개별적으로 공지될 예정입니다.

## 1. MacOs, Ubuntu

**ssh 접속**

Terminal을 열고, bash에서 아래와 같이 입력하시면 됩니다.
```bash
$ ssh -L [포트포워딩할 포트1]:localhost:[포트포워딩할 포트1] -L [포트포워딩할 포트2]:localhost:[포트포워딩할 포트2] [username]@[ip] -p [port]
```

또는  
```bash
$ ssh -L [포트포워딩할 포트1]:localhost:[포트포워딩할 포트1] [username]@[ip] -p [port]
```

포트포워딩할 포트 개수는 본인이 원하시는 개수로 선택하시면 됩니다.   
본인이 jupyter lab 브라우저 한 개만 여실 경우에는 [포트포워딩할 포트1]만 입력하셔도 됩니다.    
본인이 jupyter lab, tensorboard 2개의 브라우저를 여실 경우에는 [포트포워딩할 포트1], [포트포워딩할 포트2] 두 개를 입력하시면 됩니다.   
만약 더 필요하시다 하면 그 이상으로 사용하시면 됩니다.      




[포트포워딩 할 포트]로는 본인이 원하시는 임의의 4-5자리 숫자를 입력하시면 됩니다. ex) 2456, 84322    
다른 유저와 [포트포워딩 할 포트]가 겹치지 않기 위해 1234나 9999와 같은 간단한 숫자 말고 최대한 다채로운 숫자를 사용하시길 권장드립니다.    
후에 jupyter lab처럼 브라우저에서 열어야 하는 프로그램이 있을 경우 브라우저에 

```
localhost:[포트포워딩할 포트]
```
를 입력하시면 됩니다.

예시: 
```bash
$ ssh -L 1234:localhost:1234 yeeun.song@12.34.567.890 -p 12345
```
```
localhost:1234
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
```
ssh -L [포트포워딩할 포트1]:localhost:[포트포워딩할 포트1] -L [포트포워딩할 포트2]:localhost:[포트포워딩할 포트2] [username]@[ip] -p [port]
```


또는  
```bash
ssh -L [포트포워딩할 포트1]:localhost:[포트포워딩할 포트1] [username]@[ip] -p [port]
```

포트포워딩할 포트 개수는 본인이 원하시는 개수로 선택하시면 됩니다.   
본인이 jupyter lab 브라우저 한 개만 여실 경우에는 [포트포워딩할 포트1]만 입력하셔도 됩니다.    
본인이 jupyter lab, tensorboard 2개의 브라우저를 여실 경우에는 [포트포워딩할 포트1], [포트포워딩할 포트2] 두 개를 입력하시면 됩니다.   
만약 더 필요하시다 하면 그 이상으로 사용하시면 됩니다.   

[포트포워딩 할 포트]로는 본인이 원하시는 임의의 4-5자리 숫자를 입력하시면 됩니다. ex) 2456, 84322   
후에 jupyter lab 연결할 때와 같이 브라우저에서 열어야 하는 프로그램이 있을 경우 브라우저에 

```
localhost:[포트포워딩할 포트]
```
를 입력하시면 됩니다.


예시: 
```
C:\Users\starl>ssh -L 1234:localhost:1234 -L 5678:localhost:5678 user@12.34.56.789 -p 12345
```

```
localhost:1234
```
        
        

 
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
### Password Change   
반드시 기본 비밀번호에서 변경 부탁드립니다
```bash
[bible2@host1 bible2]$ passwd
Changing password for user bible2.
Changing password for bible2
(current) UNIX password:  (기존의 패스워드입력)
New password: (새로운 패스워드 입력)
Retype new password: (새로운 패스워드 재입력)
passwd: all authentication tokens updated successfully.
[bible2@host1 bible2]$
```

---
## Pyenv Guide
### pyenv 실행
- pyenv : 관리자 권한(root)없이 원하는 python 버전을 사용하기 위한 도구   
- pyenv-virtualenv : 격리된 파이썬 실행환경을 만들어줌. 패키지 사이의 충동을 막을수 있고, 전역 환경에 불필요한 패키지를 설치하지 않아도 됨. - 여러명이서 서버를 사용하기 위하여 반드시 필요한 환경.    
- [pyenv virtualenv 설명](http://guswnsxodlf.github.io/pyenv-virtualenv-autoenv)
- [pyenv 설명](https://velog.io/@ssseungzz7/pyenv%EC%99%80-pyenv-virtualenv%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%9C-%ED%8C%8C%EC%9D%B4%EC%8D%AC-%EA%B0%9C%EB%B0%9C-%ED%99%98%EA%B2%BD-%EA%B5%AC%EC%84%B1%ED%95%98%EA%B8%B0-p3k15vjigb)   
- **서버를 공유해서 사용하는 것이기 때문에 pyenv-virtualenv 밖에서 작업하지 않도록 주의해주시길 바랍니다. 개발환경을 바꾸시면 공용 서버라서 다시 설정하는데 어려움이 존재할 수 있습니다.**

1. virtualenv 목록 확인
```bash
$ pyenv virtualenvs
```
처음 계정이 주어졌을 때 default virtualenv로 kubig-venv를 만들어놓았습니다.   
이 virtualenv를 사용하셔도 좋고, 원하시면 본인이 추가적으로 만드시면 됩니다.  

2. virtualenv 진입
```bash
$ pyenv activate [venv 이름]
```

예시
```
$ pyenv activate kubig-venv
```

성공적으로 실행되었다면 아래와 같이 실행될 것입니다.
```
(kubig-venv) [username]@[server name]:~$
```


3. 사용
```bash
(kubig-venv) [username]@[server name]:~$ pip3 install jupyterlab
(kubig-venv) [username]@[server name]:~$ pip3 install sklearn
```

4. jupyter lab 실행
```
 (kubig-venv) [username]@[server name]:~$ jupyter lab --ip=0.0.0.0 --port=[포트포워딩한 포트] --NotebookApp.token='' --allow-root
```

5. virtualenv 벗어나기
```
(kubig-venv) [username]@[server name]:~$ pyenv deactivate
```

**꼭 이 virtualenv 안에서 작업 부탁드립니다.**   
**혹시 개별 유저들의 virtualenv 밖에서의 작업을 제한할 수 있는 방법을 아시는 분은 연락주시면 감사하겠습니다.**


### 새로운 virtualenv 만들기

1. virtualenv 만들기
```
$ pyenv virtualenv my-first-venv
```

2. virtualenv 목록 확인
```
$ pyenv virtualenvs
```

3. virtualenv 진입
```bash
$ pyenv activate [venv 이름]
```
---
## Error

### 1. pyenv: command not found
run following commands   
```bash
$ export PATH="~/.pyenv/bin:$PATH"
$ eval "$(pyenv init -)"
```

### 2. pip install 속도가 느린 경우
pip.conf 파일에 미러 서버가 미설정 되어있는 문제입니다.     
아래 command를 치시면 해결됩니다.     
ubuntu 계정의 pip.conf 에 있는 정상적인 미러 서버를 copy하는 command입니다.   
```bash
$ cp -r /home/ubuntu/.pip  /home/[username]
```

---

## 사용량 모니터링
```bash
# gpu
watch -n 1 -d nvidia-smi
# cpu, ram
htop
```
---

## Contact
admin:    
- 송예은, yeeunsong1019@gmail.com   
- 유현우, hyeon95y@gmail.com    


---
## Server Guide for Administrators

서버 관리자용 가이드   
- [서버 관리자용 wiki 링크](https://github.com/KU-BIG/nipa-connection-guide/wiki)
