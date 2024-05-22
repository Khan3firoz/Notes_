# What is difference between Client Side Routing and Server Side Routing? #WebDev 
heading:: 1

Created: February 9, 2024 12:37 AM
Updated: February 9, 2024 12:38 AM
- ## **Client-Side Routing (CSR) vs. Server-Side Routing (SSR)**
  heading:: 2
  
  | Feature | Client-Side Routing (CSR) | Server-Side Routing (SSR) |
  | --- | --- | --- |
  | Navigation | Happens on client-side | Happens on server-side |
  | Page loading | Dynamic updates without full reload | Full page reload on each navigation |
  | Performance | Fast perceived performance after initial load | Slower initial load, faster subsequent navigations |
  | SEO | Less SEO-friendly out-of-the-box | More SEO-friendly by default |
  | Complexity | More complex setup and development | Simpler development initially |
  
  **Additional considerations:**
- **Initial load time:** For applications with large amounts of content, SSR can improve initial load speed.
- **Scalability:** As applications grow, managing data fetching and rendering on the client-side in CSR can become more complex.
- **Development skills:** Working with CSR requires a good understanding of JavaScript and routing libraries.