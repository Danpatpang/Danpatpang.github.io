---
layout : post
title : "[Tip] Ubuntu 폴더 구조 및 핵심 명령어 (3)"
subtitle : "우분투의 핵심 명령어"
categories : Tip
tags : Tip
comments : true

---

# 우분투의 핵심 명령어

> 이 포스트는 자습을 목적으로 [DaddyMarkes](http://daddynkidsmakers.blogspot.kr/2018/), [pxd UX Lab](http://story.pxd.co.kr/732), [webdir](http://webdir.tistory.com/101)의 포스팅을 참고하여 작성하였습니다.

_ _ _

###### 우분투의 핵심 명령어들을 이해하기 위해서 우분투가 무엇인지, 우분투의 파일 구조는 어떻게 이루어져 있는지를 알아봤다. 이번 포스팅은 우분투의 파일구조와 핵심 명령어에 대한 마지막 포스팅으로 우분투와 좀 더 친해졌으면 하는 마음으로 작성하겠다.

### 우분투의 핵심 명령어

![ubuntu](http://Danpatpang.github.io/assets/img/Ubuntu/ubuntu.png)

윈도우만 사용하다가 우분투로 넘어오게 되니 `tar.xz` 파일부터 `chmod`, `sudo` 등 생소한 명령어들을 만나게 되었다. 다른 분들의 포스트들을 보면서 자주 봤던 명령어들에 대해 알아가 보려고 한다.

| 명령어(command) | 설명(Explanation) |
|---|---|
| ps | 프로세스 리스트 |
| df -h | 디스크 마운트 정보 확인 |
| alias | 명령어 간소화 |
| apropos | 관련된 명령어 찾기 |
| arch | 컴퓨터 종류 알아보기 |
| at | 작업시간 정하기 |
| bc | 계산기 |
| break | 루프 빠져나가기 |
| cal | 달력보기 |
| cat | 화면상에서 파일 보기 |
| cd | 디렉토리 변경하기 |
| cfdisk | 디스크 설정하기 |
| chfn | 사용자 정보 변경하기 |
| chgrp | 파일, 디렉토리가 속했던 그룹 바꾸기 |
| chmod | 파일 권한 바꾸기 |
| chown | 파일 주인 바꾸기 |
| clear | 화면 청소하기 |
| clock | CMOS 시각을 조정하기 |
| column | 가로 정렬하기 |
| command | 명령어 알아보기 |
| cpio | 복사본 만들기 |
| date | 날짜 보기 |
| dd | 블럭장치 읽고 쓰기 |
| declare | 변수 선언하기 |
| df | 파일 시스템의 사용량 보기 |
| du | 디렉토리와 파일의 용량 파악하기 |
| echo | 표준 출력하기 |
| env | 환경변수 출력하기 |
| exec | 셸 명령어 실행하기 |
| exit | 종료하기 |
| export | 변수 지정하기 |
| file | 파일 종류보기 |
| find | 파일 찾기 |
| free | 메모리 사용량 알아보기 |
| grep | 특정 문자(열) 검색하기 |
| gzip | 압축하기 |
| halt | 시스템 종료하기 |
| help | 도움말 보여주기 |
| host | 호스트 정보 보기 |
| history | 사용 명령어 목록보기 |
| id | 계정 정보 알기 |
| ifconfig | 랜카드에 주소 할당하기 |
| init | 실행 단계 정하기 |
| kill | 프로세스 강제로 죽이기 |
| look | 특정 단어 검색하기 |
| ls | 디렉토리 내용보기 |
| make | 컴파일 하기 |
| man | 메뉴얼 보기 |
| mkdir | 디렉토리 생성 |
| mv | 파일 옮기기 |
| ping | 네트워크 확인하기 |
| pwd | 절대경로 보여주기 |
| quota | 디스크 한계량 알기 |
| reboot | 재부팅 하기 |
| rm | 파일 지우기 |
| rmdir | 디렉토리 지우기 |
| rpm | 프로그램 추가/제거 |
| shutdown | 전원 끄기 |
| sleep | 절전 모드 |
| source | 스크립트 번역하기 |
| ssh | 암호화된 원격 로그인하기 |
| su | 계정 바꾸기 |
| tar | 파일 묶기 |
| unalias | 별명 제거하기 |
| who | 사용자 정보 알기 |

##### `ps`와 `tar`은 내가 우분투 초기에 가장 많이 만났던 명령어다. 아래에서는 위 두개의 명령어에 대해 좀 더 상세히 알아보겠다.

### ps

| 명령어(command) | 설명(Explanation) |
|---|---|
| ps | 실행 중인 프로세스 보기 |
| pstree -p | 더 많은 정보를 가진 프로세스를 tree 형태로 보기 |
| ps -ef | 현재 실행중인 프로세스들의 자원, 파일, ip 등 보기 |
| kill -9 pid | pid(process id)가 9번인 프로세스를 강제 종료 |
| `ps aux | grep chrome`  | 원하는 프로세스를 검색할 때 사용 |

![ps1](http://Danpatpang.github.io/assets/img/Ubuntu/ps1.png)

![ps2](http://Danpatpang.github.io/assets/img/Ubuntu/ps2.png)

![ps3](http://Danpatpang.github.io/assets/img/Ubuntu/ps3.png)

### tar

| 명령어(command) | 설명(Explanation) |
|---|---|
| `tar -cvf [a.tar] [b]` | b라는 폴더를 a.tar로 압축하기 |
| `tar -xvf [a.tar]` | a.tar라는 tar파일 압축풀기 |
| `tar -zcvf [a.tar.gz] [b]` | b라는 폴더를 a.tar.gz로 압축하기 |
| `tar -zxvf [a.tar.gz]` | a.tar.gz로 압축하기 |

![tar](http://Danpatpang.github.io/assets/img/Ubuntu/tar.png)


##### 지금까지 우분투에 대해서 기초적인 것들을 알아보았다. 아직 배워야 할 내용도 많고 개발해 나가야 할 부분도 많다. 설명이 많이 빈약하지만 우분투를 처음 접하는 사람들에게 조금이나마 도움이 되었으면 좋겠다. 평소 오픈 소스에 관심이 많은 나에게는 다시 한 번 리눅스라는 커다란 프로젝트에 대해 실감하게되는 경험이 되었던 것 같다.

##### 지금까지 읽어주셔서 감사합니다 :)

###### 출처 <br/>
[DaddyMarkes](http://daddynkidsmakers.blogspot.kr/2018/)<br/>
[pxd UX Lab](http://story.pxd.co.kr/732)<br/>
[Wiki](https://en.wikipedia.org/wiki/Ubuntu)<br/>
[Naver](http://terms.naver.com/entry.nhn?docId=1180044&cid=40942&categoryId=32839)<br/>
[webdir](http://webdir.tistory.com/101)