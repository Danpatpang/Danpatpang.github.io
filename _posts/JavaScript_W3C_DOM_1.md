---
layout : post
title : "[JavaScript] JS HTML DOM(1)"
subtitle : "[JavaScript] JavaScript HTML DOM"
categories : Development
tags : JavaScript
comments : true

---

# JavaScript HTML DOM

> 이 포스트는 자습을 목적으로 [W3C school JavaScript](https://www.w3schools.com/js/default.asp)의 내용을 토대로 작성되었습니다.

_ _ _
HTML DOM을 사용하면, JavaScript가 HTML 문서의 모든 태그에 접근하여 정보를 변경할 수 있습니다.

### The HTML DOM (Document Object Model)

웹 페이지를 로딩할 때, 브라우저는 페이지의 `Document Object Model`을 만듭니다.
HTML DOM 모델은 객체의 트리로 구성되어 있습니다.

![HTML DOM Tree](https://www.w3schools.com/js/pic_htmltree.gif)

객체 모델을 사용하여, JavaScript는 동적인 HTML을 만드는데 필요한 기능들을 제공합니다.<br>
다음은 JavaScript HTML DOM의 특징입니다.

+ JavaScript는 페이지 안의 모든 HTML 태그들을 변경할 수 있습니다.
+ JavaScript는 페이지 안의 모든 HTML 속성들을 변경할 수 있습니다.
+ JavaScript는 페이지 안의 모든 CSS style을 변경할 수 있습니다.
+ JavaScript는 HTML의 태그와 속성을 제거할 수 있습니다.
+ JavaScript는 HTML의 태그와 속성을 새롭게 추가할 수 있습니다.
+ JavaScript는 페이지 안의 이벤트 발생 시 반응할 수 있습니다.
+ JavaScript는 페이지 안에서 새로운 HTML 이벤트를 만들 수 있습니다.

### What You Will Learn

+ HTML 태그의 내용을 바꾸는 방법
+ HTML 태그의 style(CSS)를 바꾸는 방법
+ HTML DOM 이벤트에 반응하는 방법
+ HTML 태그를 추가하거나 삭제하는 방법

### What is the DOM?

DOM은 W3C(World wide Web Consortium) 표준입니다. DOM은 문서에 접근하기 위한 표준을 정의합니다.

> "The W3C Document Object Model (DOM) is a platform and language-neutral interface that allows programs and scripts to dynamically access and update the content, structure, and style of a document."<br>
> "W3C DOM은 프로그램 및 스크립트가 문서의 내용, 구조, 스타일 등을 동적으로 접근하고 업데이트 할 수 있게 해주는 플랫폼 및 언어-중립적 인터페이스입니다."

W3C DOM 표준은 3가지의 파트로 분리되어 있습니다.

1. **Core Dom** - 모든 문서 타입의 표준 모델
2. **XML DOM** - MXL 문서의 표준 모델
3. **HTML DOM** - HTML 문서의 표준 모델

### What is the HTML DOM?

HTML DOM은 HTML에 대한 표준 객체 모델이고 프로그래밍 인터페이스 입니다.
HTML DOM은 다음과 같이 정의됩니다.

+ 객체로서의 HTML 태그
+ 모든 HTML 태그의 속성
+ HTML 태그에 접근하기 위한 method
+ 모든 HTML 태그를 위한 이벤트

즉, HTML DOM은 HTML 태그를 받거나, 변경하거나, 추가하거,나 삭제하는 방법의 표준 입니다.