### Create the EventBus Service
	- ```javascript
	  ```
-
- ###  Emit an Event from a Component
	- ```java
	  ```
-
- ### Subscribe to an Event in Another Component
	- ```javascript
	  import { Component, OnInit, OnDestroy } from '@angular/core';
	  import { Subscription } from 'rxjs';
	  import { EventBusService } from './event-bus.service';
	  
	  @Component({
	    selector: 'app-details',
	    template: `<p>{{ message }}</p>`
	  })
	  export class DetailsComponent implements OnInit, OnDestroy {
	    message: string = '';
	    private subscription: Subscription;
	  
	    constructor(private eventBusService: EventBusService) {}
	  
	    ngOnInit() {
	      this.subscription = this.eventBusService.on('message').subscribe(data => {
	        this.message = data;
	      });
	    }
	  
	    ngOnDestroy() {
	      if (this.subscription) {
	        this.subscription.unsubscribe();
	      }
	    }
	  }
	  
	  ```