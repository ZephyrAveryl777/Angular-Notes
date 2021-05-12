## AngularJs Controller
- controller is a Javascript function that maintains the application data and behavior data using `$scope` object
- can attach properties and methods to the `$scope` object inside a controller function
- while attaching the controller will add/update the data and attach behaviors to HTML elements.
---
### **`$scope`**
- `$scope` object can be considered as a glue between the controller and HTML
- `ng-controller` directive is used to specify a controller in HTML element
- ![Scope](https://cdn.journaldev.com/wp-content/uploads/2014/11/MVC-angular.png)
- **Example of AngularJS Controller using `$scope`:**
```html
<!DOCTYPE html>
<html >
<head>
    <title>AngularJS Controller</title>
    <script src="~/Scripts/angular.js"></script>
</head>
<body ng-app="myNgApp">
    <div ng-controller="myController">
        {{message}}
    </div>
    <script>
        var ngApp = angular.module('myNgApp', []);

        ngApp.controller('myController', function ($scope) {
            $scope.message = "Hello World!";
        });
    </script>
</body>
</html>
<!-- Output
Hello World!
---->
```
> **Note :**
> - the `$` sign is used as prefix in all the built-in objects in AngularJS
> - AngularJS injects a different `$scope` object to each controller function.
> - data and methods attached to `$scope` inside one controller cannot be accessed in another controller.
> -  it also injects other services if included as a parameter of controller function.

![Illustration of Angular $scope](https://www.tutorialsteacher.com/Content/images/ng/ng-controller.png)

### **`$rooSpace`**
- an angularJS application has a single `$rootScope`.
- all other $scope objects are child objects.
- properties and methods attached to `$rootSpace` will be available to all the controllers.
- **Example of `$rootSpace`**
```html
<!DOCTYPE html>
<html>
<head>
    <title>AngualrJS Controller</title>
    <script src="~/Scripts/angular.js"></script>
</head>
<body ng-app="myNgApp">
    <div ng-controller="parentController">
        Controller Name: {{controllerName}} <br />
        Message: {{message}} <br />
        <div style="margin:10px 0 10px 20px;" ng-controller="childController">
            Controller Name: {{controllerName}} <br />
            Message: {{message}} <br />
        </div>
    </div>
    <div  ng-controller="siblingController">
        Controller Name: {{controllerName}} <br />
        Message: {{message}} <br />
    </div>
    <script>
        var ngApp = angular.module('myNgApp', []);

        ngApp.controller('parentController', function ($scope, $rootScope) {
            $scope.controllerName = "parentController";
            $rootScope.message = "Hello World!";
        });

        ngApp.controller('childController', function ($scope) {
            $scope.controllerName = "childController";
        });

        ngApp.controller('siblingController', function ($scope) {

        });
    </script>
</body>
</html>
<!--Output
Controller Name: parentController
Message: Hello World!
    Controller Name: childController
    Message: Hello World!
Controller Name:
Message: Hello World!
--->
```
- `$scope` object contains various methods.

| Method             | Description                                                                                                               |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------- |
| $new()             | Creates new child scope.                                                                                                  |
| $watch()           | Register a callback to be executed whenever model property changes.                                                       |
| $watchGroup()      | Register a callback to be executed whenever model properties changes. Here, specify an array of properties to be tracked. |
| $watchCollection() | Register a callback to be executed whenever model object or array property changes.                                       |
| $digest()          | Processes all of the watchers of the current scope and its children.                                                      |
| $destroy()         | Removes the current scope (and all of its children) from the parent scope.                                                |
| $eval()            | Executes the expression on the current scope and returns the result.                                                      |
| $apply()           | Executes an expression in angular outside the angular framework.                                                          |
| $on()              | Register a callback for an event.                                                                                         |
| $emit()            | Dispatches the specified event upwards till $rootScope.                                                                   |
| $broadcast()       | Dispatches the specified event downwards to all child scopes.                                                             |

### **`$watch`**
- `$watch` event will be raised whenever a model property is changed
- **Example of `$watch`**
```html
<!DOCTYPE html>
<html>
<head>
    <script src="~/Scripts/angular.js"></script>
</head>
<body ng-app="myNgApp">
    <div ng-controller="myController">
        Enter Message: <input type="text" ng-model="message" /> <br />
        New Message: {{newMessage}} <br />
        Old Message: {{oldMessage}}
    </div>
    <script>
        var ngApp = angular.module('myNgApp', []);

        ngApp.controller('myController', function ($scope) {
            $scope.message = "Hello World!";

            $scope.$watch('message', function (newValue, oldValue) {
                $scope.newMessage = newValue;
                $scope.oldMessage = oldValue;
            });
        });
    </script>
</body>
</html>
```
---
### Guidelines for use of Controllers
-   Use controllers to set up the initial state of the $scope object and add behavior to that object.
-   Do not use controllers to manipulate DOM. It should contain only business logic. Use **Data Binding** and **Directives** for DOM manipulation.
-   Do not use controllers to format inputs -- Use **Angular Form controls.**
-   Do not use to filter output -- Use **Angular Filters.**
-   Do not use controllers to share code or state across controllers -- Use **Angular Services.**
-   Do not manage the life cycle of other components using controllers.

---
### Adding Behavior to Controller
- can attach multiple methods to the scope object inside a controller
- these can be used for event handling or other purposes
- **Example of Event Handling :**
```html
<!DOCTYPE html>
<html>
<head>
    <title>AngularJS Controller</title>
    <script src="~/Scripts/angular.js"></script>
</head>
<body ng-app="myNgApp">
    <div ng-controller="myController">
        Enter Message: <input type="text" ng-model="message" /> <br />
        <button ng-click="showMsg(message)">Show Message</button>
    </div>
    <script>
        var ngApp = angular.module('myNgApp', []);

        ngApp.controller('myController', function ($scope) {
            $scope.message = "Hello World!";

            $scope.showMsg = function (msg) {
                alert(msg);
            };
        });
    </script>
</body>
</html>
```
- **Explanation of code  :**
    - attached **`showMsg()`** function to the scope object.
    - **`showMsg()`** is called on button click
    - **`ng-click`**directive is used to handle click event in AngularJS
> **Note :**
> - the properties and methods attached to the scope object inside a particular controller is only available to the HTML elements and its child elements where ng-controller is applied

- **Example of controller availability :**
```html
<!DOCTYPE html>
<html>
<head>
    <title>AngularJS Controller</title>
    <script src="~/Scripts/angular.js"></script>
</head>
<body ng-app="myNgApp">
    <div id="div1" ng-controller="myController">
        Message: {{message}} <br />
        <div id="div2">
            Message: {{message}}
        </div>
    </div>
    <div id="div3">
        Message: {{message}}
    </div>
    <div id="div4" ng-controller="anotherController">
        Message: {{message}}
    </div>
    <script>
        var ngApp = angular.module('myNgApp', []);

        ngApp.controller('myController', function ($scope) {
            $scope.message = "This is myController";
        });

        ngApp.controller('anotherController', function ($scope) {
            $scope.message = "This is anotherController";
        });
    </script>
</body>
</html>
<!--- Output
Message: This is myController
Message: This is myController
Message:
Message: This is anotherController
------>
```
- **Explanation :**
    - `message` property is defined inside `myController` hence available to `div1` and div2 but not `div3` and `div4`

---
### Attach Complex Object
- can attach an object to the `$scope` inside controller and display value of its properties in HTML
- **Example :**
```html
<!DOCTYPE html>
<html>
<head>
    <title>AngularJS Controller</title>
    <script src="~/Scripts/angular.js"></script>
</head>
<body ng-app="myNgApp">
    <h2>Student Information:</h2>
    <div ng-controller="myController">
        First Name: {{student.firstName}} <br />
        Last Name: {{student.lastName}}
    </div>
    <script>
         var ngApp = angular.module('myNgApp', []);

        ngApp.controller('myController', function ($scope) {
            $scope.student = { firstName: 'James', lastName: 'Bond' };
        });
    </script>
</body>
</html>
<!--- Output
First Name: James
Last Name: Bond
 ----->
```
---
### Nested Controllers
- Controllers enclosed within another is called Nested Controllers
- in this child controller will inherit the parent controller's scope object.
- hence child controller can access properties added in parent controller but parent controller cannot access properties added in child controller.
- mainly used for event handling
- **Example of Nested Controllers :**
```html
<!DOCTYPE html>
<html>
<head>
    <title>AngualrJS Controller</title>
    <script src="~/Scripts/angular.js"></script>
</head>
<body ng-app="myNgApp">
    <div ng-controller="parentController">
        Message: {{message1}}
        <div ng-controller="childController">
            Parent Message: {{message1}}  </br>
            Child Message: {{message2}}
        </div>
        Child Message: {{message2}}
    </div>
    <script>
         var ngApp = angular.module('myNgApp', []);

        ngApp.controller('parentController', function ($scope) {
            $scope.message1 = "This is parentController";
        });

        ngApp.controller('childController', function ($scope) {
            $scope.message2 = "This is childController";
        });
    </script>
</body>
</html>
<!--Output
Message: This is parentController
Parent Message: This is parentController
Child Message: This is childController
Child Message:
 ---->
```
---
### Minification Syntax
- All the script files in AngularJS application should be minified in the production environment.
- minification process shortens parameter and function names.
- in some cases the minification process changes the parameter names which breaks the angular framework as it needs the same parameter name for built-in objects such as $scope.
- to prevent the above error, give the name fo the parameter and controller function in square brackets [], parameter name will be the first member and last member will be action controller function in square brackets
- **Example :**
```html
<!DOCTYPE html>
<html >
<head>
    <script src="~/Scripts/angular.js"></script>
</head>
<body ng-app="myNgApp">
    <div ng-controller="myController">
        {{message}}
    </div>
<script>
    var ngApp = angular.module('myNgApp', []);

    ngApp.controller('myController', ['$scope', function ($scope) {
        $scope.message = "Hello World!";
    }]);
</script>
</body>
```
----
