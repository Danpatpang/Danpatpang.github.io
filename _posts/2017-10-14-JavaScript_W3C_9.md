---
layout : post
title : "[JavaScript] W3C JavaScript (9)"
subtitle : "[JavaScript] JavaScript의 Arithmetic"
categories : Development
tags : JavaScript
comments : true

---

# JavaScript Arithmetic

> 이 포스트는 자습을 목적으로 [W3C school JavaScript](https://www.w3schools.com/js/default.asp)의 내용을 토대로 작성되었습니다.

_ _ _

### JavaScript Arithmetic

숫자와 관련하여 무언가를 하는 전형적인 것들을 산술이라고 합니다.

### JavaScript Arithmetic Operators

산술 연산자는 숫자(문자열, 변수)에 대한 산술 연산을 수행합니다.

| Operator | Description |
|:-:|---|
| `+` | 덧셈 |
| `-` | 뺄셈 |
| `*` | 곱셈 |
| `/` | 나눗셈 |
| `%` | 나머지 |
| `++` | 증가 |
| `--` | 감소 |


### Arithmetic Operations

전형적인 산술 연산자는 두개의 수로 연산됩니다.
두개의 수가 문자열일 수도 있습니다.

**Example**
```
var a = 100;
var b = 200;
var x = 100 + 50;
document.write(x);
var x = a + b;
document.write(x);
var x = (100 + 50 ) * a;
document.write(x);
```

### Operators and Operands

산술 연산자에서 숫자는 `operand`라고 불립니다.
또한, 2개의 `operand` 사이에서 연산을 수행하는 연산자를 `operator` 라고 정의합니다.

**Example**
```
var x = 5;
var y = 2;
var z = x + y;
document.write(z);
var z = x - y;
document.write(z);
var z = x * y;
document.write(z);
var z = x / y;
document.write(z);
var z = x % y;
document.write(z);
var z = x++;
document.write(z);
var z = x--;
document.write(z);
```

### Operator Precedence

연산자의 우선 순위는 산술 표현식에서 연산이 수행되는 순서를 정의합니다.

**Example**
```
var x = 100 + 50 * 3;
var y = (100 + 50) * 3;
```

x와 y의 결과 값은 서로 다르게 나오게 됩니다. 또한, `+` 연산자 보다는 `*` 연산자가 먼저 실행됩니다. 연산자의 우선 순의는 전통적인 수학연산과 비슷합니다. `+`, `-` 보다는 `*`, `/` 이 먼저 실행되는 것입니다. 또한, `()`을 사용하여 우선 순위를 변경할 수도 있습니다.
`()`를 사용하게 되면, `()` 안에 있는 연산자들이 우선적으로 실행됩니다. 동일한 우선 순위의 연산자들이 있을 경우에는 좌측부터 우측으로 차례로 실행됩니다.

##JavaScript Operator Precedence Values

| Value | Operator | Description | Example |
|---|---|---|---|
| 19 | `()` | 표현식의 그룹화 | (3 + 4) |
|   |   |   |   |
| 18 | `.` | 멤버 | person.name |
| 18 | `[]` | 멤버 | person["name"] |
|   |   |   |   |
| 17 | `()` | 함수 호출 | myFunction() |
| 17 | `new` | 생성 | new Date() |
|   |   |   |   |
| 16 | `++` | 접미사에 붙는 증가 | x++ |
| 16 | `--` | 접미사에 붙는 감소 | x-- |
|   |   |   |   |
| 15 | `++` | 접두사에 붙는 증가 | ++x |
| 15 | `--` | 접두사에 붙는 감소 | --x |
| 15 | `!` | NOT | !(x == y) |
| 15 | `typeof` | 타입 | typeof x |
|   |   |   |   |
| 14 | `*` | 곱셈 | 10 * 5 |
| 14 | `/` | 나눗셈 | 10 / 5 |
| 14 | `%` | 나머지 | 10 % 5 |
| 14 | `**` | 제곱 |  10 \** 3 |
|   |   |   |   |
| 13 | `+` | 덧셈 | 10 + 5 |
| 13 | `-` | 뺄셈 | 10 - 5 |
|   |   |   |   |
| 12 | `<<` | 좌측 쉬프트 | x << 2 |
| 12 | `>>` | 우측 쉬프트 | x >> 2 |
| 12 | `>>>` | 우측 쉬프트(부호X) | x >>> 2 |
|   |   |   |   |
| 11 | `<` | 작다 | x < y |
| 11 | `<=` | 작거나 같다 | x <= y |
| 11 | `>` | 크다 | x > y |
| 11 | `>=` | 크거나 같다 | x >= y |
|   |   |   |   |
| 10 | `==` | 같다 | x == y |
| 10 | `===` | 같다(타입 포함) | x === y |
| 10 | `!=` | 다르다 | x != y |
| 10 | `!==` | 다르다(타입 포함) | x !== y |
|   |   |   |   |
| 6 | `&&` | AND | x && y |
| 5 | `||` | OR | x `||` y  |
|   |   |   |   |
| 3 | `=` | 대입 | x = y |
| 3 | `+=` | 대입 | x += y |
| 3 | `-=` | 대입 | x -= y |
| 3 | `*=` | 대입 | x *= y |
| 3 | `%=` | 대입 | x %= y |
| 3 | `<<=` | 대입 | x <<= y |
| 3 | `>>=` | 대입 | x >>= y |
| 3 | `>>>=` | 대입 | x >>>= y |
| 3 | `&=` | 대입 | x &= y |
| 3 | `^=` | 대입 | x ^= y |
| 3 | `|=` | 대입 | x `|=` y |

> `**`의 경우 `ECMAScript 2016`은 시험적 또는 제한된 기술입니다.<br>
> 괄호 내부의 표현식은 나머지 표현식에서 값이 계산되기 전에 완전히 계산됩니다.
