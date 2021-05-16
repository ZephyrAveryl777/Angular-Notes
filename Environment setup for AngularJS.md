## Angular Setup and Development Enviornment 

#### Choosing and Installing Editor 
- choose an editor, can choose any editions of Visual Studio,Eclipse,Atom etc
- use of Visual Studio Code as editor is recomended 
#### Install Package Manager 
- to install Angular dependencies  use of Node Package Manager (NPM) is appriciated 
- NPM: used to install/upgrade libraries, Package & application from  Public repositories. 
- Install NPM: 
- Configure NPM: 
    - npm requires `package.json` which should contain the list of modules/packages used in the Application.
    - once `package.json` is created, can install all the dependencies,by running the command `npm install`
#### Choosing a Language
- angular application must be written in JavaScript 
- including the current version of JavaScript (ES2015), TypeScript, Dart.
- TypeScript: 
  - a subset of JavaScript, code written in TypeScript cannot be used directly in the web browser. 
  - must be compiled to JavaScript before running in the web browser. this process is known as Transpilling 
  - supports Modules,classes,Interfaces and Generics. 
#### Installing Angular 
- can install Angular using Angular CLI (Angular Command Line Interface)
#### Angular CLI
- use the npm command to install Angular `npm i -g @angular/cli@latest`
- above command installs the latest versions of Angular CLI in the machine 
- it helps to quickly create an Angular application with all the configuration files and packages in one single command. 
- also helps to add features like components, directives,services etc. to existing Angular applications 
- Angular CLI uses TypeScript,Webpack(Module Bundler), Karma (for unit testing), Protractor (for an end to end testing)
#### Module Loaders 
- taking  a group of modules with their dependencies and merges them into a single file in the correct order. 
- this process is called as Module bundling. 
---
#### Creating an Application with AngularJS
- For simplicity have not used any aspx pages in starting example.
- First create a folder anywhere in your system,created a Demo folder by name "Demo".
- Create another folder in Demo folder for script file, have created Script folder for custom script and angular.min.js script file.
- Create a simple HTML page in Demo folder.

#### Code for Demo.htm
```html
<!DOCTYPE html/>
<html>
  <head>
    <script src="Scripts/angular.min.js"></script>
  </head>
  <body>
    <div ng-app>Sum of 10 and 20 is = {{10+20}}</div>
  </body>
</html>
```
**Now open this Demo folder using visual studio.**
- `File → Open → Website`

Select demo folder and click ok. The hierarchy of folder and files will be something like the image given below.

![demo](https://www.tutorialride.com/images/angularjs/demo.jpg)

**In Demo.htm file there are three important things.**

- ng-app directive
- angular.min.js
- {{ expression }}.

In AngularJS ng-app is a directive. This directive is starting point of AngularJS application.

- When you execute AngularJS application, AngularJS framework first checks the ng-app directive in your HTML page.
- Just drag the angular.min.js file from visual studio in head section of HTML. Execute the HTML file.
- If possible use Google chrome browser. It gives better debugging facility.
- If your application is not giving the output as expected, then press F12 in chrome browser. It will show you the error.
- Always remember that AngularJS expressions do not support conditions, loops, and exceptions, while JavaScript expressions do.
- AngularJS expressions support filters, but JavaScript expressions does not support filters.

**Execute the Demo.html file you will see the output as follows:**

**Output:**\
Sum of 10 and 20 is=30

> **Note**,
>
> - here `ng-app` directive is applied to div tag only. So if you write one more div tag and not applied ng-app directive then HTML will display the expression as it is, without solving it:

```jsx
<div ng-app>
     Sum of 10 and 20 is = {{10+20}}
</div>
<div>
     Sum of 100 and 200 is = {{100+200}}
</div>
```

**The output will be as follows.**

- Sum of 10 and 20 is=30
- Sum of 100 and 200 is={{100+200}}

So better apply ng-app directive in HTML tag.

```html
<!DOCTYPE html/>
<html ng-app>
  <head>
    <script src="Scripts/angular.min.js" type="text / javascript"></script>
  </head>
  <body>
    <div>Sum of 10 and 20 is={{10+20}}</div>
    <div>Sum of 100 and 200 is= {{100+200}}</div>
  </body>
</html>
```

**Now the output will be.**

- Sum of 10 and 20 is=30
- Sum of 100 and 200 is=300

---
