- #Angular
- Pipes in Angular are a powerful feature that allows you to transform data directly in your templates. They are used to format data displayed to the user, making it more readable and presentable.
-
- ## Pipes
	- ### Built-In Pipes
		- Angular comes with several built-in pipes that cover common data transformation needs. Here are some of the most commonly used ones:
			- ```
			  {{ today | date:'short' }}
			  
			  {{ 'hello' | uppercase }}
			  
			  {{ 'HELLO' | lowercase }}
			  
			  {{ 1234.56 | currency:'USD' }}
			  
			  {{ 3.14159 | number:'1.2-2' }}
			  
			  {{ 0.1234 | percent }}
			  
			  <pre>{{ myObject | json }}</pre>
			  
			  {{ 'Angular' | slice:1:5 }}
			  
			  <div *ngIf="observableValue | async as value">
			    {{ value }}
			  </div>
			  
			  ```
	- ### Custom Pipes
	  collapsed:: true
		- When built-in pipes are not sufficient, you can create custom pipes to handle specific data transformations.
		- ```javascript
		  import { Pipe, PipeTransform } from '@angular/core';
		  
		  @Pipe({
		    name: 'myCustom'
		  })
		  export class MyCustomPipe implements PipeTransform {
		    transform(value: any, ...args: any[]): any {
		      // Custom transformation logic
		      return value.toUpperCase();
		    }
		  }
		  
		  //Pipe Parameters
		  transform(value: any, param1: string, param2: number): any {
		    // Use param1 and param2 in your transformation logic
		  }
		  
		  {{ 1234.56 | currency:'EUR':'symbol-narrow':'1.2-2' }}
		  
		  ```
	- ### Pure Pipes
		- Pipes are pure by default. They are called only when Angular detects a change in the input data. This makes them efficient for performance.
		- ```javascript
		  @Pipe({
		    name: 'purePipe',
		    pure: true
		  })
		  export class PurePipe implements PipeTransform {
		    transform(value: any): any {
		      return value.toUpperCase();
		    }
		  }
		  
		  ```
	- ### Impure Pipes
		- Impure pipes are called on every change detection cycle. They are useful for situations where the data changes frequently or relies on external factors.
		- ```javascript
		  @Pipe({
		    name: 'impurePipe',
		    pure: false
		  })
		  export class ImpurePipe implements PipeTransform {
		    transform(value: any): any {
		      return value.toUpperCase();
		    }
		  }
		  
		  ```
-
- ### Chaining Pipes
	- Multiple pipes can be chained together in a template, allowing for complex transformations.
	- ```javascript
	  ```
- ### Using Pipes in Components
	- Pipes can also be used within Angular components to transform data programmatically.
	- ```javascript
	  import { Component } from '@angular/core';
	  import { UpperCasePipe } from '@angular/common';
	  
	  @Component({
	    selector: 'app-example',
	    template: `{{ transformedValue }}`
	  })
	  export class ExampleComponent {
	    transformedValue: string;
	  
	    constructor(private upperCasePipe: UpperCasePipe) {
	      this.transformedValue = this.upperCasePipe.transform('hello');
	    }
	  }
	  
	  ```