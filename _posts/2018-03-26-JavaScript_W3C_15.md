---
layout : post
title : "[JavaScript] W3C JavaScript (15)"
subtitle : "[JavaScript] JavaScript의 이벤트"
categories : Development
tags : JavaScript
comments : true

---

# JavaScript Events

> 이 포스트는 자습을 목적으로 [W3C school JavaScript](https://www.w3schools.com/js/default.asp)의 내용을 토대로 작성되었습니다.

_ _ _

HTML 이벤트는 HTML 요소에 발생하는 "어떤 것" 입니다.
JavaScript가 HTML 페이지에서 사용될 때, JavaScript는 이벤트에 "반응" 할 수 있습니다.

### HTML Events

HTML 이번트는 브라우저가 수행하는 작업이거나 유저가 사용하는 작업일 수 있습니다.
여기에 몇 가지 HTML의 이벤트 예제가 있습니다.

+ HTML 웹 페이지의 로딩이 끝났을 때
+ HTML의 입력필드가 바꼈을 때
+ HTML 버튼을 클릭했을 때

종종, 이벤트가 발생했을 때, 당신은 무언가 하기를 원할 수도 있습니다.
JavaScript는 이벤트가 탐지되었을 때, 코드를 실행할 것입니다.
HTML을 사용하면 JavaScript 코드가 있는 이벤트 핸들러 속성을 HTML 요소에 추가할 수 있습니다.
<br/>
작은 따옴표 사용

```
<element event ='some JavaScript'>
```
큰 따옴표 사용

```
<element event = "some JavaScript">
```

예제에 따르면, onclick 속성은 버튼 요소에 추가되어 있습니다.

**Example**
```
<button onclick="document.getElementById('demo').innerHTML = Date()">
	The time is?
</button>
```
위의 예제에서 JavaScript 코드는 id가 "demo"인 요소의 컨텐츠가 변합니다.
다음 예제에서는 .innerHTML을 사용하여 요소의 컨텐츠를 변화시킵니다.

**Example**
```
<button onclick="this.innerHTML = Date()">
	The time is?
</button>
```
> JavaScript 코드는 종종 긴 줄로 구성됩니다. 함수를 호충하는 이벤트 속성을 보는 것이 더 흔합니다.

**Example**
```
<!DOCTYPE html>
<html>
<body>

    <p>Click the button to display the date.</p>

    <button onclick="displayDate()">The time is?</button>

    <script>
        function displayDate() {
            document.getElementById("demo").innerHTML = Date();
        }
    </script>

    <p id="demo"></p>

</body>
</html>
```

### Common HTML Events

이것은 약간의 흔한 HTML 이벤트 리스트입니다.

| Event | Description |
|---|---|
| onchange | HTML 요소를 바꿉니다 |
| onclick | 유저가 HTML 요소를 클릭합니다 |
| onmouseover | 유저가 HTML 요소 위에 마우스를 올립니다 |
| onmouseout | 유저가 HTML 요소 위에서 마우스가 벗어납니다 |
| onkeydown | 유저가 키보드 키를 누릅니다 |
| onload | 브라우저의 페이지의 로딩이 끝납니다 |

### What can JavaScript Do?

이벤트 핸들러는 사용자의 입력, 행동, 브라우저의 작업을 확인하고 검증하는데 사용할 수 있습니다.

+ 페이지를 로드할 때마다 수행해야 하는 작업
+ 페이지를 닫을 때마다 수행해야 하는 작업
+ 유저가 버튼을 클릭했을 때 수행해야 하는 작업
+ 유저가 데이터를 넣었을 때 검증해야 하는 작업

다양한 메서드들을 사용하여, JavaScript가 이벤트와 함께 작동할 수 있습니다.

+ HTML 이벤트 속성은 JavaScript 코드를 직접 수행할 수 있다.
+ HTML 이벤트 속성은 JavaScript 함수를 호출 할 수 있다.
+ HTML 요소에 고유한 이벤트 핸들러 함수를 할당할 수 있다.
+ 이벤트가 보내지거나 처리되는 것을 막을 수 있다.

> 이벤트와 이벤트 핸들러에 관해서는 HTML DOM 챕터에서 더 많이 배울 수 있습니다.