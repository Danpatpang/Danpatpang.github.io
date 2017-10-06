---
layout : post
title : "[JavaScript] W3C JavaScript (6)"
subtitle : "[JavaScript] JavaScript의 Comments"
categories : Development
tags : JavaScript
comments : true

---

# JavaScript Comments

> 이 포스트는 자습을 목적으로 [W3C school JavaScript](https://www.w3schools.com/js/default.asp)의 내용을 토대로 작성되었습니다.

_ _ _

JavaScirpt 주석은 JavaScript 코드를 설명할 때 사용하고, 가독성을 향상시킵니다.
또한, 코드를 테스트 할 때, 원하지 않는 코드의 실행을 막을 수 있습니다.

### Single Line Comments

단일 코드 주석은 `//`로 시작합니다.
`//` 부터 라인의 끝까지 있는 JavaScript 코드는 JavaScript 실행에서 무시됩니다.

**Example**
```
<!DOCTYPE html>
<html>
    <body>
        <h1 id="head"></h1>
        <p id="paragraph"></p>
        <script>
            // Change heading:
            document.getElementById("head").innerHTML = "My page";
            // Change paragraph:
            document.getElementById("paragraph").innerHTML = "Hello";
        </script>
        <p id = "paragraph2"></p>
        <script>
        	var str = "Everyone";	//str에 "Everyone" 저장
            document.getElementById("paragraph2").innerHTML = str;
        </script>
    </body>
</html>
```
`//`는 코드라인의 위와, 코드 라인의 옆에 코드의 설명으로 사용할 수 있습니다.

### Multi-line Comments
다중 라인 주석은 `/*`로 시작하여 `*/`으로 끝납니다.
`/* */` 사이의 코드들은 모두 무시됩니다.

**Example**
```
<script>
	/*
    This code print z.
    z is x + y;
    x =5; and y =6;
    */
    var x, y, z;
    x = 5;	y = 6;
    z = x + y;
    document.wrtie(z);
</script>
```
> 대부분의 주석은 signle line comments로 사용됩니다.<br>
> Blcok comments는 형식적인 문서에서 사용합니다.

### Using Comments to Prevent Execution

코드 실행을 방지하기 위해 주석을 사용하여 코드를 테스팅을 합니다.
코드 행 앞에 `//`를 추가하면 코드 행은 주석 행으로 변경됩니다.

**Example**
```
<!DOCTYPE html>
<html>
    <body>
        <p id="demo"></p>
        <p id="demo2"></p>
        <script>
        	var x, y, z;
            x = 2;
            y = 3;
            z = x + y;
            document.getElementById("demo").innerHTML = "Hello";
            document.getElementById("demo2").innerHTML = z;
            /*
            x = 1;
            y = 2;
            z = x + y;
            document.getElementById("demo2").innerHTML = z;
            */
        </script>
    </body>
</html>
```