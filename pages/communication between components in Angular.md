- #Angular
- In Angular, there are several ways to facilitate communication between components. Here are the main methods:
	- collapsed:: true
	  
	  **Input Binding**: Use `@Input()` decorator to pass data from a parent component to a child component through properties.
		- ```htmlembedded
		  //Parent Component Template:
		  <app-child [message]="parentMessage"></app-child>
		  ```
		- ```javascript
		  //Parent Component TypeScript:
		  import { Component } from '@angular/core';
		  
		  @Component({
		    selector: 'app-parent',
		    templateUrl: './parent.component.html',
		    styleUrls: ['./parent.component.css']
		  })
		  export class ParentComponent {
		    parentMessage = "Message from parent";
		  }
		  ```
		- ```javascript
		  //Child Component TypeScript:
		  import { Component, Input } from '@angular/core';
		  
		  @Component({
		    selector: 'app-child',
		    templateUrl: './child.component.html',
		    styleUrls: ['./child.component.css']
		  })
		  export class ChildComponent {
		    @Input() message: string;
		  }
		  
		  ```
	-
	- collapsed:: true
	  
	  **Output Binding**: Use `@Output()` decorator along with `EventEmitter` to emit events from a child component to its parent component.
		- ```htmlembedded
		  //Child Component Template:
		  <button (click)="sendMessage()">Send Message</button>
		  ```
		- ```javascript
		  //Child Component TypeScript:
		  import { Component, Output, EventEmitter } from '@angular/core';
		  
		  @Component({
		    selector: 'app-child',
		    templateUrl: './child.component.html',
		    styleUrls: ['./child.component.css']
		  })
		  export class ChildComponent {
		    @Output() messageEvent = new EventEmitter<string>();
		  
		    sendMessage() {
		      this.messageEvent.emit("Message from child");
		    }
		  }
		  
		  ```
		- ```htmlembedded
		  //Parent Component Template:
		  <app-child (messageEvent)="receiveMessage($event)"></app-child>
		  ```
		- ```javascript
		  //Parent Component TypeScript:
		  import { Component } from '@angular/core';
		  
		  @Component({
		    selector: 'app-parent',
		    templateUrl: './parent.component.html',
		    styleUrls: ['./parent.component.css']
		  })
		  export class ParentComponent {
		    receivedMessage: string;
		  
		    receiveMessage($event) {
		      this.receivedMessage = $event;
		    }
		  }
		  
		  ```
	-
	- **ViewChild/ViewChildren**: Use `@ViewChild` or `@ViewChildren` decorators to query and access child components or elements from the parent component.
	  collapsed:: true
		-
		- ```javascript
		  //Parent Component TypeScript:
		  import { Component, ViewChild } from '@angular/core';
		  import { ChildComponent } from './child.component';
		  
		  @Component({
		    selector: 'app-parent',
		    templateUrl: './parent.component.html',
		    styleUrls: ['./parent.component.css']
		  })
		  export class ParentComponent {
		    @ViewChild(ChildComponent) childComponent: ChildComponent;
		    showChild: boolean = false;
		  
		    toggleChildVisibility() {
		      this.showChild = !this.showChild;
		    }
		  }
		  
		  ```
		- ```htmlembedded
		  //Child Component Template:
		  <p>Child Component</p>
		  ```
		- ```javascript
		  //Child Component TypeScript:
		  import { Component } from '@angular/core';
		  
		  @Component({
		    selector: 'app-child',
		    templateUrl: './child.component.html',
		    styleUrls: ['./child.component.css']
		  })
		  export class ChildComponent {
		  }
		  
		  ```
	-
	- ***Parent-Child Component Communication using service***: You can use a service to create a communication channel between components that are not directly related in the component tree.
		- ```javascript
		  //shared service
		  import { Injectable } from '@angular/core';
		  import { Subject } from 'rxjs';
		  
		  @Injectable({
		    providedIn: 'root'
		  })
		  export class DataService {
		    private messageSource = new Subject<string>();
		    message$ = this.messageSource.asObservable();
		  
		    sendMessage(message: string) {
		      this.messageSource.next(message);
		    }
		  }
		  
		  ```
		- ```htmlembedded
		  //Parent Component:
		  <button (click)="sendMessageToChild()">Send Message to Child</button>
		  
		  ```
		- ```javascript
		  //Parent Component:
		  import { Component } from '@angular/core';
		  import { DataService } from './data.service';
		  
		  @Component({
		    selector: 'app-parent',
		    templateUrl: './parent.component.html',
		    styleUrls: ['./parent.component.css']
		  })
		  export class ParentComponent {
		    constructor(private dataService: DataService) {}
		  
		    sendMessageToChild() {
		      this.dataService.sendMessage("Message from parent to child");
		    }
		  }
		  
		  ```
		- ```htmlembedded
		  //Child Component Template:
		  <p>Message from parent: {{ messageFromParent }}</p>
		  
		  ```
		- ```javascript
		  //Child Component Template:
		  import { Component, OnInit } from '@angular/core';
		  import { DataService } from './data.service';
		  
		  @Component({
		    selector: 'app-child',
		    templateUrl: './child.component.html',
		    styleUrls: ['./child.component.css']
		  })
		  export class ChildComponent implements OnInit {
		    messageFromParent: string;
		  
		    constructor(private dataService: DataService) {}
		  
		    ngOnInit() {
		      this.dataService.message$.subscribe(message => {
		        this.messageFromParent = message;
		      });
		    }
		  }
		  
		  ```
		-
	-
	- **[[NgRx]] /Redux Store**: Implementing state management solutions like NgRx or Redux allows components to share and synchronize data through a centralized store.
	-
	- **Router Navigation**: Components can communicate indirectly through route parameters, query parameters, or router events when navigating between routes.
		- ```javascript
		  //Navigate with Data
		  
		  ```
		- ```javascript
		  constructor(private router: Router) {
		      const navigation = this.router.getCurrentNavigation();
		      this.data = navigation?.extras.state?.data;
		    }
		  
		  ```
	-
	- **[[EventBus Service]]**: Implement a service as an event bus where components can publish and subscribe to events, enabling communication between unrelated components.
	-
-
-