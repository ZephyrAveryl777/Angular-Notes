## What is AngularJS?

- AngularJS is a JavaScript framework that helps to build web application.
- It is a full featured single page application framework. It can be added to an HTML page with a `<script>` tag.
- AngularJS enables one to create cross-browse application.
- It automatically handles JavaScript code that is compatible for each browser.
-   It is an open source project, which mean that it can be freely used, the code can be changed and shared by anyone.

## Core Features

**Following are most important features of AngularJS:**

-   **Data-binding:** It keeps the model and view in synchronization. It supports two way data binding. When you change the model, view is updated accordingly and vice versa.
-   **Scope:** `$scope` object as an argument with controller. It is available with properties and methods.The scope object is available for both the view and the controller.
-   **Controller:** A controller is a JavaScript constructor function. The main job of a controller is to build a model for the view to display.
-   **Services:** There are several built-in services in AngularJS. Services enable you to organize and share code across your app.
-   **Filters:** Filters can be added to expressions by using the pipe character |, followed by a filter as {{ expression | filter }}.
   -  **For example:**
```js
    <p>The name is {{ EmployeeName | uppercase }}</p>
```
-   **Directives:** AngularJS comes with built-in directives which offer different functionalities to your applications.For e.g. ng-app, ng-model, ng-repeat, ng-init are some of the directives. AngularJS directives are always prefixed with the ng-. These directives are extended HTML attributes.
-   **Templates**
-   **Routing**
-   **Deep Linking**
-   **Dependency Injection:** AngularJS has a built-in dependency injection subsystem.

## Module in AngularJs
-   Module is a container for different part of your container. It can contain controllers, services, directives, filters etc.
-   You can consider a module as a `main()` method, same as in C# or in Java.
-   Angular apps don't have a main method, instead modules declaratively specify how an application should be load for execution.

**Some of the advantages of module are as follows:**

-   Declarative process for creating the module is easier to understand.
-   Modules are reusable.
-   The modules can be loaded in any order.
-   Modules are fast with respect to unit tests because it loads relevant modules only.

---

- AngularJS framework provides an angular object.
- With the help of `module()` method of angular object you can create the module.
- The first parameter is the name of the module that we want to create and the second parameter shows the dependency of the module.
- A module can dependent on other module.
```js
var app = angular.module("myModule", [ ]);
```
- the above code, it will create module name "**myModule**" and it will not dependent on any external module due to second parameter as an empty array.

---
