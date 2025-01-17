- #Angular
- [[draws/2024-05-19-13-59-33.excalidraw]]
-
-
- ## Angular 10 Features
	- **Optional Stricter Setting**:
		- Angular 10 provides a stricter project setup for making a new workspace using `ng new --strict`.
	- **Boost in ngcc Performance**:
		- You can see a boost in performance that is accomplished by lowering the entry point’s size.
	- **TSLint v6, TSLib 2.9, and Typescript 3.9**:
		- Versions updated for improving editing experience, accelerating the compiler, rapid fixes, and completions.
	- **Removal and Corrections**:
		- ESM5 bundles have been taken out from the Angular Package Format. Assistance for some old browsers like Internet Explorer Mobile has also been taken out.
	- **Compiler Update**:
		- A compiler interface has been added in the most recent Angular 10 to cover the actual ngtsc compiler. `ng-content` selectors, dependency data, and Angular language service have also been added to the metadata.
- ## Angular 11 Features
	- **Experimental webpack5 Support**:
		- Can opt-in to webpack v5. Faster and smaller builds with persistent disk caching.
	- **Automatic Inlining of Fonts**:
		- During compile time Angular CLI will download and inline fonts that are being used and linked in the application.
	- **Typescript 4.0 Supported**:
		- Versions updated for improving editing experience, accelerating the compiler, rapid fixes, and completions.
	- **Linting**:
		- TSLint is deprecated by the project creators who recommend migration to ESLint.
	- **Updated Hot Module Replacement (HMR) Support**:
		- In version 11, they’ve updated the CLI to allow enabling HMR when starting an application with `ng serve --hmr`. When they make a change in the code, what they have changed will be updated without any loss of the data in the form.
- ## Angular 12 Features
	- **Ivy Everywhere**
		- Removed the deprecated View Engine to make Ivy Everywhere a reality.
		- During compile time Angular CLI will download and inline fonts that are being used and linked in the application.
	- **Stricter Message IDs**
		- Making the standard message-id design stronger and better.
	- **Nullish Coalescing Operator**
		- Introduced the nullish coalescing operator (??) to write cleaner code for conditionals.
	- **Improvements around Styles**
		- Support for inline SASS in the styles field for component decorator without including any inline Style Language option to your angular json file.
		- Support for Tailwind CSS
- ## Angular 13 Features
	- **100% Ivy**
		- Angular 13 is now fully compatible with Ivy, and the View Engine is no longer supported.
	- **FormControlStatus**
		- This feature introduces a new class, `FormControlStatus`, that simplifies working with form controls. It consolidates all status strings into a single class, making code more readable and maintainable.
	- **Version Updates**
		- Angular 13 includes updated versions of various dependencies to improve the development experience. These updates can lead to faster compilation times, better autocompletion, and more bug fixes.
	- **Changes to Angular Package Format (APF)**
		- The Angular Package Format (APF) has been updated in Angular 13 with several key changes:
			- No more production of UMD bundles.
			- Generates ES2020 output by default.
			- Creates Ivy partial compilation output.
	- **Angular CLI Enhancements**
		- The Angular CLI has been enhanced in Angular 13 to improve development speed. One of the key improvements is the introduction of a persistent build cache by default, leading to up to a 68% improvement in development build times.
- ## Angular 14 Features
	- **Standalone Components**: Creates components without the need for NgModules, reducing boilerplate code.
	- **Improved Type Safety**: Enhances type safety for forms.
	- **Enhanced Page Title Management** : Setting and updating page titles is easier, improving accessibility for users.
	- **Extended Developer Diagnostics** : Provides more detailed information during development and debugging, aiding in quicker issue resolution.
	- **Optional Injectors in Embedded Views** :Allows you to specify optional injectors when creating embedded views using `ViewContainerRef.createEmbeddedView` and `TemplateRef.createEmbeddedView`.
- ## Angular 15 Features
	- **Stabilized Standalone Components**: Angular 14's introduction of standalone components is now stabilized in Angular 15. This API allows you to build multi-route applications without NgModules.
	- **Router Standalone API**:
		- **Tree-shakeability**: Improves performance by removing unused code.
		- **Simplified Router Configuration**: Makes setting up routes easier and more intuitive.
	- **Functional Route Guards** : Angular 15 introduces functional route guards, allowing for simpler and more readable code compared to the previous class-based guards.
	- **NGOptimizedImage Directive**: This directive enhances image loading efficiency, leading to better performance and user experience.
- ## Angular 16 Features
	- **Signals** (Experimental)
		- Introduces a new experimental feature for handling data dependencies with a reactive model.
	- **Typed Component Inputs**
		- Enforces type safety for component inputs by making them optional by default.
	- **Non-Destructive Hydration** (Experimental)
		- Improves the performance of server-side rendered Angular applications.
		- Instead of completely rebuilding the DOM on the client, non-destructive hydration enriches the existing DOM.
	- **DestroyRef Injector**
		- Provides a convenient way to manage cleanup operations in components, directives, and other entities.
	- **Self-Closing Tags & Typescript 5 Support**
		- Allows you to use self-closing tags for components and adds support for Typescript 5.
- ## Angular 17 Features
	- **Built-in Control Flow** (Preview)
		- Introduces a new syntax for control flow directly within templates, offering a more declarative and ergonomic way to manage conditional logic and loops. This leads to cleaner and easier-to-read templates.
	- **Faster Builds with esbuild**
		- The Angular CLI now leverages esbuild as the default build optimizer, resulting in significantly faster build times compared to previous versions.
	- **Improved Initial Load Times**
		- This feature optimizes how Angular loads and renders modules, allowing it to prioritize critical parts of your application for faster initial load times.
	- **Improved Server-Side Rendering (SSR)**
		- Angular 17 introduces various improvements to SSR, including support for lazy loading and differential hydration, contributing to smoother & faster page loads and better SEO.
	- **Custom Element Bindings and Element Providers**
		- This feature expands the scope of custom elements in Angular, enabling you to leverage them more effectively within your applications.
-
-
-