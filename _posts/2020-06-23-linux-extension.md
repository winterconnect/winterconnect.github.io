---
layout: post
title: "[Ubuntu]리눅스의 계열과 압축"
---



### 1. 리눅스 계열
리눅스는 2가지 분류(계열)로 나뉘어져 있다.



#### 1) 데비안(Debian) 계열 리눅스
- 데비안이라는 이름을 따서 운영체제 패키지가 배포될 때 deb 확장자를 씀 (대표적: ubuntu 리눅스)
- 인공지능이 부각되면서 우분투를 많이 쓰게 됨



#### 2) 레드햇(Redhat) 계열 리눅스
- 대표적: Redhat 리눅스, Centos(기업용으로 많이 쓰여짐)레드햇






### 2. 리눅스 압축
#### 1) tar
- tar 명령어: 한 개의 파일로 묶음  (.tar 파일이 생성됨)
~~~shell
$ tar xvf xxx.tar
~~~


- tar c : 묶음파일 생성
- tar x : 묶음파일 해제(파일을 풀어라)
- tar v: 내용을 자세히 보여줘라
- tar f: 파일을 저장하라



- 한번에 하는 방법(gz를 자동으로 풀어줌)

~~~shell
$ tar xvfz xxx.tar.gz
~~~






#### 2) gzip
- gzip 명령어: 한 개의 파일을 압축 (.tar.gz 파일이 생성됨)
- gzip : 압축
- gzip –d : 압축해제

~~~shell
$gzip –d xxx.tar.gzxxx.tar
~~~


