---
layout : post
title : "[JavaScript] W3C JavaScript (8)"
subtitle : "[JavaScript] JavaScript의 Operators"
categories : Development
tags : JavaScript
comments : true

---

# JavaScript Operators

> 이 포스트는 자습을 목적으로 [W3C school JavaScript](https://www.w3schools.com/js/default.asp)의 내용을 토대로 작성되었습니다.

_ _ _

### JavaScript Arithmetic Operators

산술 연산자는 숫자의 산술을 수행할 때 사용됩니다.

| Operator | Description |
|:-:|---|
| + | 덧셈 |
| - | 뺄셈 |
| * | 곱셈 |
| / | 나눗셈 |
| % | 나머지 |
| ++ | 증가 |
| -- | 감소 |

> 산술 연산자의 자세한 부분은 [JS Arithmetic](https://www.w3schools.com/js/js_arithmetic.asp) chapter에서 다루겠습니다.

### JavaScript Assignment Operators

대입 연산자는 JavaScript변수에 값을 대입합니다.

| Operator | Example | Same as |
|:-:|---|---|
| = | x = y | x = y |
| += | x += y | x = x + y |
| -= | x -= y | x = x - y |
| *= | x *= y | x = x * y |
| /= | x/= y | x = x / y |
| %= | x%= y | x = x % y |

### JavaScript String Operators

`string`타입은 `+`과 `+=` 연산자를 사용할 수 있습니다.

**Example**
```
<script>
    var txt1 = "Dan";
    var txt2 = "Patpang";
    var txt3 = txt1 + txt2;
    document.write(txt3);
    txt1 += "Patpang"
    document.write(txt1);
</script>
```
> 문자열에 사용되는 `+`연산자는 연결 연산자라고 합니다.

### Adding Strings and Numbers

`+`연산자를 사용하여 문자와 숫자를 더할 수도 있습니다.

**Example**
```
<script>
	var x = 5 + 5;
    var y = 5 + 5 + "11";
    var z = "11" + 5 + 5;
</script>
```
> 문자열과 숫자를 더하게 된 결과 값은 문자열이 나오게 됩니다.
### JavaScript Comparison Operators

| Operator | Description |
|:-:|---|
| == | value 값이 같다. |
| === | value와 type이 같다. |
| != | value 값이 같지 않다. |
| !== | value 값 또는 type이 같지 않다. |
| > | 크다. |
| < | 작다. |
| >= | 이상이다. |
| <= | 이하이다. |
| ? | 삼항 조건 연산자 |
> 비교 연산자의 자세한 부분은 [JS Comparisons](https://www.w3schools.com/js/js_comparisons.asp)에서 다루겠습니다.

### JavaScript Logical Operators

| Operator | Description |
|:-:|---|
| && | AND |
| `||` | OR |
| ! | NOT |

### JavaScript Type Operators

| Operator | Description |
|:-:|---|
| typeof | 변수의 타입을 리턴합니다. |
| instanceof | 만약 객체의 인스턴스라면 객체의 타입을 리턴합니다. |

### JavaScript Bitwise Operators

비트 연산자는 32비트에서 작동합니다. 연산 후 피연산자는 32비트 숫자로 변환되며, 결과는 JavaScript의 숫자로 다시 반환됩니다.

| Operaotr | Description | Example | Same as | Result | Decimal |
|:-:|---|---|---|---|---|
| & | AND | 5 & 1 | 0101 & 0001 | 0001 | 1 |
| `|` | OR | 5 `|` 1 | 0101`|`0001 | 0101 | 5 |
| ~ | NOT | ~5 | ~0101 | 1010 | 10 |
| ^ | XOR | 5 ^ 1 | 0101 ^ 0001 | 0100 | 4 |
| `<<` | 좌측으로 shift 0으로 채움 | 5 `<<` 1 | 0101 `<<` 1 | 1010 | 10 |
| `>>` | 우측으로 shift 부호에 맞게 채움 | -5 `>>` 1 | 1101 `>>` 1 | 1110 | -6 |
| `>>>` | 우륵으로 shift 0으로 채움 | -5 `>>>` 1 | 1101 `>>>` 1 | 0110 | 6 |

> `>>`의 경우 부호를 생각하지만, `>>>`은 부호를 생각하지 않습니다.<br>