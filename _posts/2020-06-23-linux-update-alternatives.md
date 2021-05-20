---
layout: post
title: "[Ubuntu]동일한 명령어의 버전별 관리"
---



### 1. 버전별 관리: update-alternatives

> - 동일한 명령어가 여러 개 있을 때 버전을 선택할 수 있는 체계를 만듦
> - 중요한 명령어
> - 동일한 명령어가 여러군데 있을 때, 쓰고자 하는 명령어를 설정해줄 수 있음
> - install 로 등록하고 config로 지정



#### 1) update-alternatives --install

~~~shell
$update-alternatives: --install needs <link> <name> <path> <priority>
~~~

- \<link> : 바로가기링크
- \<name> : 바로가기이름
- \<path> : 실제 파일의 경로
- \<link>와 \<name>을 동일하게 설정 (관리상 용이)

~~~shell
$ sudo update-alternatives --install /usr/bin/java java /usr/lib/jvm/jdk-11.0.7/bin/java 1 
~~~

~~~shell
$ sudo update-alternatives --install /usr/bin/javac javac /usr/lib/jvm/jdk-11.0.7/bin/javac 1 
~~~

- /usr/bin:  디폴트로 path에 들어가 있으므로 이곳에 넣으면 편함

바로가기를 바꿔줄 수 있다.



#### 2) update-alternatives --config

> 버전을 바꿔보자!

~~~shell
$sudo update-alternatives --config java
~~~

- 마치 윈도우의 바로가기처럼 실행파일의 경로를 정해준다

