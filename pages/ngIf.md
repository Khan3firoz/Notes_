- #Angular
- **Using ngIf in Angular Templates**
- The `*ngIf` structural directive in Angular, which conditionally includes or removes a DOM element based on a given expression.
	- ```htmlembedded
	  <div *ngIf="isLoggedIn">
	    Welcome, {{ username }}!
	  </div>
	  ```
-
	- ```htmlembedded
	  <!-- app.component.html -->
	  <div *ngIf="isLoggedIn; else elseBlock">
	    <p>Welcome, {{ username }}!</p>
	    <button (click)="logout()">Logout</button>
	  </div>
	  <ng-template #elseBlock>
	    <p>Please log in to continue.</p>
	    <button (click)="login()">Login</button>
	  </ng-template>
	  
	  ```
-
	- ```htmlembedded
	  <!-- app.component.html -->
	  <div *ngIf="isLoggedIn; then loggedInTemplate else loggedOutTemplate"></div>
	  
	  <ng-template #loggedInTemplate>
	    <p>Welcome, {{ username }}!</p>
	    <button (click)="logout()">Logout</button>
	  </ng-template>
	  
	  <ng-template #loggedOutTemplate>
	    <p>Please log in to continue.</p>
	    <button (click)="login()">Login</button>
	  </ng-template>
	  
	  ```
-
	- ```htmlembedded
	  <div *ngIf="(post$ | async) as Atts">
	      <span>{{ ($any(Atts).Akhlaque) }}</span>
	      <!-- $any is to give type any -->
	  </div>
	  
	  ```
-
-
- ## New Control Flow Syntax with @if in Angular Templates
	- This markdown code explains the new control flow syntax introduced in Angular templates using the `@if` directive. This syntax provides a more concise and readable way to conditionally render content.
	  
	  **Key Points:**
		- Replaces the need for importing directives like `ngIf` and `ngElse`.
		- Offers a cleaner syntax for conditional logic within templates.
	- **Using the `@if` Directive:**
		- The `@if` directive is used to conditionally include or exclude a block of HTML code based on a given expression. Here's the basic structure:
		- ```htmlembedded
		  <div @if="isLoggedIn">
		    Welcome, {{ username }}!
		  </div>
		  
		  ```
		- ```htmlembedded
		  <div @if="isAdmin">
		      You have administrative access.
		  </div>
		  <div @else @if="hasSpecialPermission">
		      You have special permissions.
		  </div>
		  <div @else>
		      You have standard user access.
		  </div>
		  
		  ```
		- ```htmlembedded
		  ```