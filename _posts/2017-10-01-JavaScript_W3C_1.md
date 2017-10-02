---
layout : post
title : "[JavaScript] W3C JavaScript (1)"
subtitle : "[JavaScript] JavaScript 소개"
categories : Development
tags : JavaScript
comments : ture

---

# JavaScript 소개

> 이 포스트는 자습을 목적으로 [W3C school JavaScript](https://www.w3schools.com/js/default.asp)의 내용을 토대로 작성되었습니다.


_ _ _


### JavaScript Tutorial

1. 자바스크립트는 Web과 HTML의 프로그래밍적인 언어이다.
2. 자바스크립트는 배우기 쉽다.
3. 이 튜토리얼은 기본에서 고급까지 JavaScript를 가르쳐 줄 것입니다.

### 왜 JavaScript를 배우는가?

자바스크립트는 웹 개발자가 반드시 배워야할 3대 언어 중 하나 입니다.
1. HTML은 웹 페이지의 컨텐츠를 정의합니다.
2. CSS는 웹 페이지의 레이아웃을 특별하게 합니다.
3. JavaScript는 웹 페이지의 동작을 프로그래밍 합니다.

이 튜토이얼은 자바스크립트에 관한 것이며, 자바스크립트가 HTML, CSS와 어떻게 작동하는지를 알아봅니다.

#### JavaScript와 Java는 다른 언어!
JavaScript와 Java는 컨셉과 설계가 완전히 다른 언어 입니다.
JavaScript는 1995년 Brendan Eich에 의해 만들어 졌으며, 1997년에 ECMA에서 표준화되었습니다.

### JavaScript은 HTML 컨텐츠를 바꿀 수 있다.

JavaScript HTML 메소드 중 하나인 `getEleementByID()`입니다.
이 예제는 위의 메소드를 사용하여 HTML의 요소(id="demo")를 찾고 그 요소의 컨텐츠를 `.innerHTML`을 사용하여 "Hello JavaScript"로 변환합니다.
이 때, JavaScript는 큰 따옴표와 작은 따옴표 모두 허용합니다.

**Example**
```
!<DOCTYPE HTML>
<html>
	<body>
    	<h2>What Can JavaScript Do?</h2>
	    <p id="demo">JavaScript can change HTML content.</p>
		<button type="button" onclick='document.getElementById("demo").innerHTML = "Hello JavaScript!"'>Click Me!</button>
	</body>
</html>
```
JavaScript can change HTML content. 가  Hello JavaScript! 로 변하는 것을 볼 수 있습니다.

###JavaScript는 HTML 속성을 변경할 수도 있습니다.
이 예제는 `.src` 메소드를 사용하여 HTML의 이미지를 변경하는 것입니다.

**Example**
```
<!DOCTYPE html>
<html>
	<body>
		<h2>What Can JavaScript Do?</h2>
		<p>JavaScript can change HTML attributes.</p>
		<p>In this case JavaScript changes the src (source) attribute of an image.</p>
		<button onclick="document.getElementById('myImage').src='pic_bulbon.gif'">Turn on the light</button>
		<img id="myImage" src="pic_bulboff.gif" style="width:100px">
		<button onclick="document.getElementById('myImage').src='pic_bulboff.gif'">Turn off the light</button>
	</body>
</html>
```
사진의 이미지가 바뀌는 것을 볼 수 있습니다.

### JavaSciprt는 CSS를 변경할 수 있습니다.
HTML 요소의 style을 변경하여, 속성들을 사양하게 변화시킬 수 있습니다.

**Example**
```
<!DOCTYPE html>
<html>
	<body>
        <h2>What Can JavaScript Do?</h2>
        <p id="demo">JavaScript can change the style of an HTML element.</p>
		<button type="button" onclick="document.getElementById('demo').style.fontSize='35px'">Click Me!</button>
	</body>
</html>
```
글씨의 크기가 커지는 것을 볼 수 있습니다.

### JavaScirpt는 HTML 요소를 숨기거나 보이게 할 수 있습니다.

**Example**
```
<!DOCTYPE html>
<html>
    <body>
        <h2>What Can JavaScript Do?</h2>
        <p>JavaScript can show hidden HTML elements.</p>
        <p id="demo">Hello JavaScript!</p>
        <button type="button" onclick="document.getElementById('demo').style.display='none'">Hide!</button>
        <button type="button" onclick="document.getElementById('demo').style.display='block'">Show!</button>
    </body>
</html>
```
