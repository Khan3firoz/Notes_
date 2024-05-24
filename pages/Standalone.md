- #Angular
- Introduced in Angular version 14, Standalone components offer a new way to define Angular components without the need for NgModules. This simplifies application structure, improves code modularity, and enhances tree-shakability (removing unused code).
- Run ng generate component my-standalone-component --standalone to create a component with the standalone flag set.
- Key Benefits:
	- Reduced Boilerplate: Standalone components eliminate the need for NgModules, streamlining component creation and reducing code verbosity.
	- Improved Modularity: Components become self-contained units, making them easier to reuse and manage dependencies explicitly.
	- Enhanced Tree-Shakability: The Angular compiler can more effectively remove unused code from standalone components, resulting in smaller bundle sizes and faster loading times.
	- Integration with NgModule-Based Applications: Standalone components can coexist with applications using NgModules, providing flexibility in your development approach.
- Standalone Pipes and Directives: Similar to components, pipes and directives can also be marked as standalone using standalone: true in their respective decorators.
- Dependency Injection: Standalone components can inject dependencies from other standalone components or providers defined with provide in bootstrapApplication.
- Lazy Loading: Standalone components can be lazy loaded using the loadComponent function within routing configurations.
-
	- ```javascript
	  import { Component } from '@angular/core';
	  import {CommonModule} from '@angular/common';
	  import {OtherStandAloneComponent} from 'other-stand-alone/other-stand-alone.component';
	  @Component({
	    selector: 'app-my-standalone-component',
	    standalone: true,
	    imports: [CommonModule],
	    template: '<h1>Hello, World!</h1><other-stand-alone></other-stand-alone>'
	  })
	  export class MyStandaloneComponent {}
	  ```
-
- If you intend to use a standalone component within another component that belongs to an NgModule, you can include it in the imports array, as demonstrated below
	- ```javascript
	  import { NgModule } from '@angular/core';
	  import { CommonModule } from '@angular/common'; 
	  import { LandingComponent } from './landing.component';
	  import {OtherStandAloneComponent} from './other-stand-alone/other-stand-alone.component';
	  
	  @NgModule({
	      imports: [CommonModule,OtherStandAloneComponent],
	      declarations: [LandingComponent]
	  })
	  export class LandingModule { }
	  
	  ```
-
- How to Bootstrap an Angular Standalone Component
	- Bootstraping your Angular standalone component is straightforward. In your main.ts file, replace the previous code with the modified code indicated below in red. Make sure to provide the specific standalone component to the bootstrapApplication method. on the index.html, replace app-root with your component.
	- ```javascript
	  import {enableProdMode} from '@angular/core';
	  import {bootstrapApplication} from '@angular/platform-browser';
	  import {StandAloneComponent} from './stand-alone/stand-alone.component';
	  import {environment} from './environments/environment'
	   if(environment.Production){
	    enableProdMode();
	  }
	  bootstrapApplication(StandAloneComponent, { //Bootstraping Standalone
	  providers:[],  
	  })
	  
	  ```
-
- Lazy Loading a Standalone Component
	- Any route can implement lazy loading for its routed standalone component by utilizing the loadComponent() function with the import statement.
	- ```javascript
	  const routes: Routes = [
	  
	    { path: '',
	   loadChildren: () => import('./stand-alone/stand-alone.component').then(m => m.StandAloneComponent) },
	     
	  ]
	  
	  ```