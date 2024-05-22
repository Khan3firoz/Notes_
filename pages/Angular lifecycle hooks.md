- #Angular
- Angular provides a series of lifecycle hooks that give developers control over the different stages of a component or directive's existence. These hooks allow you to tap into key moments in the component lifecycle, such as creation, updates, and destruction.
-
- `ngOnChanges`: Invoked when input properties change.
- `ngOnInit`: Called once, after the first `ngOnChanges`.
- `ngDoCheck`: Called during every change detection run, immediately after `ngOnChanges` and `ngOnInit`.
- `ngAfterContentInit`: Called once after the component's content (ng-content) has been fully initialized.
- `ngAfterContentChecked` : Called after every check of the component's content (ng-content).
- `ngAfterViewInit`: Called once after the component's view and its child views have been fully initialized.
- `ngAfterViewChecked`: Called after every check of the component's view and child views.
- `ngOnDestroy`: Called once just before the component is destroyed.
-
- ```
           (ngOnChanges)
                |
                v
          Initialization
         (ngOnInit)
                |
                v
            Changes Detected?
           (ngDoCheck) - Yes (Optional)
                |          |
                v          v (No further checks)
          View Initialized  Rendered
         (ngAfterContentInit)(ngAfterViewInit)
                |                  |
                v                  v
            View Checked?      Destroyed
           (ngAfterViewChecked)  (ngOnDestroy) - Yes (Optional)
                |                  |
                v                  v (Component Removal)
                     Component Removed
  
  ```
- The diagram starts with the `Create` phase, where the `ngOnChanges` hook might be called if input properties have initial values.
- An arrow leads to `Initialization`, where `ngOnInit` is called for any setup that doesn't rely on the DOM.
- From there, Angular checks for changes. If changes are detected, the optional `ngDoCheck` hook runs. If not, the flow proceeds.
- Next, the `View Initialized` phase occurs, triggering `ngAfterContentInit` for actions related to the component's projected content.
- Simultaneously, the `Rendered` phase calls `ngAfterViewInit` for actions that require a fully rendered DOM.
- Another optional check (`View Checked`) might use `ngAfterViewChecked` for specific scenarios. If not, the flow continues.
- Finally, the `Destroyed` phase calls `ngOnDestroy` for cleanup tasks when the component is removed.