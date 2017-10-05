---
layout : post
title : "[JavaScript] W3C JavaScript (5)"
subtitle : "[JavaScript] JavaScript의 Statement"
categories : Development
tags : JavaScript
comments : true

---

# JavaScript Statement

> 이 포스트는 자습을 목적으로 [W3C school JavaScript](https://www.w3schools.com/js/default.asp)의 내용을 토대로 작성되었습니다.

_ _ _

HTML에서 JavaScript 구문은 웹 브라우저에 의해 실행 되거나, 명령입니다.

### JavaScript Statements

이 예제는 HTML 안에서 `"demo"`라는 `id`를 가지고 있는 요소가 Hello를 출력하도록 하는 구문입니다.

**Example**
```
<!DOCTYPE html>
<html>
    <body>
        <h2>JavaScript Statements</h2>
        <p>In HTML, JavaScript statements are executed by the browser.</p>
        <p id="demo"></p>
        <script>
	        document.getElementById("demo").innerHTML = "Hello Dolly.";
        </script>
    </body>
</html>
```

### JavaScript Programs

대부분의 JavaScript 프로그램들은 많은 JavaScript 구문들을 포함하고 있습니다.
구문들은 작성된 순서대로 한 줄씩 실행됩니다.
이 예제는 한 줄씩 실행되어 마지막에 z값을 출력하빈다.

**Example**
```
<!DOCTYPE html>
<html>
    <body>
        <script>
        	var x,y,z;
            x = 10;
            y = 5;
            x = 7;
            z = x + y;
	        document.write(z);
        </script>
    </body>
</html>
```
`x`값은 `10`에서 `7`로 바꼈으므로 출력 결과로 `z`는 `12`가 됩니다.
> JavaScript 프로그램과 구문들을 JavaScript code라고 부릅니다.

### Semicolons `;`

세미콜론은 JavaScript구문들을 분리하는 역할을 합니다.
실행될 각 구문의 끝마다 세미콜론을 붙여 구문들을 분리해야 합니다.
또한, 세미콜론으로 구문들이 분리되므로, 한 라인에 여러 구문을 적어도 상관없습니다.

**Example**
```
var a,b,c;
a = 1; b = 2; c = a + b;
```
### JavaScript White Space

JavaScript는 다중의 공백을 무시합니다. 우리는 코드의 가독성을 높이기 위해서 스크립트에 공백을 붙여도 상관없습니다.
JavaScript의 구문은 `;`에 의해 분리되는 것만 유의하시면 됩니다.
**Example**
```

``` 

### JavaScript의 Line length와 Line Block

가독성을 높이기 위해, 프로그래머들은 각 행이 80자가 넘지 않도록 하는 것이 좋습니다.
만약 JavaScript 구문이 한 라인에 맞지 않다면, 연산자 이후의 부분은 다음 줄에 작성하는 것도 좋습니다.

**Example**
```

```

### JavaScript Code Block

JavaScript

JavaScript 구문은 `{...}`처럼 중괄호 안에 코드 블럭으로 묶을 수 있습니다.
코드 블럭의 목적은 함께 실행될 명령문을 정의하는 것입니다.
우리는 JavaScript 함수에서 블록으로 묶여있는 구문들을 찾을 수 있습니다.

**Example**
```

```

> 이 튜토리얼에서는 코드의 여백을 4칸으로 사용하고 있습니다.

### JavaScript Keywords

JavaScript 구문들은 JavaScript가 수행하는 역할들을 식별하기 위해서 `keyword`를 앞에 붙여 함께 사용합니다.
다음은 튜토리얼에서 다루게 될 `keyword`의 목록입니다.
| Keyword | Description |
|--------|--------|
| break | swith와 같은 loop문들을 종료합니다. |
| continue | 실행중인 loop에서 나온 후, 코드 블럭의 맨 위로 갑니다. |
| debugger | JavaScript의 실행을 멈추고, debugging 함수를 호출합니다. |
| do ... while | do의 코드 블럭을 실행 후, while의 조건이 true가 될 때까지 블럭을 반복 실행 합니다. |
| for | 조건이 true인 한 실행될 구문을 표시합니다. |
| function | 함수를 정의 합니다. |
| if ... else | 조건에 따라 실행될 구문을 블럭으로 표시합니다. |
| return | 함수를 빠져 나갑니다. |
| switch | 각기 다른 case들에 의존하여 다른 코드 블럭들을 실행합니다. |
| try ... catch | 블럭의 구문에 오류를 처리하기 위해 구현합니다. |
| var | 변수를 선언합니다. |
> JavaScript keyword는 예약어입니다.
> 예약어는 변수로 사용할 수 없습니다.