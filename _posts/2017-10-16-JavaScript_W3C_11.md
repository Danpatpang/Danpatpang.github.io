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
### JavaScript Booleans

Booleans는 오직 true / false의 값만 가질 수 있습니다.
**Example**
```
var x = 5;
var y = 5;
var z = 6;
(x == y);		// return true
(x == z);		// return false
```
Booleans는 조건의 테스트 용도로 사용됩니다.

### JavaScript Arrays

JavaScript배열은 대괄호`[]`로 작성되며 배열의 요소는 `,`로 분리됩니다.
다음 코드는 cars라는 배열을 선언하고 3개의 요소를 가지고 있습니다.
**Example**
```
var cars = ["Volvo", "BMW", "SM5"];
```
배열의 인덱스는 0부터 시작합니다. 즉, 첫 번째 항목은 cars[0]이고 두 번째 항목은 cars[1]입니다.

### JavaScript Objects

JavaScript 객체들은 중괄호`{}`로 작성됩니다.
객체의 속성들은 `name : value`의 쌍으로 작성되며 `,`로 분리됩니다.
**Example**
```
var person = {firstName:"Dan", lastName:"patpang" age:25, job:"student" };
```
위의 예제에서 person객체는 fristName, lastName, age, job이라는 4가지 속성을 가지고 있습니다.

### The typeof Operator

우리는 JavaScirpt에서 JavaScript 변수의 type을 찾기 위해 `typeof` 연산자를 사용할 수 있습니다.
`typeof`연산자는 변수 또는 표현식의 type을 반환합니다.
**Example**
```
typeof "";		// return string
typeof "Dan";	// return string
typeof "25";	// retrun string
typeof 0;		// return number
typeof 3.14;	// return number
typeof (3+4);	// return number
```

### Undefined

JavaScript에서 값을 가지고 있지 않은 변수들은 undefined 값을 가집니다.
값을 undefined로 설정하면 변수를 비울 수 있으며 type또한 정의되지 않습니다.
**Example**
```
var car;	// value is undefined, type is undefined
car = undefined;	// value is undefined, type is undefined
```
### Empty Values

비어있는 값은 undefined와 아무런 관련이 없습니다.
빈 문자열은 유효한 값과 문자열을 가집니다.
**Example**
```
var car = "";		// The value is "", The type is String
```

### Null

JavaScript에서 null은 아무것도 아닙니다. 이것은 존재하지 않는 것으로 가정합니다.
불행하게도 JavaScript에서 null의 데이터 유형은 `object`입니다.

> typeof null의 값이 object라는 점은 JavaScript의 버그라고도 생각할 수 있습니다.

**Example**
```
var person = {firstName:"Dan", lastName:"patpang" age:25, job:"student" };
person = null;		//현재의 값은 null, type은 object
```

### Difference Between Undefined and Null
undefined와 null은 값은 동일하지만 type은 동일하지 않습니다.
**Example**
```
typeof undefined;		// undefined
typeof null;			// object

null === undefined		// false
null == undefined		// true
```

### Primitive Data

primate data의 값은 추가 속성 및 메서드가 없는 단순한 데이터 값입니다.
typeof 연산자는 이런 primate type중 하나를 반환합니다.( string, number, boolean, undefined )
**Example**
```
typeof "Dan";		// return string
typeof 3.14;		// return number
typeof true;		// return boolean
typeof false;		// retrun boolean
typeof x;			// return undefined
```

### Complex Data

typeof 연산자는 2개의 복잡한 type을 반환할 수 있습니다.( function, object )
typeof 연산자는 객체, 배열 및 null에 대해 object를 반환하며, 함수에 대해서는 객체를 반환하지 않습니다.
**Example**
```
typeof {name:'Dan', age:25};	//return object
typeof [1, 2, 3, 4];			//return object
typeof null;					//return object
typeof function Func(){};		//return function
```
> typeof 연산자는 JavaScript배열이 객체이므로 object를 반환합니다.
