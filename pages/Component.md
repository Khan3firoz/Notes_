- Angular components are the fundamental building blocks of your application's user interface (UI). They encapsulate everything needed to display a specific view and manage user interactions within that view. Here's a breakdown of components in Angular:
- Components are a combination of:
	- **TypeScript Class:** Defines the component's behavior and data logic.
	- **HTML Template:** Defines the structure and appearance of the view.
	- **CSS Styles (Optional):** Styles the visual presentation of the component.
- They provide a way to create reusable UI elements that you can combine to build complex and dynamic UIs.
- **Types of Angular Components:**
  
  There's not a strict classification of component types, but here are some ways to categorize them:
	- **Presentational Components:**  Focus on displaying data and user interface elements, with minimal application logic.  These components typically handle user interactions by emitting events to parent components.
	-
	- **Container Components:**  Coordinate and manage child components, often handling complex UI logic and data flow within a specific section of the application.
	-
	- **Standalone Components (Angular v14+):**
	- Standalone components are a new feature introduced in Angular version 14.  They offer a simpler way to create components without the need for a module.They are defined using a dedicated `Component` decorator and don't require a surrounding `@NgModule` decorator.Standalone components are useful for creating small, reusable components that don't require complex module hierarchies.
-
- **Uses of Angular Components:**
	- Building reusable UI elements like buttons, navigation menus, modals, or forms.
	- Organizing your application UI into smaller, manageable pieces.
	- Encapsulating data and logic related to a specific view.
	- Creating dynamic and interactive user interfaces that respond to user actions.
-
- **Common Issues with Angular Components:**
	- **Large, Complex Components:**  Can become difficult to maintain and test. Break down large components into smaller, more focused components for better maintainability.
	- **Tight Coupling:**  Components that rely heavily on each other can make your application less flexible. Use techniques like dependency injection and event communication to loosely couple components.
	- **Poor Reusability:** Components designed for a very specific purpose might be difficult to reuse elsewhere.  Strive for generic and well-designed components that can be adapted to different scenarios.
-
- **Encapsulation:**
- Encapsulation is a mechanism in Angular that controls how a component's styles and logic are isolated from other components. It helps prevent unintended styling conflicts and promotes better code organization.
	- **ViewEncapsulation.Emulated (default):**  Angular creates a shadow DOM-like environment for each component. Styles are scoped to the component's view and don't affect styles in other components.
	- **ViewEncapsulation.None:**  Component styles are applied globally and can potentially affect styles in other components. Use this cautiously to avoid unintended side effects.
	- **ViewEncapsulation.ShadowDom:**  Leverages the browser's native Shadow DOM for true component isolation. Not supported by all browsers yet.
-
- **Change Detection Strategies:**
- Change detection is the process by which Angular detects changes in a component's data and updates the view accordingly.  There are different strategies to control how this happens:
	- **ChangeDetectionStrategy.Default (default):**  Angular checks for changes whenever an event occurs in the application or a timer fires. This is suitable for most components.
	- **ChangeDetectionStrategy.OnPush:**  Angular checks for changes only when an input property changes or an event is triggered specifically for change detection. This is more efficient for components that don't rely on frequent updates from outside.
	- **ChangeDetectionStrategy.Never:**  Angular won't automatically detect changes in this component. You need to manually trigger change detection using a method like `markForCheck()`. Use this cautiously, as it requires careful management.
-
- ## several ways to specify the selector of a component
	- **Element Selector:**
		- Use the component's name as an HTML element within the template of another component.
		- ```javascript
		  @Component({
		    selector: 'app-example',
		    templateUrl: './example.component.html',
		    styleUrls: ['./example.component.css']
		  })
		  export class ExampleComponent {}
		  
		  ```
	- **Attribute Selector**:
		- Use the component as an attribute of an HTML element within the template of another component.
		- ```javascript
		  @Component({
		    selector: '[app-example]',
		    templateUrl: './example.component.html',
		    styleUrls: ['./example.component.css']
		  })
		  export class ExampleComponent {}
		  
		  ```
		- ```htmlembedded
		  <!-- Within another component's template -->
		  <div app-example></div>
		  
		  ```
	- **Class Selector:**
		- Use the component as a class of an HTML element within the template of another component.
		- ```javascript
		  @Component({
		    selector: '.app-example',
		    templateUrl: './example.component.html',
		    styleUrls: ['./example.component.css']
		  })
		  export class ExampleComponent {}
		  
		  ```
		- ```htmlembedded
		  <!-- Within another component's template -->
		  <div class="app-example"></div>
		  
		  ```
	- **Combining Selectors:**
		- You can also combine selectors to make the component available in multiple ways.
		- ```javascript
		  @Component({
		    selector: 'app-example, [app-example], .app-example',
		    templateUrl: './example.component.html',
		    styleUrls: ['./example.component.css']
		  })
		  export class ExampleComponent {}
		  
		  ```
		- ```htmlembedded
		  <!-- Within another component's template -->
		  <app-example></app-example>
		  <div app-example></div>
		  <div class="app-example"></div>
		  
		  ```