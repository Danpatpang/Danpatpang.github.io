---
layout : post
title : "[JavaScript] W3C JavaScript (4)"
subtitle : "[JavaScript] JavaScript의 Syntax"
categories : Development
tags : JavaScript
comments : true

---

# JavaScript Syntax

> 이 포스트는 자습을 목적으로 [W3C school JavaScript](https://www.w3schools.com/js/default.asp)의 내용을 토대로 작성되었습니다.

_ _ _

JavaScript 문법은 JavaScript 프로그램이 어떻게 구성되는지에 대한 규칙의 집합입니다.

### JavaScript Programs

컴퓨터 프로그램은 컴퓨터에 의해 `"instructions"`, `"executed"` 즉, 실행 할 목록입니다.
프로그램 언어에서, 이 프로그램 명령들을 `statements` 라고 부릅니다.
JavaScript는 프로그램 언어이고, 이 언어의 `statements`는 `;`으로 분리됩니다.

**Example**
```
<!DOCTYPE HTML>
<html>
	<body>
    	<script>
            var x, y, z;
            x = 5;
            y = 6;
            z = x + y;
            document.write(z);
        </script>
    </body>
</html>
```
HTML에서 JavaScript 프로그램은 웹 브라우저에 의해 실행됩니다.

### JavaScript Statements

JavaScript 구문들은 다음과 같이 구성됩니다.
+ Values ( 값 )
+ Operators ( 연산자 )
+ Expressions ( 표현식 )
+ Keywords ( 키워드 )
+ Comments ( 주석 )

### JavaScript Values

JavaScript 문법은 2종류의 Value로 정의되어 있습니다.
+ Fixed values ( 고정된 값 )
+ variable values ( 변수 )

고정된 값은 `literals`라고 불리며, 변수는 `varialbes`라고 불립니다.

#### JavaScript Literals

고정된 값을 사용할 때 가장 중요한 규칙은 다음과 같습니다.
+ Numbers
	+ 숫자는 10진법에 관계없이 사용가능 합니다.

**Example**
```
<script>
    document.wriet(10.50);
    document.write(1001);
</script>
```
> document.write(10.50)의 경우 출력 값이 10.5로 소수점 2번째 자리의 0이 생략되는 것을 볼 수 있습니다.

<br>
+ String
	+ 문자열은 큰따옴표 또는 작은따옴표로 작성된 텍스트입니다.

**Example**
```
"Danpatpang"
'Danpatpang'
```

#### JavaScript Variables

프로그래밍 언어에서, 변수는 데이터 값의 저장을 위해 사용됩니다.
JavaScript는 `var` keyword를 사용하여 변수를 선언합니다.
`=`은 변수에 값을 할당 할 때 사용합니다.

**Example**
```
<script>
	var x;
    x = 6;
</script>
```
> x라는 변수를 정의하고, x에 6이라는 값을 할당합니다.

### JavaScript Operators

JavaScript는 값의 계산을 위한 `산술 연산자( +, -, *, /, ...)`와 변수들에게 값을 할당하기 위한 `할당 연사자( = )`를 사용합니다.
**Example**
```
<script>
	var x, y;
    x = ( 5 + 6 ) * 10;
    y = x;
	document.write(y);
</script>
```

### JavaScript Expressions

표현식은 values, variables, operators 등으로 구성되며, 계산되는 값입니다.
이 계산을 `evaluation`이라고 부릅니다.
표현식은 변수를 포함할 수 있으며, value의 타입은 `number`나 `string`같은 여러 종류의 타입이 될 수도 있습니다.

**Example**
```
<script>
	var x = 1;
	document.write(5 * 10);
    document.write(x * 10);
    document.write("Dan" + " " + "patpang");
</script>
```

### JavaScript Keywords

JavaScript keywords는 수행할 작업을 식별하는데 사용됩니다.
`var` keyword는 browser에서 변수를 생성하기 위해 사용합니다.

### JavaScript Comments

주석으로 작성된 구문은 JavaScript에서 실행되지 않습니다.
주석은 코드에 `//` 또는 `/* */`를 사용하여 처리할 수 있습니다.
주석은 프로그램 실행 시 무시되며, 절대 실행되지 않습니다.

**Example**
```
<!Doctype HTML>
<html>
	<body>
    	<p>나의 값은 무엇인가?</p>
    	<p id = "demo"></p>
    	<script>
        	var y;
            y= 5;
            // y = 6;
        	document.getElementById('demo').innerHTML = y;
        </script>
    </body>
</html>
```

### JavaScript Idetifiers

식별자는 이름입니다.
JavaScript에서 식별자는 variable, function, label, keyword의 이름으로 사용됩니다.
대부분의 프로그래밍 언어에서의 선호되는 규칙은 동일합니다.
JavaScript에서 첫 번째 문자는 반드시 `문자`, `_`, `$`입니다.
이후에 이어지는 문자는 `문자`, `숫자`, `_`, `$`입니다.
> 숫자는 절대 첫 번째 문자로 사용할 수 없습니다.
> 이렇게 함으로써, JavaScript에서 숫자와 식벽자를 더 쉽게 분별할 수 있습니다.

### JavaScript는 대소문자를 구분합니다.

모든 JavaScript 식별자들은 대소문자를 구분합니다.

**Example**
```
<script>
    var test, Test;
    test = "A";
    Test = "B";
    document.write(test, Test);
</script>
```
> test의 경우 `A`를 출력하며, Test의 경우 `B`를 출력합니다.
> 또한, JavaScript는 `VAR` 또는 `Var`을 `var`로 인식하지 않습니다.

### JavaScript와 Camel Case

역사적으로, 프로그래머들은 여러 단어를 하나의 변수 이름으로 결합하는 여러가지 방법을 사용했습니다.
+ Underscore`_`의 사용
	+ **Example** `first_name`, `master_card`, `inter_city`
+ Upper Camel Case의 사용 ( Pascal Case )
	+ **Example** `FirstName`, `MasterCard`, `InterCity`
+ Lower Camel Case의 사용
	+ **Example** `firstName`, `lastName`, `interCity`

JavaScript 프로그래머들은 Lower Camel Case를 사용하는 경향이 있습니다.

### JavaScrupt Character Set

JavaScript는 `Unicode` character set을 사용합니다.
`Unicode`는 전 세계 대부분의 문자, 구두점, 기호 등을 포함하고 있습니다.
더 자세히 알고 싶으시다면, [Complete Unicod Reference](https://www.w3schools.com/charsets/ref_html_utf8.asp)를 참고하시면 됩니다.