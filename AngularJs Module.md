## AngularJs Modules
- modules defines an application
- its a container for the different pats of the application
- almost similar to a Main() method or classes.
- controller always belong to a module.
- module can export or hide components, directives,pipes and services.
- exported elements are to be used by other modules, while the ones that are not exported (hidden) are just used inside the module itself and cannot be directly accessed by other modules of our application.
- angularJS stops polluting global scope by containing specific functions in a module.
---
#### Creating a module
- angular object's module() method is used to create a module.
```html
<<!DOCTYPE html>
<html >
<head>
    <script src="~/Scripts/angular.js"></script>
</head>
<body ng-app="myApp">
    @* HTML content *@
    <script>
        var myApp = angular.module('myApp', []);

    </script>
</body>
</html>
```
- **Explanation :**
    - The `angular.module()` method creates an application module, where the first parameter is a module name which is same as specified by ng-app directive.T
    - The second parameter is an array of other dependent modules [].
    - passing an empty array because there is no dependency.
> **Note :**
> - The angular.module() method returns specified module object if no dependency is specified.
> - Therefore, specify an empty array even if the current module is not dependent on other module.

* * * * *

### Adding controller to a module
```html
<!DOCTYPE html>
<html >
<head>
    <script src="~/Scripts/angular.js"></script>
</head>
<body ng-app="myApp">
    <div ng-controller="myController">
        {{message}}
    </div>
    <script>
        var myApp = angular.module("myApp", []);

        myApp.controller("myController", function ($scope) {
            $scope.message = "Hello Angular World!";
        });
    </script>
</body>
</html>
```
- **Explanation :**
    - created a controller named "myController" using `myApp.controller()` method.
    - Here, myApp is an object of a module, and `controller()` method creates a controller inside "myApp" module.
    - So, "myController" will not become a global function.
* * * * *
### Modules in Separate Files
- can create separate JavaScript files for each module
```html
<!DOCTYPE html>
<html >
<head>
    <script src="~/Scripts/angular.js"></script>
</head>
<body ng-app="myApp">
    <div ng-controller="myController">
        {{message}}
    </div>
<script src="app.js" ></script>
<script src="myController.js" ></script>
</body>
</html>
```
- in app.js
```js
var myApp = angular.module("myApp", []);
```
- in myController.js
```js
myApp.controller("myController", function ($scope) {
    $scope.message = "Hello Angular World!";
});
```
### Add directives to modules
```html
<!DOCTYPE html>
<html>
<script src="http://ajax.googleapis.com/ajax/libs/angularjs/1.4.8/angular.min.js"></script>
<body>

<div ng-app="myApp" w3-test-directive></div>
<script>
var app = angular.module("myApp", []);
app.directive("w3TestDirective", function() {
    return {
        template : "This is a directive constructor. "
    };
});
</script>
</body>
</html>
```
---






