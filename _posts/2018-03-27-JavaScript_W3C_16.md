---
layout : post
title : "[JavaScript] W3C JavaScript (16)"
subtitle : "[JavaScript] JavaScript의 문자열"
categories : Development
tags : JavaScript
comments : true

---

# JavaScript Strings

> 이 포스트는 자습을 목적으로 [W3C school JavaScript](https://www.w3schools.com/js/default.asp)의 내용을 토대로 작성되었습니다.

_ _ _

JavaScript 문자열은 텍스트를 저장과 조작에 사용됩니다.

### JavaScript Strings
JavaScript 문자열은 따옴표 안에 0 개 이상의 문자로 작성됩니다.

**Example**
```
var x = "Dan patpang";
var y = "";
```
당신은 작은 따옴표 또는 큰 따옴표를 사용할 수 있습니다.

**Example**
```
var carname = "Volvo";
var carname2 = 'volvo';
```

당신은 문자열을 둘러싼 따옴표와 일치하지 않는 따옴표를 문자열 내에서 사용할 수 있습니다.

**Example**
```
var answer = "I'm Danpatpang";
var answer2 = 'You said "Hello, Dan"';
```

### String Length
문자열의 길이는 내장된 length 속성을 이용하여 찾을 수 있습니다.

**Example**
```
var txt = "how long?";
var txt_length = txt.length();
```

### Special Characters
문자열은 따옴표 내에서 작성되기 때문에, JavaScript는 다음 문자열을 잘못 이해합니다.

**Example**
```
var x = "you call me "Ji!", OK? "
```
이 스트링은 "you call me"를 자릅니다.
이 문제를 피하기 위한 해결책은, escape 문자 앞에 `\`를 써주는 것입니다.
백슬래쉬(`\`)escape문자는 특수 문자를 문자열 문자로 변환합니다.

| Code | Result | Description |
|---|---|---|
| \' | `'` | 작은 따옴표 |
| \" | `"` | 큰 따옴표 |
| \\ | `\` | 역 슬래쉬 |

문자열 `\"`은 문자열 내에 큰 따옴표로 삽입됩니다.

**Example**
```
var x = "you call me \"Ji!\", OK? "
```
JavaScript에는 유요한 여섯 가지의 이스케이프 문자가 더 있습니다.

| Code | Result |
|---|---|
| \b | 백 스페이스 |
| \f | 폼 피드 |
| \n | 새 줄 |
| \r | 캐리지 리턴 |
| \t | 수평 탭 |
| \v | 수직 탭 |

> 위의 6개의 이스케피ㅡ 문자는 원래 타자기, 팩스를 제어하도록 설계되었습니다. HTML에서는 의미가 없습니다.

### Breaking Long Code Lines


### String Can be Objects

> `x==y` 와 `x===y`의 차이를 주의하세요.<br/>
> 두 JavaScript 객체를 비교하는 것은 항상 false를 반환합니다.

**Example**
```
var x = "Dan patpang";
var y = "";
```
