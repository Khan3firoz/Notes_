- #Angular
- In Angular, decorators are a special kind of declaration that can be attached to a class, method, accessor, property, or parameter. Decorators are a design pattern that is used to separate modification or decoration of a class without modifying the original source code. Angular uses decorators to attach metadata to classes, which helps it understand the purpose and functionality of those classes.
	- ### Class Decorators
		- **@Component** :
			- Used to define a component, which controls a patch of the screen called a view.
			- Contains metadata like selector, templateUrl, styleUrls, etc.
			- ```javascript
			  @Component({
			    selector: 'app-example',
			    templateUrl: './example.component.html',
			    styleUrls: ['./example.component.css']
			  })
			  export class ExampleComponent {
			    // Component logic
			  }
			  
			  ```
		- **@Directive** :
			- Used to create directives, which are custom HTML elements or attributes used to extend HTML's functionality.
			- Contains metadata like selector.
			- ```javascript
			  @Directive({
			    selector: '[appHighlight]'
			  })
			  export class HighlightDirective {
			    // Directive logic
			  }
			  
			  ```
		- **@Injectable**:
			- Indicates that the class can be injected using Angular's dependency injection system.
			- Often used in service classes.
			- ```javascript
			  @Injectable({
			    providedIn: 'root'
			  })
			  export class ExampleService {
			    // Service logic
			  }
			  
			  ```
		- **@NgModule** :
			- Defines a module that contains components, directives, pipes, and providers.
			- Contains metadata like declarations, imports, providers, bootstrap, etc.
			- ```javascript
			  @NgModule({
			    declarations: [ExampleComponent],
			    imports: [BrowserModule],
			    providers: [ExampleService],
			    bootstrap: [AppComponent]
			  })
			  export class AppModule { }
			  
			  ```
			-
	-
	- ### Property Decorators
		- **@Input** :
			- Declares a data-bound property that Angular can bind to from an external component.
			- ```javascript
			  @Component({ ... })
			  export class ExampleComponent {
			    @Input() exampleInput: string;
			  }
			  
			  ```
		- **@Output** :
			- Declares an event-bound property that Angular can bind to from an external component.
			- ```javascript
			  @Component({ ... })
			  export class ExampleComponent {
			    @Output() exampleOutput = new EventEmitter<string>();
			  }
			  ```
		- **@ViewChild** :
			- Gets a reference to a child component, directive, or DOM element.
			- ```javascript
			  @Component({ ... })
			  export class ExampleComponent implements AfterViewInit {
			    @ViewChild('example') exampleElement: ElementRef;
			  
			    ngAfterViewInit() {
			      console.log(this.exampleElement.nativeElement);
			    }
			  }
			  
			  ```
		- **@ContentChild** :
			- Similar to @ViewChild but for content projected into the component.
			- ```javascript
			  @Component({ ... })
			  export class ExampleComponent implements AfterContentInit {
			    @ContentChild('example') exampleElement: ElementRef;
			  
			    ngAfterContentInit() {
			      console.log(this.exampleElement.nativeElement);
			    }
			  }
			  
			  ```
	-
	- ### Method Decorators
		- **@HostListener** :
			- Listens to events on the host element of the directive or component.
			- ```javascript
			  @Directive({ ... })
			  export class ExampleDirective {
			    @HostListener('click', ['$event'])
			    onClick(event: Event) {
			      console.log('Element clicked', event);
			    }
			  }
			  
			  ```
		- **@HostBinding** :
			- Binds a property to a host element.
			- ```javascript
			  @Directive({ ... })
			  export class ExampleDirective {
			    @HostBinding('class.active') isActive = true;
			  }
			  
			  ```
	-
	- ### Parameter Decorators
		- **@Inject** :
			- Specifies a custom provider for a parameter.
			- ```javascript
			  @Injectable()
			  export class ExampleService {
			    constructor(@Inject('SomeToken') private token: any) {
			      console.log(token);
			    }
			  }
			  
			  ```
		- **@Optional** :
			- Marks a dependency as optional.
			- ```javascript
			  @Injectable()
			  export class ExampleService {
			    constructor(@Optional() private optionalService: OptionalService) {
			      if (optionalService) {
			        // use optionalService
			      } else {
			        // handle absence of optionalService
			      }
			    }
			  }
			  
			  ```