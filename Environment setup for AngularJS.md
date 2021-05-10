## Environment setup - Angular.Js
- can use any editor for creating AngularJS project such as notepad++, eclipse, sublime text, visual studio and many more.
-   First download the script file from <https://angularjs.org/>
-   Click on Download AngularJS 1 image. After clicking you will see the given below window.

    ![download angularjs](https://www.tutorialride.com/images/angularjs/download-angularjs.jpg)

-   You can download the AngularJS script file, when you click on download button. You can download Minified, Uncompressed or in Zip file format.
-   If downloaded the zip file, then unzip it and copy and paste angularjs.min.js file in your visual studio project folder.
-   For simplicity we have not uses any aspx pages in our starting examples.
-   First create a folder anywhere in your system.We created Demo folder.
-   Create another folder in Demo folder for script file. We have created Script folder for our custom script and angular.min.js script file.
-   Create a simple HTML page in Demo folder.

#### Code for Demo.htm
```html
<!DOCTYPE html/>
<html>
      <head>
            <script src="Scripts/angular.min.js"></script>
      </head>
      <body>
            <div ng-app>
                  Sum of 10 and 20 is = {{10+20}}
            </div>
      </body>
</html>
```

**Now open this Demo folder using visual studio.**
- `File → Open → Website`

Select you demo folder and click ok. The hierarchy of folder and files will be something like the image given below.

![demo](https://www.tutorialride.com/images/angularjs/demo.jpg)

**In Demo.htm file there are three important things.**

-   ng-app directive
-   angular.min.js
-   {{ expression }}.

In AngularJS ng-app is a directive. This directive is starting point of AngularJS application.

-   When you execute AngularJS application, AngularJS framework first checks the ng-app directive in your HTML page.
-   Just drag the angular.min.js file from visual studio in head section of HTML. Execute the HTML file.
-   If possible use Google chrome bowser. It gives better debugging facility.
-   If your application is not giving the output as expected, then press F12 in chrome browser. It will show you the error.
-   Always remember that AngularJS expressions do not support conditions, loops, and exceptions, while JavaScript expressions do.
-   AngularJS expressions support filters, but JavaScript expressions does not support filters.

**Execute the Demo.html file you will see the output as follows:**

**Output:**\
Sum of 10 and 20 is=30

> **Note**,
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
          <div>
               Sum of 10 and 20 is={{10+20}}
          </div>
          <div>
               Sum of 100 and 200 is= {{100+200}}
          </div>
     </body>
</html>
```
**Now the output will be.**
- Sum of 10 and 20 is=30
- Sum of 100 and 200 is=300

---
<h4 align="left">
<p> 
   <a href=""> Previous: Introduction</a>
   </p>
</h4>
