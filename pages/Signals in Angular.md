- #Angular
- Signals in Angular are a relatively new feature introduced in Angular 17 (still under development preview as of today, March 10, 2024). They offer a powerful way to manage data changes in a reactive style, aiming to improve application performance and simplify state management
- Signals can be thought of as special values that can notify interested parts of your application whenever their value changes.
- They act like wrappers around a value, providing additional functionality like change detection tracking.
- Signals can hold any kind of data, from primitive types like numbers and strings to complex objects.
- Benifits:
	- Improved Performance: Signals enable Angular to perform more granular change detection, updating only the parts of the UI that depend on the changed signal. This can lead to significant performance gains, especially in large applications.
	- Simplified State Management: Signals provide a more reactive approach to managing application state compared to traditional techniques like NgRx or BehaviorSubject. They can simplify data flow and reduce boilerplate code.
	- Easier to Use than RxJS: While RxJS offers powerful reactive primitives, signals can be easier to understand and use for simpler data change scenarios.