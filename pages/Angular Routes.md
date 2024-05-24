- #Angular
- In traditional web application, when the user types a URL in the browser, a HTTP request is sent to the server, which then retrieves  the HTML page. For each new URL, the user is redirected to a new HTML page.
- In case of single page application we do not load the whole application, we are only loading a part of the application. This is done  with the help of angular routers. Angular routers allow us to create client-side routes
- Angular's Router module provides a powerful way to manage navigation and URL-based views in your application.it allows us to switch from one view to another as users perform application tasks. It enables developers to build  Single Page Applications with multiple views and allows navigation between these components.
-
- ## Navigation Options
	- ```javascript
	   this.router.navigate(['/about']);
	  ```
	- ```htmlmixed
	  <!-- Link to UserComponent with a dynamic user ID and query parameters -->
	  <a [routerLink]="['/user', userId]" [queryParams]="{ ref: 'email' }">View User</a>
	  ```
	- ```htmlmixed
	  this.router.navigate(['/user', 123], { queryParams: { ref: 'button' } });
	  ```
	- ```javascript
	   this.router.navigate(['/home'], { 
	        queryParams: { welcome: 'true' }, 
	        fragment: 'top',
	        queryParamsHandling: 'merge' // 'merge' or 'preserve'
	      });
	  ```
	- ```htmlmixed
	  <ul class="nav">
	    <li routerLinkActive="active" [routerLinkActiveOptions]="{ exact: true }"><a routerLink="/">Home</a></li>
	    <li routerLinkActive="active"><a routerLink="/about">About</a></li>
	    <li routerLinkActive="active"><a routerLink="/blog">Blog</a></li>
	  </ul>
	  
	  /*
	  [routerLinkActiveOptions]="{ exact: true }": This option specifies that the routerLinkActive
	  directive should only consider the exact route path for matching. Without this option, a 
	  parent route match would also activate the active class.
	  */
	  ```
- ## Route Configuration Options
	- Route configuration options include properties like `path`, `component`, `redirectTo`, `pathMatch`, and `data`.
	- ```javascript
	  const routes: Routes = [
	    { path: '', redirectTo: '/home', pathMatch: 'full' },
	    { path: 'home', component: HomeComponent, data: { title: 'Home' } }
	  ];
	  ```
-
- ## Route Parameters
	- Route parameters are used to pass data to routes. Here’s how to define and retrieve them.
	- ```javascript
	  // In your routing module
	  const routes: Routes = [
	    { path: 'user/:id', component: UserComponent }
	  ];
	  
	  // In your component
	  import { ActivatedRoute } from '@angular/router';
	  
	  @Component({
	    selector: 'app-user',
	    template: `<div>User ID: {{ userId }}</div>`
	  })
	  export class UserComponent {
	    userId: string;
	  
	    constructor(private route: ActivatedRoute) {
	      this.userId = this.route.snapshot.paramMap.get('id')!;
	    }
	  }
	  ```
-
- **RouterLink**
	- RouterLink is a directive that allows you to create links to different routes within your app. It's commonly used in navigation menus.
- **RouterOutlet**
	- RouterOutlet is a directive that acts as a placeholder for the component that will be displayed when a route is activated.
-
- ## Route Guards
	- Route guards protect routes, enforce constraints, and perform checks on specific routes. Some use cases for route guards include:
	- Preventing an anonymous user from accessing certain pages (e.g., profile page).
	- Restricting access to specific routes based on user roles.
	- Ensuring a smooth user experience by controlling navigation.
	- Angular provides different types of route guards:
		- **CanActivate**: Determines if a route can be activated.
		- **CanActivateChild**: Similar to `CanActivate`, but for child routes.
		- **CanDeactivate**: Checks if a user can leave a page (e.g., when there are pending edits).
		- **CanLoad**: Prevents lazy-loaded modules from loading until certain conditions are met.
	- ```javascript
	  import { Injectable } from '@angular/core';
	  import { CanActivate, Router } from '@angular/router';
	  import { AuthService } from './auth.service';
	  
	  @Injectable({
	    providedIn: 'root'
	  })
	  export class AuthGuard implements CanActivate {
	  
	    constructor(private authService: AuthService, private router: Router) {}
	  
	    canActivate(): boolean {
	      if (this.authService.isLoggedIn()) {
	        return true;
	      } else {
	        this.router.navigate(['/login']);
	        return false;
	      }
	    }
	  }
	  
	  // In your routing module
	  const routes: Routes = [
	    { path: 'protected', component: ProtectedComponent, canActivate: [AuthGuard] }
	  ];
	  ```
-
- ## Resolvers
	- Resolvers pre-fetch data before a route is activated. They ensure that necessary data is available before rendering a component. Use resolvers to improve performance and avoid flickering content.
	- ```javascript
	  import { Injectable } from '@angular/core';
	  import { Resolve } from '@angular/router';
	  import { UserService } from './user.service';
	  
	  @Injectable({
	    providedIn: 'root'
	  })
	  export class UserResolver implements Resolve<any> {
	  
	    constructor(private userService: UserService) {}
	  
	    resolve() {
	      return this.userService.getUser();
	    }
	  }
	  
	  // In your routing module
	  const routes: Routes = [
	    { path: 'user/:id', component: UserComponent, resolve: { user: UserResolver } }
	  ];
	  ```
-
- ## Lazy Loading
	- Lazy loading improves application performance by loading modules only when needed. Here’s how to set up a lazy-loaded feature module:
	- Create the feature module using the Angular CLI with the `--route` flag.
	- Configure the routes for the lazy-loaded module.
	- Set up an application link to trigger the lazy loading.
	- ```javascript
	  const routes: Routes = [
	    {
	      path: 'admin',
	      loadChildren: () => import('./admin/admin.module').then(m => m.AdminModule)
	    }
	  ];
	  ```
-
- ## Auxiliary Routes
	- Auxiliary routes (or named outlets) allow you to display multiple routes in a single view.
	- ```javascript
	  // In your routing module
	  const routes: Routes = [
	    { path: 'home', component: HomeComponent },
	    { path: 'aux', component: AuxComponent, outlet: 'aux' }
	  ];
	  
	  // In your template
	  <router-outlet></router-outlet>
	  <router-outlet name="aux"></router-outlet>
	  ```
-
-
- ## Preloading Strategies
	- Preloading strategies load modules in the background to improve the user experience. Angular provides a `PreloadAllModules` strategy.
	- ```javascript
	  import { NgModule } from '@angular/core';
	  import { RouterModule, Routes, PreloadAllModules } from '@angular/router';
	  
	  const routes: Routes = [
	    { path: 'feature', loadChildren: () => import('./feature/feature.module').then(m => m.FeatureModule) }
	  ];
	  
	  @NgModule({
	    imports: [RouterModule.forRoot(routes, { preloadingStrategy: PreloadAllModules })],
	    exports: [RouterModule]
	  })
	  export class AppRoutingModule { }
	  ```
-
-
- ### Wildcard Routes in Angular
	- Wildcard routes in Angular are used to handle undefined or non-existent routes in your application. These routes act as a catch-all for any paths that do not match a defined route, commonly used for displaying a 404 Not Found page.
	- To set up a wildcard route, you add a route definition with the path `**` in your routing module. This route should typically be placed at the end of your route definitions to ensure that it only catches routes that have not been matched by any other route.