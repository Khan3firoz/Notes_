- Observables vs Promises #Angular #Rxjs
- Observables and Promises are two key concepts in asynchronous programming in JavaScript and TypeScript, especially in the context of Angular. While both are used to handle asynchronous operations, they have significant differences in terms of functionality, capabilities, and use cases.
-
- ### Promises
	- A Promise represents a single future value. It's a one-time, immutable object that will either resolve to a value or reject with an error.
	- #### Key Features:
		- **Single Value**: A Promise resolves or rejects with a single value.
		- **Eager Execution**: A Promise starts executing immediately when it is created.
		- **Not Cancellable**: Once created, a Promise cannot be cancelled.
		- **Simpler API**: Promises have a straightforward API with `.then()`, `.catch()`, and `.finally()`.
		- ```javascript
		  const promise = new Promise((resolve, reject) => {
		    setTimeout(() => {
		      resolve('Promise resolved!');
		    }, 1000);
		  });
		  
		  promise.then(value => {
		    console.log(value);
		  }).catch(error => {
		    console.error(error);
		  });
		  
		  ```
	- #### Use Cases:
		- **One-Time Operations**: Useful for operations that only need to happen once, such as fetching data from an API.
		- **Sequential Execution**: Ideal for chaining asynchronous operations that need to be executed in sequence.
-
- ### Observables
	- An Observable is a stream of values or events over time, which can be synchronous or asynchronous. It allows multiple values to be emitted.
	- #### Key Features:
		- **Multiple Values**: An Observable can emit multiple values over time.
		- **Lazy Execution**: An Observable does not start emitting values until it is subscribed to.
		- **Cancellable**: Observables can be unsubscribed from, stopping the emission of values.
		- **Rich API**: Observables have a comprehensive API for operations like map, filter, reduce, retry,
		- ```javascript
		  import { Observable } from 'rxjs';
		  
		  const observable = new Observable(subscriber => {
		    setTimeout(() => {
		      subscriber.next('First value');
		    }, 1000);
		  
		    setTimeout(() => {
		      subscriber.next('Second value');
		    }, 2000);
		  
		    setTimeout(() => {
		      subscriber.complete();
		    }, 3000);
		  });
		  
		  const subscription = observable.subscribe({
		    next(value) {
		      console.log(value);
		    },
		    complete() {
		      console.log('Observable completed!');
		    }
		  });
		  
		  // To cancel the subscription
		  subscription.unsubscribe();
		  
		  ```
	- #### Use Cases:
		- **Streams of Data**: Ideal for handling streams of data or events such as user inputs, WebSocket messages, or data polling.
		- **Reactive Programming**: Supports reactive programming paradigms, enabling more complex asynchronous scenarios.
		- **Composition and Transformation**: Useful for composing and transforming multiple asynchronous streams with powerful operators.
- | Feature | Promises | Observables |
  | ---- | ---- | ---- |
  | **Value Emission** | Single value | Multiple values over time |
  | **Execution** | Eager | Lazy |
  | **Cancellability** | Not cancellable | Cancellable (via unsubscribe) |
  | **Operators** | Limited (`then`, `catch`) | Extensive (map, filter, etc.) |
  | **Use Case** | One-time async operations | Streams of events/data |
  | **Concurrency Handling** | Basic | Advanced |
  | **Error Handling** | `.catch()` | `.subscribe({ error })` |
  | **Composability** | Limited chaining | High composability |