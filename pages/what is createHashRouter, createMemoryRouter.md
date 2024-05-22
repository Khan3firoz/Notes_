# what is createHashRouter, createMemoryRouter from React Router docs. #React
heading:: 1

Created: February 9, 2024 12:40 AM
Updated: February 9, 2024 12:41 AM

In React Router v6, `createHashRouter` and `createMemoryRouter` are two alternative routers provided for specific cases:

**1. createHashRouter:**
- Purpose: Enables routing using the hash portion (`#`) of the URL instead of full paths. This is typically used when:
	- Your web server cannot be configured to serve your React application's routes directly (e.g., static file servers like GitHub Pages).
	- You have legacy browsers that don't support the History API for full path URL manipulation.
- Behavior: Similar to `createBrowserRouter` (the default router in v6), but it manages navigation using the hash fragment of the URL, not the full path.
  
  **2. createMemoryRouter:**
- Purpose: Provides a router for testing or isolation purposes where you don't want to interact with the browser's history API.
- Behavior: Works in memory, simulating navigation but not making actual requests to a server. Useful for unit testing components and ensuring they handle route changes correctly.
  
  **Key differences:**
  
  | Feature | createBrowserRouter | createHashRouter | createMemoryRouter |
  | --- | --- | --- | --- |
  | URL manipulation | Full paths | Hash portion | In-memory |
  | Server requests | Yes | No | No |
  | Use case | Web applications | Limited server config, legacy browsers | Testing, isolation |
  
  **Remember:**
- While `createHashRouter` can be a workaround for limited server environments, `createBrowserRouter` is generally recommended for most web applications due to its cleaner URLs and better SEO.
- `createMemoryRouter` is strictly for testing or specific development scenarios, not for production use.