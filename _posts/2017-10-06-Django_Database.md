---
layout : post
title : "[Django] Django Database 연동"
subtitle : "[Django] Django Database 연동"
categories : Development
tags : Django
comments : true

---

지금부터 데이터베이스와 모델을 만들고 자동으로 생성된 관리자 페이지에 대해 소개하겠습니다.

### Database setup

`Bookstore/settings.py`를 엽니다. 이 파일은 Django 설정을 나타내는 모듈레벨 변수가 있는 일반적인 파이썬 모듈입니다.<br>
기본적으로 `SQLite`를 사용하겠습니다. `SQLite`는 Python에 포함되어 있으므로 다른 것을 따로 설치할 필요는 없습니다. 그러나 다른 프로젝트를 진행할 때는 확장성이 뛰어난 데이터베이스를 사용하는 것이 좋습니다.
다른 데이터베이스를 사용하려면 적절한 [데이터베이스 바인딩](https://docs.djangoproject.com/en/1.11/topics/install/#database-installation)을 설치하고 연결 설정과 일치하도록 다음의 키를 변경해야 합니다.
```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
    }
}
```
`ENGINE`은 어떤 종류의 백엔드를 사용할지 정합니다. `NAME`은 데이터 베이스의 이름으로 `SQLite`를 사용하는 경우 데이터베이스는 컴퓨터의 파일이됩니다. `SQLite`를 사용하지 않을 경우 USER, PASSWORD, HOST를 추가해야 합니다. 자세한 내용은 [DATABASES](https://docs.djangoproject.com/en/1.11/ref/settings/#std:setting-DATABASES)를 참고해주세요.

`settings.py`에서는 `TIME_ZONE`을 설정할 수 있습니다.
```
LANGUAGE_CODE = 'ko-kr'
TIME_ZONE = 'Asia/Seoul'
```
`INSTALLED_APPS`는 Django 인스턴스에서 활성화 된 모든 장고 응용프로그램의 이름이 들어있습니다.
```
# Application definition
INSTALLED_APPS = [
    'django.contrib.admin',				# 관리 사이트
    'django.contrib.auth',				# 인증 시스템
    'django.contrib.contenttypes',		# 콘텐츠 유형을위한 프레임 워크
    'django.contrib.sessions',			# 세션 프레임 워크
    'django.contrib.messages',			# 메시징 프레임 워크
    'django.contrib.staticfiles',		# 정적 파일을 관리하기 위한 프레임 워크
    'polls.apps.PollsConfig'			# 앱 추가
]
```
이러한 응용프로그램은 일반적으로 편의를 위해 Default되어 있습니다.
필요없는 앱은 `#`으로 주석 처리하여도 상관없습니다.
응용프로그램 중 일부는 최소한 하나의 데이터베이스 테이블을 사용하므로 데이터베이스를 사용하기 전에 테이블을 생성해야 합니다. cmd 창에서 다음과 같이 입력합니다.
```
python manage.py migrate
```
`migrate` 명령은 INSTALLED_APPS설정을 확인하고 데이터베이스 설정 및 앱과 함께 제공되는 데이터베이스 마이그레이션에 따라 필요한 데이터베이스 테이블을 만듭니다.

### Creating models

이제 데이터베이스 레이아웃과 추가 메타 데이터 등을 정의 합니다.
> 모델은 데이터에 대한 진실의 근원입니다.<br>
> 여기에는 저장중인 데이터의 필드와 동작이 포함되어 있습니다.<br>
> 장고는 DRY원리를 따르며, 목표는 데이터 모델을 한 곳에 정의하여 자동으로 데이터 모델을 파생시키는 것입니다.

우리는 `Question`과 `Choice`라는 2가지 모델을 만들 것입니다.
`Question`에는 질문과 게시한 날짜가 있습니다.
`Choice`에는 텍스트와 투표 집계표라는 필드가 있습니다.

지금부터 `polls/models.py`에서 모델을 편집해 보겠습니다.
```
from django.db import models

# Create your models here.
class Question(models.Model):
    question_text = models.CharField(max_length=200)
    pub_date = models.DateTimeField('date published')

class Choice(models.Model):
    question = models.ForeignKey(Question, on_delete=models.CASCADE)
    choice_text = models.CharField(max_length=200)
    votes = models.IntegerField(default=0)
```
각 모델은 서브클래스인 `django.db.models.Model`로 표현됩니다.
각 모델들은 여러 개의 클래스 변수가 있으며, 각 클래스 변수는 모델의 데이터베이스 필드를 나타냅니다.
각 필드는 `Field`클래스의 인스턴스(`CharField`, `DateTimeField` 등)로 표시되며, Django는 각 필드에 어떤 데이터 유형이 있는지 알려줍니다.
`question_text`와 `pub_name`은 `Field`의 인스턴스 이름으로, 파이썬 코드에서 이 값을 변수를 사용하면 데이터베이스에서 이 값을 열 이름으로 사용합니다.
일부 Field에서는 `max_length`, `default`를 사용하여 인수에 속성을 주먀, 이것은 데이터베이스의 스키마 뿐만 아니라 유효성 검사에도 사용됩니다.
`ForeignKey`는 장고가 Question이 각각의 Choice와 관련이 있다고 말해줍니다. 즉, Django는 다 대 다, 다 대 일, 일 대 일 등 모든 공통 데이터베이스 관계를 지원합니다.

### Activating models

작은 모델 코드들은 Djnago에게 많은 정보를 제공합니다. 이와 함께 Django는 App을 위해 데이터베이스의 `scheme`를 만들거나 객체들의 접근을 위해 Python 접근 API를 만듭니다. 우리는 먼저 우리의 프로젝트에 `polls` App을 설치해야 합니다.
>  Django App들은 플러그형입니다. 즉, 여러 프로젝트에서 사용 가능합니다.

놓친 분들을 위해, `Bookstore/settings.py`의 `INSTALLED_APPS`에 `polls` APP을 추가합니다.
```
# Application definition
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'polls.apps.PollsConfig',		# APP 추가
]
```

이후, cmd창에서 `python manage.py makegirations polls`를 입력합니다.
실행 결과로 `Choice`, `Question` 모델이 생성된 것을 볼 수 있습니다.

`makemigrations`명령은 Djnago에게 모델의 몇 가지 사항이 변경되고, `migration`에 변경된 사항을 저장합니다.
`migration`은 Djnago가 모델에 변경 사항을 저장하는 방법이며, 디스크에 있는 파일입니다. `migrate`는 `migration`을 수행하고 데이터베이스 스키마를 자동으로 관리하는 명령입니다. `sqlmigrate`는 `migration`의 이름을 사용하여, `SQL문`을 반환합니다.

```
python manage.py sqlmigrate polls 0001		# 실행
```
결과로써 SQL문을 확인할 수 있습니다.
+ 정확한 출력은 사용중인 데이터베이스에 따릅니다.
+ 기본키 (ID)는 자동으로 추가됩니다.
+ 외부 키와의 관계는 제약 조건에 의해 명시적으로 지정됩니다.
+ `sqlmigrate`명령은 실제로 데이터베이스 `migration`을 실행하는 것은 아닙니다. Djnago가 할 일을 확인하거나 변경을 위해 화면에 출력하는 역할만 합니다.

이제 `migrate`를 실행하여 데이터베이스에 모델 테이블을 재작성합니다.
```
python manage.py migrate
```
즉, `migrate`명령은 적용되지 않은 모든 `migration`을 Djnago 데이터베이스에 대해 실행합니다. `migration`은 데이터베이스의 테이블을 삭제하거나 만들 필요없이 프로젝트를 개발할 때마다 모델을 변경할 수 있습니다. 즉, 모델 변경 3단계를 기억하면 됩니다.
1. 모델의 변경(models.py)
2. 변경 사항에 대한 `migration` 실행 `python manage.py migrations`
3. 변경 사항을 데이터베이스에 적용 `python manage.py migrate`

`migrations`와 `migrate`가 분리된 이유는 버전 관리 시스템을 이유로 개발자가 쉽게 개발할 수 있을 뿐만 아니라 다른 개발자와 같이 사용하기 위해서 입니다.

###API로 재생하기
