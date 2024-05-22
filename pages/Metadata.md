- Metadata is information attached to your code using decorators. These decorators are annotations (special functions) that add metadata to classes, properties, methods, or parameters.
- The metadata tells Angular what a class represents (e.g., a component, a service), its configuration details, and how it interacts with other parts of your application.
-
- **Types of Angular Metadata:**
  
  There are various types of metadata associated with different Angular building blocks:
	- **Component Metadata (`@Component` decorator):**
		- Defines a class as an Angular component.
		- Specifies details like the component's selector (HTML tag), template URL, and stylesheet URL.
		- Can also include configuration options for data binding, change detection, and view encapsulation.
	- **Directive Metadata (`@Directive` decorator):**
		- Identifies a class as an Angular directive.
		- Specifies the directive's selector (attribute or element it applies to).
		- May include options for inputs, outputs, and lifecycle hooks.
	- **Service Metadata (`@Injectable` decorator):**
		- Marks a class as an injectable service.
		- Can define the service's visibility (singleton or provider scope).
	- **Pipe Metadata (`@Pipe` decorator):**
		- Identifies a class as a data transformation pipe.
		- Specifies the pipe name and its pure or impure nature.
-
-
- **Importance of Metadata:**
- Provides instructions to Angular:  Metadata tells Angular how to create components, attach directives, and inject services, essentially guiding the framework's behavior.
- Code Organization:  Decorators and metadata promote clean code organization by separating configuration details from the core class logic.
- Reusability:  Metadata allows for generic decorators that can be applied to various components or directives, fostering code reusability.
-
- Example: Component Metadata
	- ```javascript
	  @Component({
	    selector: 'app-my-component',
	    templateUrl: './my-component.component.html',
	    styleUrls: ['./my-component.component.css']
	  })
	  export class MyComponent {
	    title = 'Welcome to my Angular application!';
	  }
	  
	  ```
- ```
  In this example, the @Component decorator defines metadata for the MyComponent class. It specifies the component's selector (app-my-component), the template URL (my-component.component.html), and the stylesheet URL (my-component.component.css).
  ```