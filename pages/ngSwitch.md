- #Angular
- The `[ngSwitch]` directive in Angular adds or removes templates based on whether the expression matches the switch expression. It allows you to conditionally render a section of HTML only if it corresponds to a specific value. The expressions to match are provided by the `*ngSwitchCase` directive.
  
  Here are the key points about `[ngSwitch]`:
- **Usage**:
	- `[ngSwitch]` is used as a property binding, and the `*` symbol is used with the `*ngSwitchCase` and `*ngSwitchDefault` directives.
	- The `*ngSwitchCase` directive defines a condition that, when matched with the expression, will render the associated element.
	- Every view that matches a case is rendered. If there are no matches, the `*ngSwitchDefault` directive is rendered.
	- ```htmlmixed
	  <div [ngSwitch]="course">
	    <p *ngSwitchCase="'AAS'">Architectural Technology</p>
	    <p *ngSwitchCase="'BBA'">Bachelor of Business Administration</p>
	    <p *ngSwitchDefault>HEA, using MatchPath</p>
	  </div>
	  
	  ```
-
- ### New control flow
	- ```htmlmixed
	  <div @switch="selectedValue">
	    <p @case="'option1'">Option 1 is selected.</p>
	    <p @case="'option2'">Option 2 is selected.</p>
	    <p @default>Default case.</p>
	  </div>
	  
	  ```