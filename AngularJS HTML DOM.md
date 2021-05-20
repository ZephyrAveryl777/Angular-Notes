### AngularJS HTML DOM
- directives are used to bind application data to the attributes of HTML DOM elements.

| Sr.No. | Name & Description                                  |
| ------ | --------------------------------------------------- |
| 1      | ng-disabled => disables a given control.              |
| 2      | ng-show => shows a given control.                     |
| 3      | ng-hide => hides a given control.                     |
| 4      | ng-click => represents a AngularJS click event. |

### `ng-disabled` Directive
- Add *ng-disabled* attribute to an HTML button and pass it a model.
- Bind the model to a checkbox and see the variation.
```html
<input type = "checkbox" ng-model = "enableDisableButton">Disable Button
<button ng-disabled = "enableDisableButton">Click Me!</button>
```
### `ng-show` Directive
- Add *ng-show* attribute to an HTML button and pass it a model.
- Bind the model to a checkbox and see the variation.
```html
<input type = "checkbox" ng-model = "showHide1">Show Button
<button ng-show = "showHide1">Click Me!</button>
```
### `ng-hide` Directive
- Add *ng-hide* attribute to an HTML button and pass it a model.
- Bind the model to a checkbox and see the variation.
```html
<input type = "checkbox" ng-model = "showHide2">Hide Button
<button ng-hide = "showHide2">Click Me!</button>
```
### `ng-click` Directive
- Add *ng-click* attribute to an HTML button and update a model.
- Bind the model to HTML and see the variation.
```html
<p>Total click: {{ clickCounter }}</p>
<button ng-click = "clickCounter = clickCounter + 1">Click Me!</button>
```
- **Example**
### testAngularJS.htm
```html
<html>
<head>
<title>AngularJS HTML DOM</title>
</head>
<body>
<h2>AngularJS Sample Application</h2>
<div  ng-app  =  "">
<table  border  =  "0">
<tr>
<td>
<input  type  =  "checkbox"  ng-model  =  "enableDisableButton">Disable Button</td>
<td>
<button  ng-disabled  =  "enableDisableButton">Click Me!</button>
</td>
</tr>
<tr>
<td>
<input  type  =  "checkbox"  ng-model  =  "showHide1">Show Button</td>
 <td>
 <button  ng-show  =  "showHide1">Click Me!</button>
 </td>
 </tr>
 <tr>
 <td><input  type  =  "checkbox"  ng-model  =  "showHide2">Hide Button</td>
 <td>
 <button  ng-hide  =  "showHide2">Click Me!</button>
 </td>
 </tr>
 <tr>
 <td>
 <p>Total click: {{ clickCounter }}
 </p>
 </td>
 <td>
 <button  ng-click  =  "clickCounter = clickCounter + 1">Click Me!</button>
 </td>
</tr>
</table>
</div>
<script  src  =  "https://ajax.googleapis.com/ajax/libs/angularjs/1.3.14/angular.min.js">
</script>
</body>
</html>
```
---
