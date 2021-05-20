---
layout: post
title: "[Ubuntu]우분투 명령어 목록"
categories: Linux
---





## [Ubuntu] 명령어 목록



### 1. Id

> 현재 로그인 한 계정에 대한 정보 출력

~~~shell
$id
uid=1000(acorn)gid=1000(acorn)groups=1000(acorn),4(adm),24(cdrom),27(sudo),30(dip),46(plugdev),116(lpadmin),126(sambashare)
~~~

- uid: user(소유자)
- gid: 그룹(소유자가 속한 그룹)
- groups: other(전혀 다른 그룹)



### 2. apt

> 우분투 리눅스의 운영체제 패키지



#### 1) 패키지 검색

~~~shell
 $sudo apt search htop
~~~

- htop: 찾고자 하는 패키지 명



#### 2) 패키지 설치

~~~shell
$sudo apt install htop
~~~

- htop: 설치할 패키지명



#### 3) 패키지 확인

~~~shell
$sudo apt list --installed htop
~~~

- htop: 확인할 패키지명
- --installed: 현재 운영체제에 설치된 것만 보여주는 옵션



#### 4) 패키지에 대한 상세한 정보 확인

~~~shell
$sudo apt show htop
~~~



#### 5) 패키지 삭제

~~~shell
$sudo apt remove <삭제할 패키지명>
$sudo apt purge <삭제할 패키지명>
~~~

- remove: 휴지통에 들어가는 기능
- purge: 완전삭제



#### 6) 패키지 업데이트(중요)

~~~shell
$sudo apt upgrade
$sudo apt upgrade <특정 패키지 업그레이드>
~~~



### 3. clear

> 터미널 화면 깨끗이 지우기



### 4. hostname

> 현재 컴퓨터의 이름을 출력



### 5. echo

> 시스템 환경변수 출력

~~~shell
echo $PS1
~~~

- PS1: 명령어 프롬프트 제어 변수



### 6. export

> 시스템 환경변수의 값 변경(설정)

~~~shell
$export PS1="[\u@\h\w]\\$"

or

$PS1="[\u@\h\w]\\$"
$export PS1
~~~

- 단, 이 환경변수는 1회용이기 때문에 다시 로그인하게 되면 이전의 환경변수값의 설정으로 돌아감
- 영속적으로 명령어 프롬프트를 변경하려면 **~/.bashrc** 에 명령어 추가
  - 모든 운영체제는 로그인하면 실행되는 프로그램이 정해져있고, bashrc 폴더는 가장 마지막으로 실행됨
  - 여기에 명령어를 추가하면 영속적으로 변경내용 저장 가능



### 7. su

> 사용자 계정 바꿈(Switch User)

~~~shell
$su root
$su – root
~~~

- '-' 이 들어가면, 계정 변경시 변경된 계정의 홈폴더로 자동 이동



### 8. exit

> 현재 계정에서 빠져나감 (logout)
>
> 단, su(switch user) 명령어로 계정을 바꾼 상태에서만 적용



### 9. history



### 10. touch

> 새로운 파일 생성(단, 크기가 0인 파일)
> 기존하는 파일에 touch하면 해당 파일의 최종 수정시간만 갱신

~~~shell
$touch ps1.sh
~~~



### 11. date

> 현재 시스템의 날짜와 시간정보 출력



### 12. more or less

> 지정한 파일의 내용을 한 페이지씩 보기

~~~shell
$more <filename>
$less <filename>
~~~



### 13. cat

> 지정한 파일의 내용을 처음부터 끝까지 한번에 모두 출력

~~~shell
$cat <filename>
~~~



### 14. grep (중요)

> 지정한 검색어를 지정된 파일에서 검색 및 출력

~~~shell
$grep oinstall /etc/group
~~~

- grep -n: 검색된 행 수도 알려줌



### 15. egrep (중요)

> 지정한 검색어를 지정된 파일에서 검색 및 출력

~~~shell
$egrep 'oinstall|dba|oper|nobody|asmadmin' /etc/group
~~~



### 16. mkdir –p <만들 디렉토리 경로>

> 지정된 디렉토리 경로대로 디렉토리를 모두 생성

~~~shell
$mkdir –p 
~~~

- -p 옵션: 지정된 디렉토리 경로 중에 없는 디렉토리는 생성하고 이미 존재하는 디렉토리는 그대로 둠



### 17. pwd

> Print Working Directory
>
> 현재 위치하고 있는 폴더의 절대경로 출력



### 18. tree

> 지정된 디렉토리의 하부구조를 트리모양으로 출력

~~~shell
$tree .
~~~



### 19. rmdir

> 지정된 디렉토리만 삭제
>
> 단, 지정된 디렉토리 안에 파일 또는 디렉토리가 존재한다면 삭제는 실패

~~~shell
$ rmdir ttt
~~~



### 20. rm –rf <디렉토리명|파일명>

> 지정된 디렉토리 또는 파일을 recursive 하게 무조건 삭제(매우 주의할 것)

~~~shell
$rm –rf ttt
~~~

- rm: remove
- -r: recursive
- -f: forcely



### 21. chown <대상사용자명 : 대상사용자그룹> <디렉토리|파일>

> Change Owner
>
> 지정된 대상 사용자와 그룹으로 지정된 디렉토리 또는 파일의 소유를 변경함

~~~shell
$ chown –R oracle:oinstall ttt
~~~



### 22. chmod

~~~
$sudo chmod –R 775 /u01
$chmod u+rwx/u+r/u–r a+rwx/a+r/a+w
~~~

- **775**의 의미
  - rwx / rwx / rwx 을 2의 지수로 표현
  - 421 / 421 421
  - 775 = rwx/rwx/r-x)



### 23. mv