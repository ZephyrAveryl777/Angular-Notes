## AngularJS Service
- AngularJS services are JavaScript functions for specific tasks, which can be reused throughout the application.

> - AngularJS built-in services starts with `$`, same as other built-in objects.

- AngularJS includes services for different purposes.
- AngularJS also allows to create custom service for applications.
- Most AngularJS services interact with the controller, model or custom directives.
- some services interact with view (UI) also for UI specific tasks.
- ![Service Description](https://dhananjay25.files.wordpress.com/2015/02/image6.png)

![Angular Services](https://www.tutorialsteacher.com/Content/images/ng/ng-service.png)

---
### Services
- list of all the **built-in** AngularJS services.

| $anchorScroll  | $exceptionHandler          | $interval    | $rootScope       |
| -------------- | -------------------------- | ------------ | ---------------- |
| $animate       | $filter                    | $locale      | $sceDelegate     |
| $cacheFactory  | $httpParamSerializer       | $location    | $sce             |
| $templateCache | $httpParamSerializerJQLike | $log         | $templateRequest |
| $compile       | $http                      | $parse       | $timeout         |
| $controller    | $httpBackend               | $q           | $window          |
| $document      | $interpolate               | $rootElement |

- All the Angular services are lazy instantiated and singleton.
- in simple AngularJS instantiates a service when an application component depends on it.
- all the components share the same instance of a service.

---
### **`$http`**
- `$http` services is used to send or receive data by using browser's `XMLHttpRequest` or `JSONP`
- `$http` is a service as an object.

| Method         | Description                  |
| -------------- | ---------------------------- |
| $http.get()    | Perform Http GET request.    |
| $http.head()   | Perform Http HEAD request.   |
| $http.post()   | Perform Http POST request.   |
| $http.put()    | Perform Http PUT request.    |
| $http.delete() | Perform Http DELETE request. |
| $http.jsonp()  | Perform Http JSONP request.  |
| $http.patch()  | Perform Http PATCH request.  |

----
### **`$http.get()`**
- `$http.get()` method sends http GET request to the remote server and retrieves the data.
- Signature: `HttpPromise $http.get(url)`
- `$http.get()` method returns HttpPromise object, which includes various methods to process the response of http GET request.
- **Example :**
```html
<!DOCTYPE html>
<html>
<head>
    <script src="~/Scripts/angular.js"></script>
</head>
<body ng-app ="myApp">
    <div>
        <div ng-controller="myController">
           Response Data: {{data}} <br />
           Error: {{error}}
        </div>
    </div>
    <script>
        var myApp = angular.module('myApp', []);

        myApp.controller("myController", function ($scope, $http) {

            var onSuccess = function (data, status, headers, config) {
                $scope.data = data;
            };

            var onError = function (data, status, headers, config) {
                $scope.error = status;
            }

            var promise = $http.get("/demo/getdata");

            promise.success(onSuccess);
            promise.error(onError);

        });
    </script>
</body>
</html>
```
- *Explanation:*
    - 'myController' controller includes `$http` parameter, so that it can be used to send GET request.
    - AngularJS automatically injects $scope parameter at runtime.
    - The `$http.get()` method returns HttpPromise which includes methods like `success()` and `error()`.
    - The `success()` method registers a callback method which is called when a request completes successfully.
    - The `error()` method registers a callback method which is called when a request fails and returns an error.
    - The `onSuccess()` method above, attaches the response data to the `$scope`.
    - The `onError()` method attaches status property to the `$scope`.
    - These methods can be called in chain.
- *Example :*
```html
<!DOCTYPE html>
<html>
<head>
    <script src="~/Scripts/angular.js"></script>
</head>
<body ng-app ="myApp">
    <div>
        <div ng-controller="myController">
           Response Data: {{data}} <br />
           Error: {{error}}
        </div>
    </div>
    <script>
        var myApp = angular.module('myApp', []);

        myApp.controller("myController", function ($scope, $http) {

            var onSuccess = function (data, status, headers, config) {
                $scope.data = data;
            };

            var onError = function (data, status, headers, config) {
                $scope.error = status;
            }

            var promise = $http.get("/demo/getdata").success(onSuccess).error(onError);

        });
    </script>
</body>
</html>
```
---
### **`$http.post`**
- `$http.post()` method sends Http POST request to the remote server to submit and retrieve the data.
- Signature: HttpPromise `$http.post(url, dataToSubmit);`
- **Example:**
```html
<!DOCTYPE html>
<html >
<head>
    <script src="~/Scripts/angular.js"></script>
</head>
<body ng-app="myApp">
    <div ng-controller="myController">
        Response Data: {{data}} <br />
        Error: {{error}}
    </div>
    <script>
        var myApp = angular.module('myApp', []);

        myApp.controller("myController", function ($scope, $http) {

            var onSuccess = function (data, status, headers, config) {
                $scope.data = data;
            };

            var onError = function (data, status, headers, config) {
                $scope.error = status;
            }

            $http.post('/demo/submitData', { myData: 'Hello World!' })
                 .success(onSuccess)
                 .error(onError);

        });
    </script>
</body>
</html>
```
---
### **`$http()`**
```html
<!DOCTYPE html>
<html >
<head>
    <script src="~/Scripts/angular.js"></script>
</head>
<body ng-app="myApp">
    <div ng-controller="myController">
            Response Data: {{data}} <br />
        Error: {{error}}

    </div>
    <script>
       var myApp = angular.module('myApp', []);

        myApp.controller("myController", function ($scope, $http) {

            var onSuccess = function (data, status, headers, config) {
                $scope.data = data;
            };

            var onError = function (data, status, headers, config) {
                $scope.error = status;
            }

           var getReq = {
                    method: 'GET',
                    url: '/demo/getdata'
                };

            $http(getReq).success(onSuccess).error(onError);

            var postReq = {
                    method: 'POST',
                    url: '/demo/submitData',
                    data: { myData: 'test data' }
                };

            $http(postReq).success(onSuccess).error(onError);

        });
    </script>
</body>
</html>
```
---
### **`$log()`**
- AngularJs includes logging service `$log`, which logs the messages to the browser's console.
- The `$log` service includes different methods to log the error, information, warning or debug information.
- It can be useful in debugging and auditing.
```html
<!DOCTYPE html>
<html>
<head>
    <script src="~/Scripts/angular.js"></script>
</head>
<body ng-app="myApp" >
    <div ng-controller="myController">
        <p>Please check the browser console for the logging information.</p>
    </div>
    <script>
        var myApp = angular.module('myApp', []);

        myApp.controller("myController", function ($log) {

            $log.log('This is log.');
            $log.error('This is error.');
            $log.info('This is info.');
            $log.warn('This is warning.');
            $log.debug('This is debugging.');

        });
    </script>
</body>
</html>
```
---
### **`$interval()`**
- AngularJS includes $interval service which performs the same task as `setInterval()` method in JavaScript.
-  `$interval` is a wrapper for `setInterval()` method, so that it will be easy to override, remove or mocked for testing.
- `$interval` service executes the specified function on every specified milliseconds duration.
- Signature: `$interval(fn, delay, [count], [invokeApply], [Pass]);`
- **Example**
```html
<!DOCTYPE html>
<html >
<head>
    <script src="~/Scripts/angular.js"></script>
</head>
<body ng-app="myApp">
    <div ng-controller="myController">
        {{counter}}
    </div>
    <script>
        var myApp = angular.module('myApp', []);

        myApp.controller("myController", function ($scope, $interval) {
            $scope.counter = 0;

            var increaseCounter = function () {
                $scope.counter = $scope.counter + 1;
            }

            $interval(increaseCounter, 1000);
        });
    </script>
</body>
</html>
```
- *Explanation*
    - `$interval` service calls `increaseCounter()` function on every 1000 milliseconds.
    - `increaseCounter()` function increases the $scope.counter property by 1.
    - counter increases on every milliseconds.

#### Execution Count
- `$interval` service also executes the specified function for the specified number of times as count parameter.
- **Example**
```html
<!DOCTYPE html>
<html >
<head>
    <script src="~/Scripts/angular.js"></script>
</head>
<body ng-app="myApp">
    <div ng-controller="myController">
        {{counter}}
    </div>
    <script>
        var myApp = angular.module('myApp', []);

        myApp.controller("myController", function ($scope, $interval) {
            $scope.counter = 0;

            var increaseCounter = function () {
                $scope.counter = $scope.counter + 1;
            }

            $interval(increaseCounter, 1000, 10);
        });
    </script>
</body>
</html>
```
- *Explanation*
    - `increaseCounter()` method will be executed on each 1000 milliseconds but not more than 10 times.

#### Cancel Execution
- `$interval` service returns an object of HttpPromise which can be used to stop the counter by using `$interval.cancel(promise)` method.
- **Example**
```html
<!DOCTYPE html>
<html >
<head>
    <script src="~/Scripts/angular.js"></script>
</head>
<body ng-app="myApp">
    <div>
        <div ng-controller="myController">
            {{counter}} <br /><br />
            <button ng-click="cancel()">Cancel</button>
        </div>

    </div>
    <script>
        var myApp = angular.module('myApp', []);

        myApp.controller("myController", function ($scope, $interval) {
             $scope.counter = 0;

            var increaseCounter = function () {
                $scope.counter = $scope.counter + 1;
            }

            var promise = $interval(increaseCounter, 1000);

            $scope.cancel = function () {
                $interval.cancel(promise);

                $scope.counter = "Cancelled!";
            };

        });
    </script>
</body>
</html>
```
---
### **`$window()`**
- `$window` service refers to the browser window object.
- `$window` service is a wrapper around window object, so that it will be easy to override, remove or mocked for testing.
- It is recommended to use` $window` service in AngularJS instead of global window object directly.
- **Example**
```html
<!DOCTYPE html>
<html>
<head>
    <script src="~/Scripts/angular.js"></script>
</head>
<body ng-app="myApp" ng-controller="myController">
    <button ng-click="DisplayAlert('Hello World!')">Display Alert</button>
    <button ng-click="DisplayPrompt()">Display Prompt</button>
    <script>
        var myApp = angular.module('myApp', []);

        myApp.controller("myController", function ($scope, $window) {

            $scope.DisplayAlert = function (message) {
                $window.alert(message);
            }

            $scope.DisplayPrompt = function () {
                var name = $window.prompt('Enter Your Name');

                $window.alert('Hello ' + name);
            }

        });
    </script>
</body>
</html>
```
---
### Creating and Registering custom Angular Services
- Angular services are created by registering them with the module they are going to operate in.
- There are three ways to create an angular service. They are using **Factory**, **Service** and **Provider**
- Creating a module named **app** using the following syntax
```js
var app = angular.module("app", []);
```
### AngularJS service using Factory
- The most common way to create a service is by using the Module’s Factory API.
- We use the factory method to create an object, add properties to it and return the same object.
- Later it can be injected to the components like controller, service, filter or directive.
```js
app.factory('factoryName',function(){
return factoryObj; });
```
### Create angular Services using Services
- This is instantiated with the new keyword, will be provided with an instance of the function passed to the service.
- This object instance becomes the service object that AngularJS registers and is injected to the required components.
- We use this keyword to add properties and functions to this service object. Unlike factory method, this does not return anything.
- General syntax of using `Service`
```js
app.service('serviceName',function(){ });
```
### AngularJS services example using Provider
- Providers are the only service you can pass into your `.config()` function.
- Providers are used when you want to provide module-wide configuration for your service object before making it available.
- It returns value by using `$get()` function.
```js
// syntax for creating a provider
app.provider('providerName',function(){ });
//syntax for configuring a provider
app.config(function(providerNameProvider){});
```
### AngularJS Service Example
- usage of factory, service and provider services. We are going to develop a sample message service, which prints out a message using all these service APIs.
- The code shown below (index.html) is our view. We need to get the serviceMsg, factoryMsg and providerMsg using the Service APIs and we use controller to wire the data to this view.
```html
<html>
<head>
<title>
AngularJS Services Tutorial
</title>
<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.3.12/angular.min.js">
</script>
<script src="main.js">
</script>
</head>
<body>
<div>
<div ng-app="mainApp" ng-controller="myController">
<p>
<b>
Message From Service:
</b>
{{serviceMsg}}
</p>
<p>
<b>Message From Factory:
</b>
{{factoryMsg}}
</p>
<p>
<b>
Message From Provider:
</b>
{{providerMsg}}
</p>
</div>
</div>
</body>
</html>
```
- defines the services and the controller used in the application.
- **main.js**
```js
var
app = angular.module(
'mainApp'
, []);
//define a service named myService
app.service(
'myService'
,
function ()
{
this
.message =
''
;
this
.setMessage =
function (newMessage)
{
this
.message = newMessage;
return
this
.message; }; });
//define factory named 'myFactory'
app.factory(
'myFactory'
,
function ()
{
var
obj = {}; obj.message =
''
; obj.setMessage =
function (newMessage)
{ obj.message = newMessage; };
return
obj; });
//Defining a provider 'configurable'
app.provider(
'configurable'
,
function ()
{
var
returnMessage =
''
;
this
.setMessage =
function (newMessage)
{ returnMessage = newMessage; };
this
.$get =
function ()
{
return
{
message
: returnMessage }; }; });
//configuring provider
app.config(
function (configurableProvider)
{ configurableProvider.setMessage(
"Hello, I'm From Provider"
); });
//defining controller
app.controller(
'myController'
,
function ($scope, myService, myFactory, configurable)
{ $scope.serviceMsg = myService.setMessage(
"Hello, I'm From Service"
); myFactory.setMessage(
"Hello, I'm From Factory "
); $scope.factoryMsg = myFactory.message; $scope.providerMsg= configurable.message; });
```
### AngularJS Services Example code
- Created a module named mainApp using angular.module(‘mainApp’, []);
- Defined a service using service method in the module and you can see how we added properties and function to the service object for getting the message. We used this keyword to add the properties to the service object.
- Defined a service using factory method in the module and returned the service object.
- Defined a service using provider method in the module and used $get() function to get the message.
- Configured the provider using the config() function in the module to set the message.
- Defined a controller and all the services are injected to the controller.
- Set the factory and service messages.
- Finally controller wire all the messages to the view using $scope
