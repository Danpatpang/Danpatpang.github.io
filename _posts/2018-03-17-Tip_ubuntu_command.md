---
layout : post
title : "[Tip] Ubuntu 폴더 구조 및 핵심 명령어"
subtitle : "우분투 폴더 구조 및 핵심 명령어를 알아보자"
categories : Tip
tags : Tip
comments : true

---
# AngularJS Modules

> 이 포스트는 자습을 목적으로 [W3C school AngularJS](https://www.w3schools.com/angular/default.asp)의 내용을 토대로 작성되었습니다.

_ _ _

AngularJS 모듈은 애플리케이션을 정의합니다. 모듈은 애플리케이션의 여러 부분과 컨트롤러를 담는 컨테이너입니다. 컨트롤러는 항상 모듈에 속합니다.

### Creating a Module

모듈은 AngularJS의 함수 `angular.module`에 의해 생성됩니다.
```
<div ng-app="myApp">...</div>
<script>
    var app = angular.module("myApp", []);
</script>
```
파라미터 "myApp"은 애플리케이션에서 실행될 HTML 요소를 나타냅니다.
이제 AngularJS 애플리케이션에 컨트롤러, 명령어, 필터 등 다양한 것을 추가할 수 있습니다.

### Adding a Controller

애플리케이션에 컨트롤러를 추가하고 `ng-controller` 명령어로 컨트롤러를 참조합니다.

**Example**
```
<div ng-app="myApp" ng-controller="myCtrl">
    {{ firstName + " " + lastName }}
</div>

<script>
    var app = angular.module("myApp", []);
    app.controller("myCtrl", function($scope) {
        $scope.firstName = "John";
        $scope.lastName = "Doe";
    });
</script>
```

### Adding a Directive

AngularJS는 애플리케이션에 기능을 추가할 수 있는 명령어 집합을 가지고 있습니다.
자세한 내용은 [AngularJS directive reference](https://www.w3schools.com/angular/angular_ref_directives.asp)에서 다루겠습니다.
또한, 모듈을 사용하여 애플리케이션에 직접 명령어를 추가 할 수 있습니다.

**Example**
```
<!DOCTYPE html>
<html>
    <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.6.4/angular.min.js">
    </script>
	<body>
	<div ng-app="myApp" direct></div>
	<script>
        var app = angular.module("myApp", []);
        app.directive("direct", function() {
            return {
                template : "I was made jjn a directive constructor!"
            };
        });
	</script>
	</body>
</html>
```

### Moudles and Controllers in Files
AngularJS 애플리케이션에서 모듈과 컨트롤러를 JavaScript파일에 저장하는 것이 일반적입니다. 이 예제에서 "myApp.js"는 모듈을 정의하고 "myCtrl.js"는 컨트롤러를 포함합니다.

**Example**
```
<!DOCTYPE html>
<html>
<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.6.4/angular.min.js"></script>
<body>
    <div ng-app="myApp" ng-controller="myCtrl">
        {{ firstName + " " + lastName }}
    </div>
    <script src="myApp.js"></script>
    <script src="myCtrl.js"></script>
</body>
</html>
```
```
//myApp.js
var app = angular.module("myApp",[]);
```
> 모듈 정의 안에 있는 `[]` 파라미터를 사용하여 종속 모듈을 정의 할 수 있습니다.
> `[]` 파라미터가 없으면 새 모듈을 만들지 않고 기존 모듈을 검색합니다.

```
//myCtrl.js
app.controller("myCtrl", function($scope) {
$scope.firstName = "Dan";
$scope.lastName = "patpang";
});
```

### Functions can Pollute the Global Namespace

전역 함수는 다른 script를 덮어쓰거나 파괴하기 쉬우므로 JavaScript에서 피해야 합니다. AngularJS 모듈은 모든 기능을 모듈에 로컬로 유지함으로써 이 문제를 줄입니다.

### When to Load the Library

HTML 애플리케이션에서 `<body>`태그의 끝 부분에 스크립트를 배치하는 것이 일반적이지만 AngularJS 라이브러리는 `<head>`의 시작 부분 또는 `<body>`의 첫 부분에 적는 것이 좋습니다. 이는 `angular.module` 라이브러리를 로드한 후에 호출을 컴파일 할 수 있기 때문입니다.

**Example**
```
<!DOCTYPE html>
<html>
<body>
    <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.6.4/angular.min.js"></script>
    <div ng-app="myApp" ng-controller="myCtrl">
    	{{ firstName + " " + lastName }}
    </div>
    <script>
        var app = angular.module("myApp", []);
        app.controller("myCtrl", function($scope) {
            $scope.firstName = "Dan";
            $scope.lastName = "patpang";
        });
    </script>
</body>
</html>
```