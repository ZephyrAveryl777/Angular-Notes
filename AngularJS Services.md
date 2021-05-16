## AngularJS Service
- AngularJS services are JavaScript functions for specific tasks, which can be reused throughout the application.

> - AngularJS built-in services starts with `$`, same as other built-in objects.

- AngularJS includes services for different purposes.
- AngularJS also allows to create custom service for applications.
- Most AngularJS services interact with the controller, model or custom directives.
- some services interact with view (UI) also for UI specific tasks.

![Angular Services](https://www.tutorialsteacher.com/Content/images/ng/ng-service.png)

---
### Services
- list of all the built-in AngularJS services.

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
