## AngularJS Data Binding
- Data Binding acts as a bridge between the view and business logic of the application
### Classification  of Data Binding
![Data Binding](https://csharpcorner.azureedge.net/article/temp/61509/Images/image001.jpg)
### One-Way Data Binding
**Component to View**
- this is an approach where a value is taken from the data model and inserted into a HTML element.
- no way to update model from view.
- used in classical template systems.
- ![Onw-Way Data Binding](https://www.javatpoint.com/js/angularjs/images/one-way-data-binding.png)
- different types of one-way binding:
  - Interpolation Binding
  - Property Binding
  - Attribute Binding
  - Class Binding
  - Style Binding
#### Interpolation Binding
- interpolation is nothing but how to used `this binding expression {{}}`
- it places the component property name in the View template, enclose in double curly braces: `{{property Name}}`
- **Example**:
````html
<!--- File Name: Index.html [start up page is used for all components]--->
<!DOCTYPE html>
<html>
  <head>
    <title>First Angular Program</title>
    <base href="/src/">
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="stylesheet" href="styles.css">

    <!-- Polyfill(s) for older browsers -->
    <script src="/node_modules/core-js/client/shim.min.js"></script>

    <script src="/node_modules/zone.js/dist/zone.js"></script>
    <script src="/node_modules/systemjs/dist/system.src.js"></script>

    <script src="systemjs.config.js"></script>
    <script>
      System.import('main.js').catch(function(err){ console.error(err); });
    </script>
  </head>

  <body>

      <!--Here is the selector mapped-->
      <my-app>Loading AppComponent content here ...</my-app>

  </body>
</html>
````
`````typescript
// File Name: app.components
import { Component } from "@angular/core";
@Component({
    selector: 'my-App',
    template: `
                <div>
                <strong>{{firstname}}</strong>
                 <strong>{{lastname}}</strong>
                </div>
})
export class AppComponent {
    firstname: string = "Sachin";
    lastname:string = "Tendulkar"
}
`````
![Interplotation Example](https://csharpcorner.azureedge.net/article/temp/61509/Images/image002.jpg)
#### Property Binding
- used to bing values of component/model properties to the HTML elements.
- Depending on the values, it will change the existing
- **Syntax**: `[property] = 'expression'`
- there is source and target in property binding, Example: `[innerHTML] = 'firstname'` (innerHTMl is a target that is a property of span tag and source is a component property i.e firstname)`
- **Example**
````js
import { Component } from "@angular/core";

@Component({

    selector: 'my-App',
    template: `
                <div>
                <span [innerHTML]='firstname'></span>
                </div>
})
export class AppComponent {
    firstname: string = "Sachin";
}
````
- ![](https://csharpcorner.azureedge.net/article/temp/61509/Images/image003.jpg)
#### Attribute Binding
- with this its possible to set the value of attribute directly
- use attribute binding only when there is no element property to bind
- Example situation: ARIA, SVG and table span
- **Example Code**
````html
<table border="1">
    <thead>
        <tr>
            <th [attr.colspan]="2">Student Details</th>

        </tr>
    </thead>
    <tbody>
        <tr>
            <td>First Name</td>
            <td>{{firstName}}</td>
        </tr>
        <tr>
            <td>Last Name</td>
            <td>{{lastName}}</td>
        </tr>
        <tr>
            <td>Gender</td>
            <td>{{gender}}</td>
        </tr>
        <tr>
            <td>Qualification</td>
            <td>{{qualification}}</td>
        </tr>
    </tbody>
</table>
````
![Attribute Binding](https://csharpcorner.azureedge.net/article/temp/61509/Images/image004.png)
#### Class Binding
- class Binding, can add and remove CSS class names from HTML elements
- it is similar to the attribute binding but it starts with the prefix class, optionally followed by dot(.) and the name of CSS `class:[class.Class-name]`
- **Example :**
````html
<style>
    .txtcenter{
    text-align:center;
}

.txtright{
     text-align:right;
}

.txtleft{
      text-align:left;
}
</style>

<table border="1">
    <thead>
        <tr>
            <th [attr.colspan]="2" class="txtcenter"  [class.txtright]='true'>Student Details</th>

        </tr>
    </thead>
    <tbody>
        <tr>
            <td>First Name</td>
            <td>{{firstName}}</td>
        </tr>
        <tr>
            <td>Last Name</td>
            <td>{{lastName}}</td>
        </tr>
        <tr>
            <td>Gender</td>
            <td>{{gender}}</td>
        </tr>
        <tr>
            <td>Qualification</td>
            <td>{{qualification}}</td>
        </tr>
    </tbody>
</table>
````
![](https://csharpcorner.azureedge.net/article/temp/61509/Images/image007.jpg)
#### Style Binding
- by using this, can set inline styles to the HTML element
- it is used to set single line style.
- to send multiple line style, angular provides directive called NgStyle
- **Syntax :** similar to the attribute and class binding, It also starts with the prefix style followed by a dot(.) and the name of a `CSS style property: [style. Style-property]`
- **Example**
````html
<thead>
        <tr>
            <th [attr.colspan]="2"  [style.font-size.px]="50">Student Details</th>
        </tr>
    </thead>
````
![Style-Binding](https://csharpcorner.azureedge.net/article/temp/61509/Images/image008.png)
### One way Data-Binding [View to Component]
#### Event Binding
- binds the data from an HTML element to a component
- **Syntax :** `<button (click)="onClick()">Click me</button>
`
- **Example**
````js
import { Component } from "@angular/core";

@Component({

    selector: 'my-App',
    template: `<button (click)='onClick()' >Click me</button>`

})

export class AppComponent {
    onClick(): void {
        console.log('you clicked me!!');
    }
}
````
![Event Binding](https://csharpcorner.azureedge.net/article/temp/61509/Images/image009.jpg)
---
### Two-Way Data Binding
- in simple, two-way data bining is a combination of both Property Binding and Event Binding
- this is the automatic synchronization of data between the model and view components
- model is considered as the single point of change
- the view is a projection of the model at all times.
- If the model is changed, the view reflects the change and vice-versa
- ![Two-Way Data Binding](https://www.javatpoint.com/js/angularjs/images/two-way-data-binding.png)
- *Syntax :* `<input [value]='data1' (input)='data1 =$event.target.value'>`
- **Example :**
````js
import { Component } from '@angular/core';

@Component({
    selector: 'my-app',
    template: `
                Enter the value  : <input [value]='data1' (input)='data1 = $event.target.value'>
                <br>
                 Entered value : Hi  {{data1}}
              `
})
export class AppComponent {
    data1: string = '';
}
````
![Two-Way Binding](https://csharpcorner.azureedge.net/article/temp/61509/Images/image010.png)

#### Binding using[(ngModel)] directive
- Angular 2 provides the ngModel directive which combines the square brackets of property binding with the parenthesis of event binding in a single notation.
- *Syntax :* `<input [(ngModel)] = 'data1'`
- **Example :**
````js
import { FormsModule } from "@angular/forms"

import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { FormsModule } from "@angular/forms"

import { AppComponent } from './app.component';

@NgModule({
    imports: [BrowserModule, FormsModule],
    declarations: [ AppComponent],
    bootstrap: [AppComponent]
})
export class AppModule { }
````
-----
