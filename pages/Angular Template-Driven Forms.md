- #Angular
- Template-driven forms rely on Angular's `FormsModule` and use Angular directives to bind HTML form elements to data properties in the component class.
-
	- ```htmlmixed
	  <!-- template-driven-form.component.html -->
	  <form (ngSubmit)="onSubmit()">
	  <label for="name">Name:</label>
	  <input type="text" id="name" name="name" [(ngModel)]="user.name" required minlength="3">
	  <div *ngIf="name.invalid && name.touched">
	    <small *ngIf="name.errors?.required">Name is required.</small>
	    <small *ngIf="name.errors?.minlength">Name must be at least 3 characters long.</small>
	  </div>
	    
	    <label for="email">Email:</label>
	    <input type="email" id="email" name="email" [(ngModel)]="user.email">
	  
	    <button type="submit">Submit</button>
	  </form>
	  
	  ```
	- ```javascript
	  export class TemplateDrivenFormComponent {
	    user = {
	      name: '',
	      email: ''
	    };
	  
	    onSubmit() {
	      console.log('Form Submitted!', this.user);
	    }
	  }
	  ```