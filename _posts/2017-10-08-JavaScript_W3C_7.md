---
layout : post
title : "[JavaScript] W3C JavaScript (7)"
subtitle : "[JavaScript] JavaScript의 Variables"
categories : Development
tags : JavaScript
comments : true

---

# JavaScript Variables

> 이 포스트는 자습을 목적으로 [W3C school JavaScript](https://www.w3schools.com/js/default.asp)의 내용을 토대로 작성되었습니다.

_ _ _

### JavaScript Variables

JavaScript의 변수들은 데이터의 값을 저장하고 있습니다.

**Example**
```
var x = 5;
var y = 7;
var z = x + y;
```
위의 예제는 `x`에는 5를 저장, `y`에는 7을 저장, `z`에는 `x + y`인 12를 저장합니다.

### Much Like Algebra
**Example**
```
var price_water = 500;
var price_coke = 1200;
var total_price = price_water + price_coke;
```
프로그래밍에서는 대수와 비슷하게 변수를 사용하여 값을 저장합니다. 또한, 대수학과 마찬가지로 식의 표현에서 변수를 사용합니다.

### JavaScript Identifiers

모든 JavaScript의 변수들은 특별한 이름으로 식별됩니다.
특별한 이름을 `Identifiers` 즉, 식별자라고 부르며 식별자는 `x`, `y`와 같은 짧은 이름과 `age`, `sum`, `totalVolume`과 같은 기술적인 이름일 수 있습니다.<br>
변수를 구성하는 일반적인 규칙은 다음과 같습니다.
+ 변수의 이름에는 문자, 숫자, `$`, `_` 기호가 포함될 수 있습니다.
+ 변수의 이름은 문자, `$`, `_`기호로 시작할 수 있습니다.
+ 변수의 이름은 **대소 문자**를 구분합니다. (`X`와 `x`는 다른 변수입니다.)
+ 예약어 즉, JavaScript의 Keyword는 변수의 이름으로 사용할 수 없습니다.

### The Assignment Operator

JavaScript에서, equal`=` 기호는 `같다`는 것이 아닌 `대입` 연산자 입니다.
이것은 대수학과 다른 점입니다.
```
x = x + 5
```
JavaScript 에서는 `x` 는 `x + 5`와 같다가 아닌 `x`에 `x + 5` 를 대입한다는 의미입니다.
즉, `x + 5`의 값을 계산하고 그 결과를 `x`에 대입하는 것입니다.
> `equal to`와 같은 연산자는 JavaScript에서 `==`을 사용합니다.

### JavaScript Data Types

JavaScript의 변수는 `100`과 같은 숫자가 될 수 있고, `"John"`과 같은 텍스트도 될 수 있습니다.
프로그래밍에서 이런 텍스트를 문자열`string`이라고 부릅니다. JavaScript는 이외에도 많은 유형의 데이터를 처리 할 수 있습니다. 문자열은 작은 따옴표나 큰 따옴표로 작성되며, 숫자는 따옴표 없이 작성됩니다. 만약 따옴표 안에 숫자를 넣으면 그 숫자는 숫자가 아닌 문자열로 인식됩니다.

**Example**
```
var str = "String";
var num = 1;
var str_num = "1";
```

### Declaring JavaScript Variables

JavaScript의 변수를 만드는 것을 `변수를 선언하다`라고 말합니다.
변수는 JavaScript에서 `var` 키워드를 사용하여 선언되며, 선언이 된 후에는 변수에 아무 값도 가지고 있지 않습니다. 즉, 변수의 값이 정의되지 않은 상태입니다. 이후, 앞에서 배웠던 대입연산자를 사용하여 변수에 값을 정의할 수 있습니다.

**Example**
```
var carName; 			//carName이라는 변수 선언
carName = "Volvo"		//carName에 "Volvo"라는 문자열 대입
var carName2 = "Audi"	//carName2 변수 선언 및 "Audi"라는 문자열 대입
```
이후, `carName` 또는 `carName2`를 출력 시 저장된 `Volvo`와 `Audi`가 출력되는 것을 볼 수 있습니다.

> Script를 시작할 때 모든 변수를 선언하는 것이 좋은 프로그래밍 습관입니다.

### One Statement, Many Variables

우리는 많은 수의 변수들을 한 구문 안에 선언할 수 있습니다.
`var`로 시작해서 `;`로만 끝나면 됩니다.

**Example**
```
var name = "Danpatpang", car = "Audi", age = 25;
var job = "programmer",
	isMale = true,
    phoneNumber = "010-1234-5678";
```

### Value = undefined

컴퓨터 프로그램에서 변수는 종종 값 없이 선언됩니다. 값은 무언가를 계산한 값이나, 사용자의 입력 값이 될 수도 있습니다.
Value 값 없이 선언 된 변수는 값을 가지고 있지 않습니다. 즉, `var carName`은 선언이 후 값을 가지고 있지 않게 됩니다.

### Re-Declaring JavaScript Variables

만약 JavaScript에서 변수를 다시 선언한다면, 저장된 값을 잃지 않습니다.

**Example**
```
<script>
    var value = "I'm stored";
    var value;
    document.write(value);
</script>
```

### JavaScript Arithmetic

대수학에서와 같이, JavaScirpt 변수들은 `=`, `+`와 같은 연산자를 이용하여 산술적으로 사용될 수 있습니다.

**Example**
```
<script>
    var cal = 5+2*10;
    var str = "Dan" + " " + "patpang";
    var whatIsThis = "5" + 2 + 3;
    document.write(cal);
    document.write(str);
    document.write(whatIsThis);
</script>
```
> 만약 숫자를 따옴표로 묶으면 나머지 숫자들은 문자열로 처리됩니다.

**Example**
```
var w = 2 + 3 + "5";				// result 55
var x = "5" + 2 + 3;				// result 523
var y = 12 * 12 + "1";				// result 1441
var z = "1" + 12 * 12 + 3 + 6;		//result 111436
document.write(w, x, y, z);
```