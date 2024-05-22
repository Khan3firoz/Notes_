- #Angular
- *ngFor is a structural directive that renders a template for each item in a collection. It is a repeater directive that iterates over a  collection of data. The directive is placed on an element, which becomes the parent of the cloned templates
	- ```htmlembedded
	  <div *ngFor="let Atts of courses | keyvalue">
	    <span>{{ $any(Atts).key }}: {{ $any(Atts).value }}</span>
	  </div>
	  
	  ```
	- ```htmlembedded
	  <ul>
	    <li *ngFor="let item of items; let i = index">{{ i + 1 }}. {{ item }}</li>
	  </ul>
	  
	  ```
	- ```htmlmixed
	  <ul>
	    <li *ngFor="let item of items | filter: searchTerm">{{ item }}</li>
	  </ul>
	  
	  ```
	- ```htmlmixed
	  <ul>
	    <li *ngFor="let item of items; trackBy: trackByFn">{{ item.id }}</li>
	  </ul>
	  
	  ```
-
-
- ## **New `@for` Syntax:**
	- The `@for` syntax is an alternative to `*ngFor` introduced in Angular.
	- It aims to provide a more concise and readable way to achieve the same result.
	- ```htmlmixed
	  <ul>
	    <li @for="let item of items; let i = index">{{ i + 1 }}. {{ item }}</li>
	  </ul>
	  
	  ```