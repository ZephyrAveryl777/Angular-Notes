## AngularJS First Example

- AngularJS applications are a mix of HTML and JavaScript. The first thing you need is an HTML page.
```html
<!DOCTYPE html>  
<html>  
<head>  
.  
.  
</head>  
<body>  
.  
.  
</body>  
</html>  
```

- Second, you need to include the AngularJS JavaScript file in the HTML page so we can use AngularJS:

``` html
<!DOCTYPE html>  
<html>  
<head>  
<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.2.5/angular.min.js"></script>  
</head>  
<body>  
.  
.  
</body>  
</html>  
```

> **Note:**
> - You should always use the latest version of AngularJS, so it is not necessary to use the same version as the above example.

###  First Example

- Following is a simple "Hello Word" example made with AngularJS.
- It specifies the Model, View, Controller part of an AngularJS app. 

#### Model Part
```html
<!DOCTYPE html>  
<html lang="en">  
<head>  
<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.2.5/angular.min.js"></script>  
</head>  
<body ng-app="myapp">  
<div ng-controller="HelloController" >  
<h2>Hello {{helloTo.title}} !</h2>  
</div>  

<script>  
angular.module("myapp", [])  
.controller("HelloController", function($scope) {  
14. $scope.helloTo = {};  
15. $scope.helloTo.title = "World, AngularJS";  
16. } );  
</script>  
</body>  
</html>   
```

#### View Part
```html
<div ng-controller="HelloController" >  
<h2>Hello {{helloTo.title}} !</h2>  
</div>  
```
#### Controller Part
```html
<script>  
angular.module("myapp", [])  
.controller("HelloController", function($scope) {  
$scope.helloTo = {};  
$scope.helloTo.title = "World, AngularJS";  
});  
</script>
```
- Typical Example of Angular Application
![Angular Application](https://www.tektutorialshub.com/wp-content/uploads/2016/08/Angular-2-Architecture-Overview-and-Concepts.png)

---
