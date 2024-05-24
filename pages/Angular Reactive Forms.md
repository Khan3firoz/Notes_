- #Angular
-
- Reactive forms in Angular provide a model-driven approach to handling form inputs. They offer more control and flexibility compared to template-driven forms, making them ideal for complex form scenarios.
-
	- ```javascript
	  export class ReactiveFormComponent implements OnInit {
	    userForm: FormGroup;
	  
	    constructor(private fb: FormBuilder) {}
	  
	    ngOnInit() {
	      this.userForm = this.fb.group({
	        name: ['', [Validators.required, Validators.minLength(3)]],
	        email: ['', [Validators.required, Validators.email]],
	        password: ['', [Validators.required, Validators.minLength(6)]],
	        age: ['', [Validators.required, Validators.min(18), Validators.max(65)]],
	        gender: ['', Validators.required],
	        terms: [false, Validators.requiredTrue]
	      });
	    }
	  
	    onSubmit() {
	      if (this.userForm.valid) {
	        console.log('Form Submitted!', this.userForm.value);
	      }
	    }
	  }
	  ```
	- ```htmlmixed
	  <!-- reactive-form.component.html -->
	  <form [formGroup]="userForm" (ngSubmit)="onSubmit()">
	    <div>
	      <label for="name">Name</label>
	      <input type="text" id="name" formControlName="name">
	      <div *ngIf="userForm.get('name').invalid && userForm.get('name').touched">
	        <small *ngIf="userForm.get('name').errors?.required">Name is required.</small>
	        <small *ngIf="userForm.get('name').errors?.minlength">Name must be at least 3 characters long.</small>
	      </div>
	    </div>
	  
	    <div>
	      <label for="email">Email</label>
	      <input type="email" id="email" formControlName="email">
	      <div *ngIf="userForm.get('email').invalid && userForm.get('email').touched">
	        <small *ngIf="userForm.get('email').errors?.required">Email is required.</small>
	        <small *ngIf="userForm.get('email').errors?.email">Enter a valid email.</small>
	      </div>
	    </div>
	  
	    <div>
	      <label for="password">Password</label>
	      <input type="password" id="password" formControlName="password">
	      <div *ngIf="userForm.get('password').invalid && userForm.get('password').touched">
	        <small *ngIf="userForm.get('password').errors?.required">Password is required.</small>
	        <small *ngIf="userForm.get('password').errors?.minlength">Password must be at least 6 characters long.</small>
	      </div>
	    </div>
	  
	    <div>
	      <label for="age">Age</label>
	      <input type="number" id="age" formControlName="age">
	      <div *ngIf="userForm.get('age').invalid && userForm.get('age').touched">
	        <small *ngIf="userForm.get('age').errors?.required">Age is required.</small>
	        <small *ngIf="userForm.get('age').errors?.min">Age must be at least 18.</small>
	        <small *ngIf="userForm.get('age').errors?.max">Age must be under 65.</small>
	      </div>
	    </div>
	  
	    <div>
	      <label for="gender">Gender</label>
	      <select id="gender" formControlName="gender">
	        <option value="" disabled>Select Gender</option>
	        <option value="male">Male</option>
	        <option value="female">Female</option>
	        <option value="other">Other</option>
	      </select>
	      <div *ngIf="userForm.get('gender').invalid && userForm.get('gender').touched">
	        <small *ngIf="userForm.get('gender').errors?.required">Gender is required.</small>
	      </div>
	    </div>
	  
	    <div>
	      <label for="terms">
	        <input type="checkbox" id="terms" formControlName="terms">
	        Accept Terms and Conditions
	      </label>
	      <div *ngIf="userForm.get('terms').invalid && userForm.get('terms').touched">
	        <small *ngIf="userForm.get('terms').errors?.required">You must accept the terms and conditions.</small>
	      </div>
	    </div>
	  
	    <button type="submit" [disabled]="userForm.invalid">Submit</button>
	  </form>
	  
	  ```