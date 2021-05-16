## AngularJS

- AngularJS is a JavaScript framework that helps to build web application.
- It is a full featured single page application framework. It can be added to an HTML page with a `<script>` tag.
- AngularJS enables one to create cross-browse application.
- It automatically handles JavaScript code that is compatible for each browser.
-   It is an open source project, which mean that it can be freely used, the code can be changed and shared by anyone.

### Versions of Angular 
- Early versions of Angular was named as Angular 2
- later was renamed to just Angular. 
- the lastest version uses ivy compiler and runtime by default, as it brings smaller bundle sizes, faster & better testing debugging, improved type checking, build times, etc 

### Prequesties 
- requires a working knowledge of JavaScript,HTMl,CSS, also the concepts of OOP. 
- TypeScript would be an added advantage, 

## Core Features

**Following are most important features of AngularJS:**

- **Two-Way Data Binding**
    - data binding is automatic and fast, change in view is automatically updated in the component class and vide versa
- **Powerful Routing Switching**
    - routing engine loads the page asynchronously on the same page enabling to create a Single Page Application
- **Expressive HTML**
  -  enables to use programming constructs like if conditions,for loops.. to render and control HTML pages
-  **Modular by Design**
   -   built in support to communicate with the back-end servers and execute any business logic/retrive data
-  **Active Community**
   -  supported by Google, has an active community of supporters
   -  easy to resolve queries.
-   **Scope** `$scope` object as an argument with controller. It is available with properties and methods.The scope object is available for both the view and the controller.
-   **Controller** A controller is a JavaScript constructor function. The main job of a controller is to build a model for the view to display.
-   **Services** There are several built-in services in AngularJS. Services enable you to organize and share code across your app.
-   **Filters** Filters can be added to expressions by using the pipe character |, followed by a filter as {{ expression | filter }}.
   -  **For example:**
```js
    <p>The name is {{ EmployeeName | uppercase }}</p>
```
-   **Directives** AngularJS comes with built-in directives which offer different functionalities to your applications.For e.g. ng-app, ng-model, ng-repeat, ng-init are some of the directives. AngularJS directives are always prefixed with the ng-. These directives are extended HTML attributes.
-   **Templates**
-   **Routing**
-   **Deep Linking**
-   **Dependency Injection:** AngularJS has a built-in dependency injection subsystem.

---
### Differences between Angular and AngularJS

| Key Features         | Angular                                                                                      | AngularJS                                                                                                                                                    |
| -------------------- | -------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
|  |
| Architecture         | Angular uses components and directives.                                                      | Angular.js works on MVC (Model-View-Controller) design.                                                                                                      |
| Language             | Angular code is written in Microsoft TypeScript.                                             | AngularJS code is written in Javascript.                                                                                                                     |
| Mobile               | Angular builts mobile support applications.                                                  | AngularJS code is not mobile-friendly.                                                                                                                       |
| Expression syntax    | ( ) and \[ \] attributes are used for two way binding between view and model.                | {{ }} expressions are used for two way binding between view and model. Special methods, ng-bind can also be used to do the same.                             |
| Dependency Injection | A hierarchical dependency injection system is used.                                          | Dependency injection system is not used.                                                                                                                     |
| Routing              | The Angular team uses @RouteConfiguration {(…)} to define routing information.               | AngularJS development team uses @routeProvider.when ( ),for configuration and routing information. |
| Management           | Angular code has a better structure, and it is easy to create and manage large applications. | AngularJS project is difficult to manage with increasing the size of the source code.                                                                        |

----
### Pros and Cons of Angular and AngularJs

### Angular
**Pros**
-   The latest version of Angular supports TypeScript that allows code modularity and code optimization using the OOPS concept.
-   It has a mobile support framework, unlike other Angular versions.
-   Angular supports the changes for an enhanced hierarchical dependencies system along with the modularity.
-   A developer gets the choice to function with the features like Dart, syntax for type checking, TypeScript, Angular CLI, ES5, iterators, lambda operators, and ES6.
-   Angular follows semantic versioning which contains major-minor-patch arrangement.
-   One of the major benefits of Angular is that it provides the event of simplest routing.

**Cons**
-   When it comes to the event of set-up, Angular versions are more complex than Angular JS.
-   It is not an ideal choice if the aim is to create an output of simple web applications.
-   Here, in Angular, directing an extensive range of browsers is challenging as it does not support all the traits of modern versions. You can compensate by loading polyfill scripts for browsers that you should support.

### AngularJS
**Pros**
-   AngularJS uses a great MVC (Model-View-Controller) data binding that makes dynamic application performance.
-   Here, change detection and unit testing can be done at any point of time.
-   The web developers can use the features like declarative template language using HTML to help and support them turn more intuitive.
-   This open source framework provides the much-structured front end development process, as it does not need any other platforms or plugins to work.
-   The Angular JS programmers will be able to run AngularJS applications on iOS and Android devices, including phones and tablets.

**Cons**
-   AngularJS is not only big but also complicated because of its multiple ways of performing the same thing.
-   One of the major drawbacks of AngularJS is that it has a scale of implementation which is a little rough and poor.
-   On disabling the JavaScript of an AngularJS app, users get to see a page which is basic.
-   Further, UI gets cracked up with the rush of more than 250+ apps at one time in Angualr JS.

---

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
<h4 align="right">
<p> 
   <a href=""> Next: Environment setup </a>
   </p>
</h4>
   
