- #Angular
- Ahead-of-Time (AOT) compilation is a feature provided by Angular that allows you to compile your Angular applications during the build process, rather than at runtime. This contrasts with Just-in-Time (JIT) compilation, where the compilation happens in the browser at runtime. AOT compilation offers several advantages:
	- **Faster Rendering**: AOT-compiled code loads faster because it's already compiled before reaching the client's browser. This can significantly reduce the initial load time of your application, improving user experience, especially on slower devices or networks.
	- **Smaller Bundle Sizes**: AOT compilation removes Angular's compiler from the final bundle sent to the client, reducing the bundle size. Smaller bundles mean faster downloads, which again contributes to improved performance.
	- **Detect Template Errors Earlier**: AOT compilation detects and reports template binding errors during the build process rather than runtime. This helps catch errors early in the development cycle, reducing the chance of errors reaching production.
	- **Improved Security**: Since the template parsing and compilation happen offline during the build process, there's no runtime compilation in the browser. This reduces the risk of client-side template injection attacks.
- to enable AOT compilation by default in the Angular CLI configuration:
	- ```javascript
	  {
	    "angularCompilerOptions": {
	      "fullTemplateTypeCheck": true,
	      "strictInjectionParameters": true
	    }
	  }
	  
	  ```
- Enabling AOT compilation in Angular typically leads to better performance, smaller bundle sizes, and improved security for your applications. However, it's essential to note that AOT compilation might increase build times compared to JIT compilation, as the compilation process is more extensive and happens during build time.