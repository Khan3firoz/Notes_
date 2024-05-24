- #Angular
- Angular's `ngTemplateOutlet` directive allows us to define and render template content with full control over how and when the content is displayed. It can be especially useful for scenarios where you need to dynamically switch between different templates or reuse a single template in multiple places with different contexts.
	- ```htmlmixed
	  <ng-template #templateRef>
	    <span>Content to Show</span>
	  </ng-template>
	  
	  <header>
	    <ng-container *ngTemplateOutlet="templateRef"></ng-container>
	  </header>
	  
	  ```
- #### Passing Context to the Template
	- ```htmlmixed
	  // Define Template with Variables:
	  
	  <ng-template #templateRef let-data let-a="age" let-n="nickName">
	    <span>{{data}} {{a}} {{n}}</span>
	  </ng-template>
	  
	  // Pass Context to Template:
	  <header>
	    <ng-container *ngTemplateOutlet="templateRef; context: {$implicit: 'Akhlaque', age: 22, nickName: 'AtTs'}"></ng-container>
	  </header>
	  
	  ```