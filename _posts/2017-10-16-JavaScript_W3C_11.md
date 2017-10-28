---
layout : post
title : "[JavaScript] W3C JavaScript (11)"
subtitle : "[JavaScript] JavaScript의 Data Types"
categories : Development
tags : JavaScript
comments : true

---

# JavaScript Data Types

> 이 포스트는 자습을 목적으로 [W3C school JavaScript](https://www.w3schools.com/js/default.asp)의 내용을 토대로 작성되었습니다.

_ _ _

### JavaScript Data Types

JavaScript의 변수는 다양한 데이터 타입으로 묶여 있습니다.

**Example**
```
var length = 16;	// Number
var lastname = "Patpang";	//String
var name = {firstName:"Dan", lastName:"Patpang"};	//Object
```

### The Concept of Data Types

프로그래밍에서 데이터 타입은 중요한 개념입니다.
변수로 작동하려면, 타입에 대해 알아야 합니다.
데이터 타입이 없다면, 안전하게 문제를 해결할 수 없습니다.
```
var x = 16 + "Volvo";
```
예를 들어, 16과 "Volvo" 를 더하는 것은 어떤 의미입니까?
`x`는 결과물을 생산할까요 아니면 에러를 생산할까요?
JavaScript는 위의 예를 다음과 같이 해석합니다.
```
var x = "16" + "Volvo";
```
> 숫자와 문자열을 더할 때, JavaScript는 숫자를 문자열처럼 다룹니다.

```
var x = 16 + "Volvo";	//result 16Volvo
var x = "Volvo" + 16;	//result Volvo16
var x = 16 + 4 + "Volvo";	//result 20Volvo
var x = "Volvo" + 16 + 4;	//result Volvo164
```
> JavaScript는 표현식을 왼쪽에서부터 오른쪽으로 평가합니다. 시퀀스가 다르면 다른 결과가 발생할 수 있습니다.<br>
> 3번째 예제에서는 문자열에 도달하기 전까지 숫자로 처리합니다.<br>
> 4번째 에제에서는 문자열에 문자열부터 시작하므로 모든 피연산자는 문자열로 처리됩니다.

### JavaScript Types are Dynamic

JavaScript에는 동적인 타입이 있습니다. 즉, 동일한 변수를 사용하여 다른 데이터 타입을 유지할 수 있습니다.
```
var x;			// Now x is Undifned
var x = 5;		// Now x is Number
var x = "John";	// Now x is String
```

### JavaScript Stirngs
String은 일련의 문자입니다. 문자열은 따옴표로 작성되며 작은따옴표 또는 큰따옴표를 사용할 수 있습니다.
**Example**
```
var car = "Volvo";
var car = 'volvo';
```

> 문자열을 둘러싼 따옴표와 동일하지 않는 한 문자열 내에서 다른 따옴표를 사용할 수 있습니다.

### JavaScript Numbers

JavaScript는 오직 한가지 타입의 숫자를 가지고 있습니다.
Numbers는 소수 또는 소수 없이 작성될 수 있습니다.
**Example**
```
var x1 = 34.00;
var x2 = 34;
```
매우 크거나 매우 작은 숫자는 과학적(기하 급수적)표현을 사용하여 작성할 수도 있습니다.
**Example**
```
var x = 123e5;	// 12300000
var z = 123e-5;	// 0.00123
```
