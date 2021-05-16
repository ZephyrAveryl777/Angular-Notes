## AngularJS Directives
- AngularJS lets extend HTML with new attributes, these attributes are called directives
- a set of built-in directives in AngularJS, can be self definied also.
- directives start with `ng-` prefix , the most common ones are :
	- ng- app : this directive starts an AngularJS Application
	- ng- init : initalizes application data
	- ng- model : defines the model that is variable to be used in AngularJS
	- ng- repeat : repeats  html elements for each item in  a collection
- types of Directives:
	- **Component**
			  -  adding the @Component annotation extends the @Directive annotation with template-related features
			  -  instead of manipulating the DOM, it comes with its own template
			  -  components use the directive API and provide a nicer way to define them
	- **Attribute Directives**
			  -  manipulate the DOM by changing it's appearance and behaviour.
		  	-  are like normal HTML attribute and can be applied to DOM elements
			  -  an example of attribute directive is the ngModel directive `<input [[ngModel]] = "student.name">`
	- **Structural Directive**
			-  used to create and remove DOM elements
			-  these modify the layout by adding,removing or replacing elements.
			-  normally start with the \*sign
			-  **Example :**
			````html
				<li \*ngFor="let student of students"\></li>
			<app\-student-detail \*ngIf="selectedStudent"\></app-student-detail>
			````
---
### Example of AngularJS directives
````html
<!DOCTYPE html\>
<html\>
<head\>
 <title\>AngularJS Directives</title\>
</head\>
<body\>
 <h1\>Sample Application</h1\>

 <div ng-app = "" ng-init = "countries = \[{locale:'en-IND',name:'India'}, {locale:'en-PAK',name:'Pakistan'}, {locale:'en-AUS',name:'Australia'}\]"\>
  <p\>Enter your Name: <input type = "text" ng-model = "name"\></p\>
  <p\>Hello <span ng-bind = "name"\></span\>!</p\>
  <p\>List of Countries with locale:</p\>

  <ol\>
  <li ng-repeat = "country in countries"\>
  {{ 'Country: ' + country.name + ', Locale: ' + country.locale }}
  </li\>
  </ol\>
  </div\>
 <script src = "http://ajax.googleapis.com/ajax/libs/angularjs/1.3.14/angular.min.js"\></script\>
</body\>
</html>
````
---
### List of AngularJS Directives
| Directive                                                                           | Description                                                                                                           |
| ----------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
|  |
| ng-app                    | It defines the root element of an application.                                                                        |
| ng-bind                   | It binds the content of an html element to application data.                                                          |
| ng-bind-html         | It binds the inner HTML of an HTML element to application data, and also removes dangerous code from the html string. |
| ng-bind-template| It specifies that the text content should be replaced with a template.                                                |
| ng-blur                  | It specifies a behavior on blur events.                                                                               |
| ng-change              | It specifies an expression to evaluate when content is being changed by the user.                                     |
| ng-checked            | It specifies if an element is checked or not.                                                                         |
| ng-class                | It specifies css classes on html elements.                                                                            |
| ng-class-even       | It is same as ng-class, but will only take effect on even rows.                                                       |
| ng-class-odd         | It is same as ng-class, but will only take effect on odd rows.                                                        |
| ng-click               | It specifies an expression to evaluate when an element is being clicked.                                              |
| ng-cloak                | It prevents flickering when your application is being loaded.                                                         |
| ng-controller      | It defines the controller object for an application.                                                                  |
| ng-copy                  | It specifies a behavior on copy events.                                                                               |
| ng-csp                     | It changes the content security policy.                                                                               |
| ng-cut                     | It specifies a behavior on cut events.                                                                                |
| ng-dblclick           | It specifies a behavior on double-click events.                                                                       |
| ng-focus                | It specifies a behavior on focus events.                                                                              |
| ng-hide                 | It hides or shows html elements.                                                                                      |
| ng-href                   | It specifies a URL for the <a> element.                                                                               |
| ng-if                      | It removes the html element if a condition is false.                                                                  |
| ng-include            | It includes html in an application.                                                                                   |
| ng-init                  | It defines initial values for an application.                                                                         |
| ng-jq                      | It specifies that the application must use a library, like jQuery.                                                    |
| ng-keydown             | It specifies a behavior on keydown events.                                                                            |
| ng-keypress         | It specifies a behavior on keypress events.                                                                           |
| ng-keyup                | It specifies a behavior on keyup events.                                                                              |
| ng-list                  | It converts text into a list (array).                                                                                 |
| ng-open                   | It specifies the open attribute of an element.                                                                        |
| ng-options            | It specifies `<options>` in a `<select>`  list.                                                                            |
| ng-paste               | It specifies a behavior on paste events.                                                                              |
| ng-pluralize        | It specifies a message to display according to en-us localization rules.                                              |
| ng-readonly           | It specifies the readonly attribute of an element.                                                                    |
| ng-required           | It specifies the required attribute of an element.                                                                    |
| ng-selected           | It specifies the selected attribute of an element.                                                                    |
| ng-show                   | It shows or hides html elements.                                                                                      |
| ng-src                     | It specifies the src attribute for the `<img>` element.                                                                 |
| ng-srcset               | It specifies the srcset attribute for the `<img>` element.                                                              |
| ng-style                 | It specifies the style attribute for an element.                                                                      |
| ng-submit               | It specifies expressions to run on onsubmit events.                                                                   |
| ng-switch               | It specifies a condition that will be used to show/hide child elements.                                               |
| ng-transclude       | It specifies a point to insert transcluded elements.                                                                  |
| ng-value                 | It specifies the value of an input element.                                                                           |
| ng-disabled                     | It specifies if an element is disabled or not.                                                                        |
| ng-form                         | It specifies an html form to inherit controls from.                                                                   |
| ng-model                        | It binds the value of html controls to application data.                                                              |
| ng-model-options                | It specifies how updates in the model are done.                                                                       |
| ng-mousedown                    | It specifies a behavior on mousedown events.                                                                          |
| ng-mouseenter                   | It specifies a behavior on mouseenter events.                                                                         |
| ng-mouseleave                   | It specifies a behavior on mouseleave events.                                                                         |
| ng-mousemove                    | It specifies a behavior on mousemove events.                                                                          |
| ng-mouseover                    | It specifies a behavior on mouseover events.                                                                          |
| ng-mouseup                     | It specifies a behavior on mouseup events.                                                                            |
| ng-non-bindable                | It specifies that no data binding can happen in this element, or it's children.                                       |
| ng-repeat                      | It defines a template for each data in a collection.                                                                  |

---
