## AngularJS Expression

- AngularJS expression is like JavaScript expression surrounded with braces - {{ expression }}.
- AngularJS evaluates the specified expression and binds the result data to HTML. 
- these can contain literals, operators and variables like JavaScript expression.
- **Example:** `Expression`
```html
<!DOCTYPE html>
<html >
<head>
    <script src="~/Scripts/angular.js"></script>
</head>
<body >
    <h1>AngularJS Expression Demo:</h1>
    <div ng-app>
        2 + 2 = {{2 + 2}} <br />
        2 - 2 = {{2 - 2}} <br />
        2 * 2 = {{2 * 2}} <br />
        2 / 2 = {{2 / 2}}
    </div>
</body>
</html>
<!--
Result:
2 + 2 = 4
2 - 2 = 0
2 * 2 = 4
2 / 2 = 1
--->
```
> **Note :**
> - If you remove the directive `ng-app`, HTML will display the expression without solving it
---
### Difference between AngularJS expressions and JavaScript expression
1.  AngularJS expression cannot contain conditions, loops, exceptions or regular expressions e.g. if-else, ternary, for loop, while loop etc.
2.  AngularJS expression cannot declare functions.
3.  AngularJS expression cannot contain comma or void.
4.  AngularJS expression cannot contain return keyword.

- AngularJS expression contains literals of any data type.
- **Example: Expression**
```html
<html >
<head>
    <script src="~/Scripts/angular.js"></script>
</head>
<body >
    <h1>AngularJS Expression Demo:</h1>
    <div ng-app>
        {{"Hello World"}}<br />
        {{100}}<br />
        {{true}}<br />
        {{10.2}}
    </div>
</body>
</html>
<!---
Result:
Hello World
100
True
10.2
--->
```
- AngularJS expression can contain arithmetic operators which will produce the result based on the type of operands, similar to JavaScript:
- **Example: Expression**
```html
<!DOCTYPE html>
<html >
<head>
    <script src="~/Scripts/angular.js"></script>
</head>
<body >
    <div ng-app>
        {{"Hello" + " World"}}<br />
        {{100 + 100 }}<br />
        {{true + false}}<br />
        {{10.2 + 10.2}}<br />
    </div>
</body>
</html>
<!---
Result:
Hello World
200
1
20.4
-->
```
- AngularJS expression can contain variables declared via ng-init directive.
- The `ng-init` directive is used to declare AngularJS application variables of any data type.
- **Example: Expression**
```html
<!DOCTYPE html>
<html >
<head>
    <script src="~/Scripts/angular.js"></script>
</head>
<body >
    <div ng-app ng-init="greet='Hello World!'; amount= 10000;rateOfInterest = 10.5; duration=10;  myArr = [100, 200]; person = { firstName:'Steve', lastName :'Jobs'}">
        {{ (amount * rateOfInterest * duration)/100 }}<br />
        {{myArr[1]}} <br />
        {{person.firstName + " " + person.lastName}}
    </div>
</body>
</html>
<!---
Result:
10500
200
Steve Jobs
-->
```
---
### AngularJS Strings
```html
<!DOCTYPE html>
<html>
<script src="http://ajax.googleapis.com/ajax/libs/angularjs/1.4.8/angular.min.js"></script>
<body>
<div ng-app="" ng-init="firstName='A1';lastName='A2'">
<p>My full name is: {{ firstName + " " + lastName }}</p>
</div>
</body>
</html>
```
- Same example with `ng-bind`
```html
<!DOCTYPE html>
<html>
<script src="http://ajax.googleapis.com/ajax/libs/angularjs/1.4.8/angular.min.js"></script>
<body>
<div ng-app="" ng-init="firstName='A1';lastName='B1'">
<p>My full name is: <span ng-bind="firstName + ' ' + lastName"></span></p>
</div>
</body>
</html>
```
---
### AngularJS Objects
```html
<!DOCTYPE html>
<html>
<script src="http://ajax.googleapis.com/ajax/libs/angularjs/1.4.8/angular.min.js"></script>
<body>
<div ng-app="" ng-init="person={firstName:'A1',lastName:'A2'}">
<p>My name is {{ person.firstName }}</p>
</div>
</body>
</html>
```
- using `ng-bind`
```html
<!DOCTYPE html>
<html>
<script src="http://ajax.googleapis.com/ajax/libs/angularjs/1.4.8/angular.min.js"></script>
<body>
<div ng-app="" ng-init="person={firstName:'Sonoo',lastName:'Jaiswal'}">
<p>The name is <span ng-bind="person.firstName"></span></p>
</div>
</body>
</html>
```
---
### AngularJs Arrays
```html
<!DOCTYPE html>
<html>
<script src="http://ajax.googleapis.com/ajax/libs/angularjs/1.4.8/angular.min.js"></script>
<body>
<div ng-app="" ng-init="points=[1,15,19,2,40]">
<p>The first result is {{ points[0] }}</p>
</div>
</body>
</html>
```
- using `ng-bind`
```html
<!DOCTYPE html>
<html>
<script src="http://ajax.googleapis.com/ajax/libs/angularjs/1.4.8/angular.min.js"></script>
<body>
<div ng-app="" ng-init="points=[1,15,19,2,40]">
<p>The first result is <span ng-bind="points[0]"></span></p>
</div>
</body>
</html>
```
---
