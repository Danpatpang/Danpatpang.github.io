---
layout : post
title : "[JavaScript] W3C JavaScript (14)"
subtitle : "[JavaScript] JavaScript의 영역"
categories : Development
tags : JavaScript
comments : true

---

# JavaScript Scope

> 이 포스트는 자습을 목적으로 [W3C school JavaScript](https://www.w3schools.com/js/default.asp)의 내용을 토대로 작성되었습니다.

_ _ _

### JavaScript Function Scope

JavaScript에는 2가지 종류의 타입이 있습니다.
+ local scope (지역 범위)
+ global scope (전역 범위)

JavaScript는 각각의 함수를 만들 때 새로운 범위를 주어 함수의 범위를 가집니다.
범위는 이러한 변수들의 접근성(가시성)을 결정합니다.
함수 내에서 정의된 변수는 함수 외부에서 접근할 수 없습니다.

### Local JavaScript Variable

JavaScript 함수 내에서 선언된 변수는 함수의 LOCAL이 됩니다.
로컬 변수는 로컬 영역을 가진다. 그들은 함수 내에서만 접근할 수 있습니다.

```
function myFunction() {
    var carName = "Volvo";
```

로컬 변수가 함수 내부에서만 인식되기 때문에, 같은 이름의 변수를 다른 함수에서 사용할 수 있습니다.
로컬 변수는 함수가 시작할 때 생생되며, 함수가 종료 시 삭제됩니다.

### Global JavaScript Variables

변수가 함수 밖에서 선언되면, 전역 변수가 됩니다.
전역 변수는 웹 페이지의 모든 스크립트과 함수에서 접근할 수 있는 global scope를 가집니다.

```
var carName = " Volvo";
	// code here can use carName
function myFunction() {
    // code here can use carName 
}
```

### JavaScript Variables

JavaScript에서 개체와 함수 또한 변수입니다.
> 스코프는 코드의 다른부분에서 변수, 개체, 함수의 접근성을 정의합니다.

### Automatically Global

만약 선언되지 않은 변수에 값을 할당한다면, 자동으로 글로벌 변수가 됩니다. 이 코드는 값이 함수 내에 할당 된 경우에도 전역 변수 carName을 선언합니다.

```
<!DOCTYPE html>
<html>
    <body>

    <p>
    If you assign a value to a variable that has not been declared,
    it will automatically become a GLOBAL variable:
    </p>

    <p id="demo"></p>

    <script>
        myFunction();

        // code here can use carName as a global variable
        document.getElementById("demo").innerHTML = "I can display " + carName;

        function myFunction() {
            carName = "Volvo";
        }
    </script>

    </body>
</html>
```

### Strict Mode

모든 현대의 브라우저는 "Strict Mode"에서 JavaScript가 실행될 수 있도록 지원합니다. 당신은 튜토리얼의 나중 챕터에서 strict mode를 사용하는 방법을 배울 수 있습니다.

> 전역 변수는 "Strict Mode"에서 자동적으로 생성되지 않습니다.

### Global Variables in HTML

JavaScript에서 전역 범위는 완전한 JavaScript 환경입니다.
HTML에서 전역 범위는 윈도우 객체입니다. 모든 전역 변수는 윈도우 객체에 속해 있습니다.

```
var carName = "Volvo";
```


### Warning

> 의도하지 않는 한, 전역 변수를 작성하지 마세요.
> 너의 전역 변수(함수)는 윈도우 변수(함수)를 덮어쓸 수 있습니다.
> 윈도우 객체를 포함하는 함수는 당신의 전역변수와 함수를 덮어쓸 수 있습니다.

### The Lifetime of JavaScript Variables

JavaScript 변수의 생명주기는 변수가 선언되었을 때 시작됩니다.
지역변수는 함수가 종료될 시 삭제됩니다.
웹 브라우저에서 전역 변수는 브라우저 창을 닫거나(탭) 할 때 삭제됩니다. 하지만, 같은 창에 로드된 새 페이지에서는 계속 사용할 수 있습니다.

### Function Arguments

함수의 인자(매개 변수)는 함수 내에서 지역 변수로 작동합니다.