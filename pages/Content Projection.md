- #Angular
- Content projection in Angular allows you to insert content from a parent component into a child component. This is a powerful feature for creating reusable and flexible components.
	- ```javascript
	  // child.component.ts
	  import { Component } from '@angular/core';
	  
	  @Component({
	    selector: 'app-child',
	    template: `
	      <div class="child">
	        <h2>Child Component</h2>
	        <ng-content></ng-content>
	      </div>
	    `,
	    styles: []
	  })
	  export class ChildComponent {}
	  
	  <!-- parent.component.html -->
	  <app-child>
	    <p>This content is projected from the parent component.</p>
	  </app-child>
	  
	  ```
- #### Named Slots
	- Named slots allow more fine-grained control over where specific pieces of content should be projected. You can use the `select` attribute to designate named slots.
	- ```javascript
	  // child.component.ts
	  import { Component } from '@angular/core';
	  
	  @Component({
	    selector: 'app-child',
	    template: `
	      <div class="child">
	        <h2>Child Component</h2>
	        <div class="header">
	          <ng-content select="[header]"></ng-content>
	        </div>
	        <div class="body">
	          <ng-content></ng-content>
	        </div>
	      </div>
	    `,
	    styles: []
	  })
	  export class ChildComponent {}
	  
	  <!-- parent.component.html -->
	  <app-child>
	    <div header>
	      <h3>Header Content</h3>
	    </div>
	    <p>This is the main body content projected from the parent component.</p>
	  </app-child>
	  
	  ```
-
- #### Conditional Content Projection
	- we can conditionally project content using Angular's structural directives like `*ngIf`.
	- ```javascript
	  // child.component.ts
	  import { Component } from '@angular/core';
	  
	  @Component({
	    selector: 'app-child',
	    template: `
	      <div class="child">
	        <h2>Child Component</h2>
	        <ng-content *ngIf="showContent"></ng-content>
	      </div>
	    `,
	    styles: []
	  })
	  export class ChildComponent {
	    showContent = true;
	  }
	  
	  
	  <!-- parent.component.html -->
	  <app-child>
	    <p>This content is conditionally projected based on the child's `showContent` property.</p>
	  </app-child>
	  
	  ```
-
-
- ### Angular Content Projection and Dynamic Template Rendering
-
	- ```javascript
	  <!-- parent.component.html -->
	  <ng-template #AttsTemplate let-name="name">
	    <h1>Hello {{name}}</h1>
	  </ng-template>
	  
	  <app-home [template]="AttsTemplate"></app-home>
	  
	  <!-- child.component.html -->
	  <section *ngFor="let value of values">
	    <ng-container *ngTemplateOutlet="template; context: { name: value }"></ng-container>
	  </section>
	  
	  <!-- child.component.ts -->
	  export classChildComponent {
	    @Input() template: TemplateRef<any>;
	    values = ['John', 'Jane', 'Doe'];
	  }
	  ```