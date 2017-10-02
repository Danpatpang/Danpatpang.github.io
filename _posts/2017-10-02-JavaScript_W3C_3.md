---
layout : post
title : "[JavaScript] W3C JavaScript (3)"
subtitle : "[JavaScript] JavaScript의 Output"
categories : Development
tags : JavaScript
commens : ture

---

# JavaScript Output

> 이 포스트는 자습을 목적으로 [W3C school JavaScript](https://www.w3schools.com/js/default.asp)의 내용을 토대로 작성되었습니다.

_ _ _

### JavaScirpt Diplay 가능성

JavaScript는 데이터들을 여러가지 방법으로 보여줄 수 있습니다.
+ HTML의 요소에 작성하는, `innerHTML`
+ HTML의 출력에 사용되는, `documnet.write()`
+ 경고 상자를 보여주는, `window.alert()`
+ 콘솔 브라우저에 보여주는, `console.log()`

### `innerHTML`의 사용

HTML의 요소에 접근하기 위해, JavaScript는 `document.getElementById(id)`라는 메서드를 사용합니다.
여기서 id 속성은 HTML 요소로 정의되며, `innerHTML`을 사용하여 HTML의 컨텐츠를 정의할 수 있습니다.

**Example**
```
<!DOCTYPE html>
<html>
    <body>
        <h2>My First Web Page</h2>
        <p>My First Paragraph.</p>
        <p id="demo"></p>
        <script>
            document.getElementById("demo").innerHTML = 5 + 6;
        </script>
    </body>
</html>
```
> HTML 요소의 innerHTML 속성을 변경하는 것은 데이터를 HTML로 표시하는 일반적인 방법입니다.

### `document.wirte()`의 사용
`document.write()`은 테스팅을 목적으로 사용하기 편리합니다.

**Example**

```
<!DOCTYPE html>
<html>
    <body>
        <h2>Testing</h2>
        <script>
            document.write(5 + 6);
        </script>
    </body>
</html>
```

위 예제의 결과는 다음과 같습니다.
```
Testing
11
```
하지만, 주의해야할 점은 HTML문서가 완전히 로드된 후, `document.write()`를 사용하게 되면 기존의 HTML문서가 사라지게 됩니다.

**Example**
```
<!DOCTYPE html>
<html>
    <body>
        <h2>Testing</h2>
        <button onclick="document.write(5+6)" > Click </button>
    </body>
</html>
```
위의 예제는 `document.write()`를 button으로 변형한 것입니다.
( `onclick` 속성의 경우, javaScirpt로 이루어지므로 script문을 따로 사용할 필요가 없습니다.)
위의 실행결과는 `11`이 나오게 됩니다.
`Testing`은 문서가 완전히 로드된 후 이므로 사라지게 됩니다.
이 때문에, `document.write()`는 테스트 용으로만 사용하는 것이 좋습니다.

### `window.alert()`의 사용
`window.alert()`은 데이터를 경고 창에 보여주고 싶을 때 사용합니다.

**Example**
```
<!DOCTYPE html>
<html>
    <body>
        <h2>My First Web Page</h2>
        <p>My first paragraph.</p>
        <script>
            window.alert(5 + 6);
        </script>
    </body>
</html>
```

### `console.log()`의 사용

`console.log()`는 디버깅을 목적으로 사용되며, 콘솔 창에서 데이터를 확인할 수 있습니다.

**Example**
```
<!DOCTYPE html>
<html>
    <body>
    	<p>Chrome browser의 사용자일 경우 F12를 눌려보세요.</p>
        <script>
            console.log(5 + 6);
        </script>
    </body>
</html>
```
위의 예제의 결과 값은 HTML에서 확인 할 수 없으며, 각 브라우저의 콘솔 창에서 확인 가능합니다.
Chrome Browser의 사용자의 F12를 누르면 Developer Tools라는 창이 나옵니다.
이 창은 현재 보고 있는 페이지의 소스, 네트워크, 메모리 사용등을 볼 수 있습니다.
창의 하단 쪽에 보시면 Console이라는 버튼이 있습니다.
이 버튼을 클릭하시면 `11` 이라는 결과 값을 확인 할 수 있습니다.
> 콘솔에 대한 자세한 내용은 뒤에서 다루겠습니다.