---
layout : post
title : "[JavaScript] W3C JavaScript (13)"
subtitle : "[JavaScript] JavaScript의 Objects"
categories : Development
tags : JavaScript
comments : true

---

# JavaScript Objects

> 이 포스트는 자습을 목적으로 [W3C school JavaScript](https://www.w3schools.com/js/default.asp)의 내용을 토대로 작성되었습니다.

_ _ _

### Real Life Objects, Properties, and Methods

실세계에서, 자동차는 하나의 object입니다.
자동차는 무게, 색상과 같은 속성을 가지고 있고, 출발하고 멈추는 기능을 가지고 있습니다.
![car](https://www.w3schools.com/js/objectExplained.gif)

| 속성 | 기능 |
|---|---|
| car.name = Fiat | car.start() |
| car.model = 500 | car.drive() |
| car.weight = 850kg | car.brake() |
| car.color = white | car.stop() |

모든 차량은 같은 속성을 가지고 있지만, 각 차마다 다른 속성 값을 가집니다.
또한, 모든 차는 같은 기능을 가지고 있지만 메서드가 수행되는 시간은 다릅니다.

### JavaScript Objects

우리는 이미 JavaScript 변수가 데이터 값을 포함한다는 것을 배웠습니다.
다음의 코드는 `car`변수에 단순한 값을 대입하는 것입니다.
```
var car = "Fiat";
```
객체들 또한 변수입니다. 그러나 객체는 많은 값들을 포함할 수 있습니다.
다음의 코드는 `car`라는 변수에 많은 값을 대입하는 것입니다.
```
var car = {type:"Fiat", model:"500", color:"white"};
```
`name:value`쌍을 이용하여 값을 작성합니다. (각 name들은 `,`로 분리됩니다.)
> JavaScript 객체는 이름을 가지는 값들을 포함합니다.

### Object Properties

`name:value`쌍은 JavaScript에서 속성이라고 불립니다.
```
var person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};
```

| Property | Porperty Value |
|---|---|
| fistname | Dan |
| lastname | Patpang |
| age | 50 |
| eyeColor | blue |

### Object Methods

메서드는 객체가 수행할 수 있는 동작입니다.
메서드는 함수 정의로써 속성에 저장됩니다.

| Property | Porperty Value |
|---|---|
| fistName | Dan |
| lastName | Patpang |
| age | 50 |
| fullName | `function(){retrun this.firstName + " " + this.lastName}` |

> JavaScript 객체들은 속성 또는 메서드를 포함하고 있습니다.

### Object Definition
우리는 객체 리터럴을 사용하여 JavaScript 객체를 정의(및 생성)합니다.
띄어쓰기와 줄바꿈을 중요하지 않습니다. 객체는 다중의 라인으로 작성 될 수 있습니다.

**Example**
```
var person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};
//equal
var person = {
    firstName:"John",
    lastName:"Doe",
    age:50,
    eyeColor:"blue"
};
```

### Accessing Object Properties

우리는 2가지 방법으로 객체의 속성에 접근할 수 있습니다.

**Example**
```
// objectName.propertyName
<script>
    var person = {
        firstName: "John",
        lastName : "Doe",
        id       :  5566
    };

    document.getElementById("demo").innerHTML =
    person.firstName + " " + person.lastName;
</script>
```
```
// objectName["propertyName"]
<script>
    var person = {
        firstName: "John",
        lastName : "Doe",
        id       :  5566
    };

    document.getElementById("demo").innerHTML =
	person["firstName"] + " " + person["lastName"];
</script>
```

### Accessing Object Methods

메서드는 다음과 같은 문법으로 접근할 수 있습니다.
```
objectName.methodName()
```
**Example**
```
<script>
    var person = {
        firstName: "John",
        lastName : "Doe",
        id       : 5566,
        fullName : function() {
           return this.firstName + " " + this.lastName;
        }
    };

    document.getElementById("demo").innerHTML = person.fullName();
</script>
```
만약 메서드에서 ()를 생략하고 접근한다면, 함수의 정의가 반환됩니다.
```
<script>
    var person = {
        firstName: "John",
        lastName : "Doe",
        id       : 5566,
        fullName : function() {
           return this.firstName + " " + this.lastName;
        }
    };

    document.getElementById("demo").innerHTML = person.fullName;
    // 결과 값
    // function () { return this.firstName + " " + this.lastName; }
</script>
```
> 메서드는 실제로 속성의 값으로써 저장되는 함수 정의입니다.

### Do Not Declare Strings, Numbers, and Booleans as Objects!

JavaScript 변수는 "new"라는 키워드와 함께 선언됩니다.
변수는 객체로서 생성됩니다.

```
var x = new String();        // Declares x as a String object
var y = new Number();        // Declares y as a Number object
var z = new Boolean();       // Declares z as a Boolean object
```
String, Number, Boolean 객체는 피하는 것이 좋습니다. 코드가 복잡해지고 실행 속도가 느려지게 됩니다.