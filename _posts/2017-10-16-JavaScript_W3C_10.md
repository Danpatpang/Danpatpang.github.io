---
layout : post
title : "[JavaScript] W3C JavaScript (10)"
subtitle : "[JavaScript] JavaScript의 Assignment"
categories : Development
tags : JavaScript
comments : true

---

# JavaScript Assignment

> 이 포스트는 자습을 목적으로 [W3C school JavaScript](https://www.w3schools.com/js/default.asp)의 내용을 토대로 작성되었습니다.

_ _ _

### JavaScript Assignment Operators

대입 연산자는 JavaScript의 변수에 값을 대입합니다.

| Operator | Example | Same as |
|---|---|---|
| `=` | x=y | x=y |
| `+=` | x+=y | x=x+y |
| `-=` | x-=y | x=x-y |
| `*=` | x*=y | x=x*y |
| `/=` | x/=y | x=x/y |
| `$=` | x%=y | x=x%y |
| `<<=` | x<<=y | x=x<<y |
| `>>=` | x>>=y | x=x>>y |
| `>>>=` | x>>>=y | x=x>>>y |
| `&=` | x&=y | x= x&y |
| `^=` | x^=y | x=x^y |
| `|=` | x`|=`y | x=x`|`y |
| `**=` | x `**=` y  | x=x**y |

> `**=`연산자는 더 이상 browser의 stable이 아닙니다. 사용하지 않는 것이 좋습니다.

**Example**
```
<!DOCTYPE html>
<html>
<body>
    <p id="demo"></p> 
    <script>
        var x = 10;
        // add code here
        document.getElementById("demo").innerHTML = x;
    </script>
</body>
</html>
```