---
layout : post
title : "[JavaScript] W3C JavaScript (2)"
subtitle : "[JavaScript] JavaScript의 사용 방법"
categories : Development
tags : JavaScript
commens : ture

---

# JavaScript의 사용 방법

> 이 포스트는 자습을 목적으로 [W3C school JavaScript](https://www.w3schools.com/js/default.asp)의 내용을 토대로 작성되었습니다.

_ _ _

### `<script>` 태그

 HTML에서 JavaScript 코드는 반드시 `<script>` 와 `</script>` 태그 안에 위치해야 합니다.

**Example**
```
<!DOCTYPE html>
<html>
	<body>
		<h2>JavaScript in Body</h2>
		<p id="demo"></p>
        <script>
        document.getElementById("demo").innerHTML = "My First JavaScript";
        </script>
	</body>
</html>

```
오래된 자바스크립트 예제에는 "text/javascript" 타입 속성을 사용하였습니다.
지금은 타입 속성이 필요하지 않습니다. JavaScript는 HTML의 기본 스크립팅 언어입니다.

### JavaScirpt의 함수와 이벤트

JavaScript 함수는 JavaScript코드의 블럭이며, 호출할 때 실행됩니다.
예를 들어, 한 함수는 user가 버튼을 클릭할 때와 같은 이벤트 발생 시 호출됩니다.
> 더 자세한 내용은 뒤에서 다루겠습니다.

### JavaScirpt는 `<head>` 또는 `<body>` 안에 위치합니다.

HTML 문서 안에서 많은 script문을 선언할 수 있습니다.
script문들은 HTML 페이지에서 `<head>`, `<body>` 태그 내부에 위치할 수 있습니다.

**Example**
```
<!DOCTYPE html>
<html>
    <head>
        <script>
            function myFunction() {
                document.getElementById("demo").innerHTML = "Paragraph changed.";
            }
        </script>
    </head>
    <body>
        <h1>A Web Page</h1>
        <p id="demo">A Paragraph</p>
        <button type="button" onclick="myFunction()">Try it</button>
        <button type="button" onclick="myFunction2()">Try it</button>
        <script>
            function myFunction2() {
                document.getElementById("demo").innerHTML = "Hello!";
            }
        </script>
    </body>
</html>
```

**`<body>`태그의 가장 아래에 script문을 배치하면 script 컴파일이 화면 속도를 늦추기 때문에 표시 속도가 향상됩니다.**

### 외부 JavaScript

 Script문은 외부의 파일에서도 불러올 수 있습니다.
예를 들어, 외부 파일 myScript.js를 생성합니다.
```
function myFunction() {
	document.getElemnetById('demo').innerHTML = "Paragraph changed.";
}
```
외부 script를 사용하는 것은 효율적인 측면에서 좋습니다.
여러 개의 웹 페이지에서 동일한 코드를 사용하고 싶을 때, 외부 script 하나 만을 선언함으로써 모두 사용 가능합니다.
JavaScript파일은 `.js` 로 저장해야 하며, 외부 script를 사용하기 위해서, 해당 웹 페이지의 `<script>` 태그의 속성 `src`에 파일의 이름을 선언하면 됩니다.

**Example**
```
<!DOCTYPE html>
<html>
    <body>
        <h2>External JavaScript</h2>
        <p id="demo">A Paragraph.</p>
        <button type="button" onclick="myFunction()">Try it</button>
        <p>myFunction is stored in an external file called "myScript.js"</p>
        <script src="myScript.js"></script>
    </body>
</html>

```
외부 script 참조는 `<head>`, `<body>` 어디에서든 선언이 가능하며, `<script>`태그 안에 위치해야 합니다.

> 외부 scirpt들은 `<script>`태그를 포함하고 있지 않습니다.

### 외부 Script의 이점
위에서 간략히 언급했지만, 외부 스크립트를 사용할 때의 몇 가지 이점이 있습니다.
+ HTML코드와 Script코드가 분리됩니다.
+ HTML과 JavaScript를 읽는 것과 유지보수하는 것이 쉽습니다.
+ 캐시된 JavaScript 파일은 페이지 로드를 더 빠르게 할 수 있습니다.

추가적으로 한 페이지에서 여러 개의 외부 파일들을 사용할 수 있습니다.
**Example**
```
<script src = "script1.js"></script>
<script src = "script2.js"></script>
```

### 외부 참조

외부 Script는 URL이나 현재 웹 페이지와 관련된 경로를 통해 참조할 수 있습니다.
다음은, 외부 Script를 참조하는 방법입니다.

**URL**
`<Script src = "https://www.w3schools.com/js/myScript.js"></script>`

**PATH (동일 위치)**
`<Script src = "myScript.js"></script>`

**PATH (다른 위치)**
`<Script src = "/js/myScript.js"></script>`

