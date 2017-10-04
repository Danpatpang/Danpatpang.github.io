---
layout : post
title : "[Django] 앱 만들기"
subtitle : "[Django] 앱 만들기"
categories : Development
tags : Django
comments : true

---

# Django 앱 만들기

이전 포스트에서는 프로젝트를 만드는 방법에 대해서 알아보았습니다.
이번에는 프로젝트 내부의 앱을 만들어 보겠습니다.

### Project vs App

App은 (블로그, 공공 기록물을 위한 데이터베이스, 설문조사 등) 특정한 기능을 수행하는 웹 어플리케이션을 말합니다. 프로젝트는 이런 특정 웹 사이트를 위한 App들과 설정들을 한 곳에 묶어서 관리하는 것입니다. 프로젝트는 다수의 App을 포함할 수 있고, App은 다수의 프로젝트에 포함될 수 있습니다.

App은 Python경로 어디에 있어도 상관없지만, import의 편의를 위해 프로젝트 안에서 생성해 보겠습니다.
cmd창을 실행합니다.
```
cmd
cd Desktop
cd Bookstore
python manage.py startapp polls
```

저는 Bookstore 프로젝트가 바탕화면에 있으므로 위와 같이 실행했고, 본인이 만들었던 프로젝트 내부에서 `python manage.py startapp (appName)`을 입력하면 됩니다.

그러면 polls라는 디렉토리가 생겼고 내부는 아래와 같이 구성되어 있습니다.
```
polls/
	__init__.py
    admin.py
    apps.py
    migrations/
    	__init__.py
    models.py
    tests.py
    views.py
```
기존의 프로젝트와 비슷한 파일들이 생성된 것을 확인할 수 있습니다.

### view 작성하기

`polls/view.py` 파일을 연 후, 다음과 같이 작성합니다.
```
from django.http import HttpResponse

def index(request):
	return HttpResponse("My first App")
```
`from (moduleName) import (moduleFunction)`는 `django.http`라는 모듈에서 `HttpResponse`라는 함수를 사용하겠다는 것입니다.
`HttpResponse`는 웹 서버에서 클라이언트에게 응답하는 함수입니다.

view를 호출하기 위해서는 이와 연결된 `URL`이 있어야 하는데, 이를 위해 `URLconf`가 사용됩니다.
polls 디렉토리에 `URLconf`를 생성하기 위해, `urls.py`파일을 생성합니다.
(polls 내부에 `urls.py`가 없으므로 `notepad`, `idle`, `tool` 등을 이용해서 만들어주시면 됩니다.)

`polls/urls.py`를 작성해보겠습니다.
```
from django.conf.urls import url
from . import views

urlpatterns = [
	url(r'^$', views.index, name='index')
]
```
다음은, 프로젝트와 App의 url의 모듈을 연결시켜보겠습니다.
Bookstore 프로젝트의 `Bookstore/urls.py`를 작성합니다.
```
from django.conf.urls import include, url
from django.contrib import admin

urlpatterns = [
	url(r'^polls/', include('polls/urls')),
    url(r'^admin/', admin.site.urls),
]
```
`url`은 `URLconf`를 사용하는 것이라 생각하면 됩니다.
`urlpatterns` 리스트 안에 url들을 저장합니다.
`url`함수는 `(regex, view, kwargs, name)`으로 이루어져 있습니다.
`include()` 함수는 다른 `URLconf`를 참조할 수 있도록 도와주며, `admin.site.urls`를 제외한, 다른 `URL` 패턴을 `include`할 때마다 항상 사용해야 합니다.

이제, `python manage.py runserver`를 입력하여 서버를 실행합니다.
브라우저에서 http://localhost:8000/polls를 입력하면 작성했던 `view`를 볼 수 있습니다.


_ _ _

### URL의 argument

`url`함수는 `(regex, view, kwargs, name)`으로 이루어져 있습니다.
위의 작성한 코드가 어떤 의미인지 다시 해석해보겠습니다.

#### regex

`regex`는 정규 표현식("Regular Expression")을 짧게 줄여 쓰는 표현입니다. 문자열의 패턴을 일치시키는 문법을 말하며, url의 패턴을 찾는 데에 사용되었습니다. Django에서는 리스트의 순서대로 요청된 URL에 대해 일치하는 표현식이 발견 될 때까지 차례로 비교합니다.

단, 이 정규식이 매개변수나 도메인 이름을 조사하지는 않습니다.
예를 들어, `http://localhost/polls/`가 요청된 경우, `URLconf`는 `polls/` 부분만 바라보고 `http://localhost/polls/?page=2` 같은 요청에도, `polls/`부분만 바라보고 있습니다.
정규 표현식은 [Wikipedia's entry](https://en.wikipedia.org/wiki/Regular_expression)를 참고하시기 바랍니다.

> 정규 표현식은 모든 내용을 전부 알아야 할 필요가 없습니다.
> 또한, 복잡한 정규 표현식을 사용하면 검색 속도가 느려짐에 주의해야 합니다.
> 그럼에도, 정규 표현식을 사용하는 이유는 단순하다면 굉장히 빠른 속도로 컴파일됩니다.

#### view

Django에서 일치하는 정규 표현식을 찾아내면, `HttpRequset`객체가 첫번째 인자, 같이 넘어온 값들이 나머지 인수로 특정 `view`를 호출합니다.

#### kwargs

임의의 키워드 인수들을 목표한 view에 dictionary형으로 전달합니다.

#### name

URL에 이름을 지으면, 템플릿을 포함한 Django 어디에서든 명확하게 참조할 수 있습니다. 이 기능을 이용하여, 하나의 파일을 수정해도 project내의 모든 URL패턴을 바꿀 수 있도록 도와줍니다.

> 정규표현식에 관한 내용은 다른 포스트에서 한 번 더 다루도록 하겠습니다.
