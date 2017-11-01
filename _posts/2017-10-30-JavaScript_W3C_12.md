---
layout : post
title : "[JavaScript] W3C JavaScript (12)"
subtitle : "[JavaScript] JavaScript의 Functions"
categories : Development
tags : JavaScript
comments : true

---

# JavaScript Functions

> 이 포스트는 자습을 목적으로 [W3C school JavaScript](https://www.w3schools.com/js/default.asp)의 내용을 토대로 작성되었습니다.

_ _ _

### JavaScript Functions

**JavaScript 함수는 특정한 작업을 수행하기 위해 설계한 블럭 코드입니다.**
**JavaScript 함수는 무언가에 의해 호출될 때 실행됩니다.**
```
function myFunction(p1, p2){		//p1, p2를 곱한 값을 반환하는 함수
	return p1* p2;
}
```

### JavaScript Function Syntax

JavaScript함수는 키워드`function`, 함수 이름, `()`와 함께 정의됩니다.
함수 이름은 문자, 숫자, `_`, `$`를 포함할 수 있습니다. `()`에는 파라미터를 포함할 수 있습니다. `{ }`안에는 함수에 의해 실행될 코드를 작성합니다.
```
function function_name(parameter1, parameter2, parameter3){
	// code to be executed
}
```
함수의 parameter는 함수의 정의에서 `()` 안에 선언된 변수의 이름입니다.
함수의 argument는 함수가 호출 될 때 함수가 가져오는 실제 값 입니다.
함수 내에서 argument는 지역 변수로 사용됩니다.
> 함수는 다른 프로그램에서 Procedure이나 Subroutine과 동일합니다.

### Function Invocation

함수 내부의 코드는 함수의 호출에 의해서 실행됩니다.
+ 이벤트가 발생했을 때 (유저가 버튼을 클릭할 때)
+ JavaScript 코드에서 함수를 호출 할 때
+ 자동적으로 (self invoked)

### Function Return
JavaScript가 `return statement`에 도착하면, 함수의 실행는 중지됩니다.
