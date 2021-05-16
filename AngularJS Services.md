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


