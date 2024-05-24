- #Angular
- Just-in-Time (JIT) compilation is the default compilation mode for Angular applications. In JIT compilation, the Angular compiler runs in the client's browser at runtime and compiles the application's templates and components into JavaScript code on-the-fly.
- Here are some key points about JIT compilation:
	- **Dynamic Compilation**: With JIT compilation, the Angular compiler dynamically compiles the application as it loads in the browser. This means that template parsing and compilation happen on the client's device rather than during the build process.
	- **Larger Bundle Sizes**: JIT compilation includes Angular's compiler in the final bundle sent to the client's browser. This increases the bundle size compared to Ahead-of-Time (AOT) compilation, where the compiler is removed from the bundle.
	- **Slower Initial Load Time**: Because compilation occurs in the browser, JIT-compiled applications may have a slower initial load time compared to AOT-compiled applications. The browser needs to compile templates and components before rendering the application, which can result in a delay, especially on slower devices or networks.
	- **Runtime Template Errors**: Since template parsing and compilation happen at runtime, any errors in templates or bindings are detected during application execution. This means that template errors may not be discovered until the application is running, potentially leading to issues reaching production.
-
- While JIT compilation is the default mode for development, it's often recommended to use Ahead-of-Time (AOT) compilation for production builds to benefit from faster rendering, smaller bundle sizes, and improved security. However, JIT compilation can still be useful during development due to its faster build times, which can aid in quicker iteration and debugging.