- #Angular
- In Angular, both `ngOnInit` and the constructor are used during the component's initialization phase, but they serve different purposes and are called at different times.
- ### Constructor
	- **Purpose**: The constructor is a feature of TypeScript (and JavaScript classes) used to initialize class members. It is primarily used for dependency injection, where services and other dependencies are injected into the component.
	- **When It’s Called**: The constructor is called when Angular instantiates the component class, before any lifecycle hooks.
- ### ngOnInit
	- **Purpose**: `ngOnInit` is a lifecycle hook provided by Angular. It is intended for component initialization that should occur after Angular has initialized all data-bound properties.
	- **When It’s Called**: `ngOnInit` is called once, after the first `ngOnChanges` and before the view is fully rendered.
-
-
- | Aspect | Constructor | ngOnInit |
  | ---- | ---- | ---- |
  | **Purpose** | Dependency injection and simple initializations | Component initialization logic |
  | **Called** | When the component class is instantiated | After the first `ngOnChanges` and before the view is rendered |
  | **Access to Inputs** | Inputs are not yet resolved | Inputs are resolved and available |
  | **Access to DOM** | No | Yes |
  | **Usage** | Inject dependencies, basic setup | Initialize the component, fetch data, setup complex logic |