## AngularJS Events
- AngularJS includes certain directives which can be used to provide custom behavior on various DOM events, such as click, dblclick, mouseenter etc.
- commonly used AngularJS event directives.

| Event Directive |
| --- |
| ng-blur |
| ng-change |
| ng-click |
| ng-dblclick |
| ng-focus |
| ng-keydown |
| ng-keyup |
| ng-keypress |
| ng-mousedown |
| ng-mouseenter |
| ng-mouseleave |
| ng-mousemove |
| ng-mouseover |
| ng-mouseup |


### **`ng-click`**
- `ng-click` directive is used to provide event handler for click event. 
```html
<!DOCTYPE html>
<html >
<head>
    <script src="~/Scripts/angular.js"></script>
</head>
<body ng-app="myApp">
    <div ng-controller="myController">
        Enter Password: <input type="password" ng-model="password" /> <br />

        <button ng-click="DisplayMessage(password)">Show Password</button
    </div>
    <script>
        var myApp = angular.module('myApp', []);

        myApp.controller("myController", function ($scope, $window) {

            $scope.DisplayMessage = function (value) {
                $window.alert(value)
            }
        });
    </script>
</body>
</html>
```
- **Explanation:**
    - ng-click directive is used to call a `DisplayMessage()` function with the 'password' parameter when a user clicks a button.
    - A 'password' is a model property defined using `ng-model` directive in the input box.
    - The `DisplayMessage()` function is attached to a `$scope` object in myController, so it will be accessible from button click as button comes under myController. The `$window` service is used to display an alert.

### Mouse Events
```html
<!DOCTYPE html>
<html>
<head>
    <script src="~/Scripts/angular.js"></script>
    <style>
        .redDiv {
            width: 100px;
            height: 100px;
            background-color: red;
            padding:2px 2px 2px 2px;
        }
        .yellowDiv {
            width: 100px;
            height: 100px;
            background-color: yellow;
            padding:2px 2px 2px 2px;
        }
    </style>
</head>
<body ng-app>
        <div ng-class="{redDiv: enter, yellowDiv: leave}" ng-mouseenter="enter=true;leave=false;" ng-mouseleave="leave=true;enter=false">
            Mouse <span ng-show="enter">Enter</span> <span ng-show="leave">Leave</span>
        </div>
</body>
</html>
```
- *Explanation:*
    - `ng-class` directive includes map of CSS classes, so redDiv will be applied if enter=true and yellowDiv will be applied if leave=true.
    - `ng-mouseenter` directive sets 'enter' to true, which will apply redDiv class to the \<div> element.
    - In the same way, `ng-mouseleave` will set leave to true, which will apply yellowDiv class.

---
