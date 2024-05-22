- ```
  # Install NgRx
  ng add @ngrx/store
  ```
- **Create Actions**:
	- ```
	  // message.actions.ts
	  import { createAction, props } from '@ngrx/store';
	  
	  export const setMessage = createAction('[Message] Set Message', props<{ message: string }>());
	  
	  ```
- **Create Reducer**:
	- ```
	  // message.reducer.ts
	  import { createReducer, on } from '@ngrx/store';
	  import * as MessageActions from './message.actions';
	  
	  export const initialState = '';
	  
	  export const messageReducer = createReducer(
	    initialState,
	    on(MessageActions.setMessage, (state, { message }) => message)
	  );
	  
	  ```
- **Create Selectors**:
	- ```
	  // message.selectors.ts
	  import { createSelector, createFeatureSelector } from '@ngrx/store';
	  import { AppState } from './app.state';
	  
	  export const selectMessage = createSelector(
	    (state: AppState) => state.message,
	    message => message
	  );
	  
	  ```
- **Update AppModule**:
	- ```
	  // app.module.ts
	  import { StoreModule } from '@ngrx/store';
	  import { messageReducer } from './message.reducer';
	  
	  @NgModule({
	    imports: [
	      StoreModule.forRoot({ message: messageReducer })
	    ],
	  })
	  export class AppModule { }
	  
	  ```
- **Dispatch Action from Parent Component**:
	- ```
	  // parent.component.ts
	  import { Store } from '@ngrx/store';
	  import { AppState } from './app.state';
	  import * as MessageActions from './message.actions';
	  
	  @Component({
	    selector: 'app-parent',
	    templateUrl: './parent.component.html',
	    styleUrls: ['./parent.component.css']
	  })
	  export class ParentComponent {
	    constructor(private store: Store<AppState>) {}
	  
	    sendMessageToChild() {
	      this.store.dispatch(MessageActions.setMessage({ message: "Message from parent to child" }));
	    }
	  }
	  
	  ```
- **Access State in Child Component**:
	- ```
	  // child.component.ts
	  import { Store, select } from '@ngrx/store';
	  import { AppState } from './app.state';
	  import { Observable } from 'rxjs';
	  import { selectMessage } from './message.selectors';
	  
	  @Component({
	    selector: 'app-child',
	    templateUrl: './child.component.html',
	    styleUrls: ['./child.component.css']
	  })
	  export class ChildComponent {
	    messageFromParent$: Observable<string>;
	  
	    constructor(private store: Store<AppState>) {
	      this.messageFromParent$ = this.store.pipe(select(selectMessage));
	    }
	  }
	  
	  ```
- **Use Message in Child Component Template**:
	- ```
	  <!-- child.component.html -->
	  <p>Message from parent: {{ messageFromParent$ | async }}</p>
	  
	  ```
- This example demonstrates how to use NgRx for state management in Angular to share and synchronize data between parent and child components through a centralized store.