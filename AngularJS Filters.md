## AngularJS Filters

- filters are used to format data.
- Following is a list of filters used for transforming data.

| Filter                                                              | Description                                                                          |
| ------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
|  |
| Currency   | It formats a number to a currency format.                                            |
| Date          | It formats a date to a specified format.                                             |
| Filter       | It select a subset of items from an array.                                           |
| Json            | It formats an object to a Json string.                                               |
| Limit      | It is used to limit an array/string, into a specified number of elements/characters. |
| Lowercase | It formats a string to lower case.                                                   |
| Number        | It formats a number to a string.                                                     |
| Orderby     | It orders an array by an expression.                                                 |
| Uppercase  | It formats a string to upper case.                                                   |

* * * * *

### Adding filters to expressions
-  add filters to expressions by using the pipe character |, followed by a filter.
- **Example**
```html
<!DOCTYPE html>  
<html>  
<script src="http://ajax.googleapis.com/ajax/libs/angularjs/1.4.8/angular.min.js"></script>  
<body>  
<div ng-app="myApp" ng-controller="personCtrl">  
<p>The name is {{ firstName | uppercase }}</p>  
</div>  
<script>  
9.  angular.module('myApp', []).controller('personCtrl', function($scope) {  
$scope.firstName = "Sonoo",  
$scope.lastName = "Jaiswal"  
12. });  
</script>  
</body>  
</html>  
```
- **Example-2**
```html
<!DOCTYPE html>  
<html>  
<script src="http://ajax.googleapis.com/ajax/libs/angularjs/1.4.8/angular.min.js"></script>  
<body>  
<div ng-app="myApp" ng-controller="personCtrl">  
<p>The name is {{ firstName | lowercase }}</p>  
</div>  
<script>  
angular.module('myApp', []).controller('personCtrl', function($scope) {  
$scope.firstName = "Sonoo",  
$scope.lastName = "Jaiswal"  
 });  
</script>  
</body>  
</html>  
```
* * * * *
### Adding filters to directives
- Filters can be added to directives, like ng-repeat, by using the pipe character |, followed by a filter.
- **Example :**
```html
<!DOCTYPE html>  
<html>  
<script src="http://ajax.googleapis.com/ajax/libs/angularjs/1.4.8/angular.min.js"></script>  
<body>      
<div ng-app="myApp" ng-controller="namesCtrl">  
<p>Looping with objects:</p>  
<ul>  
<li ng-repeat="x in names | orderBy:'country'">  {{ x.name + ', ' + x.country }}
</li>  
</ul>  
</div>  
<script>  
angular.module('myApp', []).controller('namesCtrl', function($scope) {  
$scope.names = [  
{name:'Ramesh',country:'India'},  
{name:'Alex',country:'USA'},  
{name:'Pooja',country:'India'},  
{name:'Mahesh',country:'India'},  
{name:'Iqbal',country:'Pakistan'},  
{name:'Ramanujam',country:'India'},  
{name:'Osama',country:'Iraq'},  
{name:'Johnson',country:'UK'},  
{name:'Karl',country:'Russia'}  
];  
});  
</script>  
</body>  
</html>  
```
* * * * *

###  `filter` Filter
- The filter Filter can only be used on arrays because it selects a subset of an array. - It returns an array containing only the matching items.
- **Example**
```html
<!DOCTYPE html>  
<html>  
<script src="http://ajax.googleapis.com/ajax/libs/angularjs/1.4.8/angular.min.js"></script>  
<body>  
<div ng-app="myApp" ng-controller="namesCtrl">  
<ul>  
<li ng-repeat="x in names | filter : 'o'">  
{{ x }}  
</li>  
</ul>  
</div>  
<script>  
angular.module('myApp', []).controller('namesCtrl', function($scope) {  
$scope.names = [  
'Ramesh',  
'Pooja',  
'Mahesh',  
'Ramanujam',  
'Osama',  
'Iqbal',  
'2Karl',  
'Johnson',  
'Alex'  
];  
});  
</script>  
<p>This example displays only the names containing the letter "o".</p>  
</body>  
</html>  
```
----
### Filter an array based on user input
- can use the value of the input field as an expression in a filter by setting the ng-model directive on an input field.
- **Example:**
```html
 <!DOCTYPE html>  
 <html>  
 <script src="http://ajax.googleapis.com/ajax/libs/angularjs/1.4.8/angular.min.js"></script>  
 <body>  
 <div ng-app="myApp" ng-controller="namesCtrl">  
 <p>Type a letter in the input field:</p>  
 <p><input type="text" ng-model="test"></p>  
 <ul>  
 <li ng-repeat="x in names | filter:test">  
 {{ x }}  
 </li>  
 </ul>  
 </div>  
 <script>  
 angular.module('myApp', []).controller('namesCtrl', function($scope) {  
 $scope.names = [  
 'Ramesh',  
 'Pooja',  
 'Mahesh',  
 'Ramanujam',  
'Osama',  
'Iqbal',  
'Karl',  
'Johnson',  
'Alex'  
];  
});  
</script>  
<p>The list will only contain the names matching the filter.</p>  
</body>  
</html>  
```
----

### Sort an array based on user input
- can sort an array according to the table columns.
- **Example:**
```html
 <!DOCTYPE html>  
 <html>  
 <script src="http://ajax.googleapis.com/ajax/libs/ularjs/1.4.8/angular.min.js"></script>  
 <body>  
 Click the table headers to change the sorting order:</ 
 <div ng-app="myApp" ng-controller="namesCtrl">  
 <table border="1" width="100%">  
 <tr>  
 <th ng-click="orderByMe('name')">Name</th>  
 <th ng-click="orderByMe('country')">Country</th>  
 </tr>  
 <tr ng-repeat="x in names | orderBy:myOrderBy">  
 <td>{{x.name}}</td>  
 <td>{{x.country}}</td>  
 </tr>  
 </table>  
 </div>  
 <script>  
 angular.module('myApp', []).controller('namesCtrl',function($scope) {
$scope.names = [  
 {name:'Ramesh',country:'India'},  
 {name:'Alex',country:'USA'},  
 {name:'Pooja',country:'India'},  
 {name:'Mahesh',country:'India'},  
 {name:'Iqbal',country:'Pakistan'},  
 {name:'Ramanujam',country:'India'},  
 {name:'Osama',country:'Iraq'},  
 {name:'Johnson',country:'UK'},  
 {name:'Karl',country:'Russia'}  
 ];  
 $scope.orderByMe = function(x) {  
 $scope.myOrderBy = x;  
 }  
 });  
 </script>  
 </body>  
 </html>  
```
* * * * *

### AngularJS Custom Filters
- You can create your own filters by register a new filter factory function with your module.
- **Example:**
```html
<!DOCTYPE html>  
<html>  
<script src="http://ajax.googleapis.com/ajax/libs/angularjs/1.4.8/angular.min.js"></script>  
<body>  
<p>Click the table headers to change the sorting order:</p>  
<div ng-app="myApp" ng-controller="namesCtrl">  
<table border="1" width="100%">  
<tr>  
<th ng-click="orderByMe('name')">Name</th>  
<th ng-click="orderByMe('country')">Country</th>  
</tr>  
<tr ng-repeat="x in names | orderBy:myOrderBy">  
<td>{{x.name}}</td>  
<td>{{x.country}}</td>  
</tr>  
</table>  
</div>  
<script>  
angular.module('myApp', []).controller('namesCtrl', function($scope) {  
$scope.names = [  
{name:'Ramesh',country:'India'},  
{name:'Alex',country:'USA'},  
{name:'Pooja',country:'India'},  
{name:'Mahesh',country:'India'},  
{name:'Iqbal',country:'Pakistan'},  
{name:'Ramanujam',country:'India'},  
{name:'Osama',country:'Iraq'},  
{name:'Johnson',country:'UK'},  
{name:'Karl',country:'Russia'}  
];  
$scope.orderByMe = function(x) {  
$scope.myOrderBy = x;  
}  
});  
</script>  
</body>  
</html>  
```
---
