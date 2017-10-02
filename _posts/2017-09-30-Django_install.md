---
layout : post
title : "[Django] Django 설치 및 프로젝트 생성"
subtitle : "[Django] Django 설치 및 프로젝트 생성"
categories : Development
tags : Django
comments : true

---

# Django 설치하기

[Django 다운로드](https://www.djangoproject.com/download/)
#### 1. command창에 입력
###### `pip install Django==1.11.5 `
command창에서 Django를 설치한다.
#### 2. install 확인
`python -m django --version`
  	설치가 끝나면 다음과 같이 입력 후 Django가 설치되었는지 확인한다.
#### 3. project 생성
 `cd Desktop`
 `django-admin startproject Bookstore`
 Desktop으로 이동 후 Bookstore(프로젝트 이름)의 프로젝트를 생성한다. 
 참고로, 프로젝트 이름을 test, django로 할 시, 후에 충돌이 일어날 가능성이 크므로 다른 이름을 사용하는 것이 좋다.
 #### 4. project 내부 확인
 프로젝트가 성공적으로 만들어졌다면 다음과 같은 디렉토리를 볼 수 있다.
 ```
 Bookstore/
	manage.py
    Bookstore/
    	__init__.py
        settings.py
        urls.py
        wsgi.py
 ```
 먼저 Bookstore 디렉토리 안에 manage.py와 또 다른 Bookstore 디렉토리가 생성된다.
 `manage.py`는 Django project와 다양한 방법으로 상호작용하는 command라인의 utility다.
 Bookstore 디렉토리는 project를 위한 실제 python 패키지들이 저장된다. 즉, `Bookstore.urls`와 같은 식으로 project 어디서나 패키지를 import할 수 있다.
 `__init__.py`는 디렉토리를 패키지 처럼 다루라고 알려주는 용도의 단순한 빈 파일이다.
 `settings.py`는 현재 프로젝트의 환경, 구성을 저장한다.
 `urls.py`는 프로젝트의 URL 선언을 저장한다.
 `wsgi.py`는 프로젝트를 서비스 하기 위한 WSGI호환 웹 서버의 진입점이다.
 **
 WSGI는 Web Server Gateway Interface로 웹서버와 웹 어플리케이션의 인터페이스를 위한 python 프레임워크다.
 **

#### 5. 서버 실행
```
cd Bookstore
python manage.py runserver
```
서버를 실행하기 위해 프로젝트 안에서 `manage.py`를 실행시킨다.
Web browser에 (http://127.0.0.1:8000)을 실행시키면 
```
It worked!
Congratulations on your first Django-powered page.
```
라는 구문을 볼 수 있는데 여기까지 왔다면 서버를 실행 시키는데 성공한 것이다.
서버를 끄고 싶을 경우 cmd창에서 ctrl+c를 누르면 된다.

또한, :8000은 8000번 포트로 접속한 것인데 포트번호를 바꾸고 싶다면 `python manage.py runserver 8080`으로 서버를 연 후, 8080번으로 접속해도 상관없다.
