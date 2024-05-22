# React Router #React 
heading:: 1

Created: February 9, 2024 12:52 AM
Updated: February 9, 2024 12:52 AM
- ## **React Router: Mastering Navigation in Your React Apps**
  heading:: 2
  
  React Router is an essential library for building dynamic and user-friendly single-page applications (SPAs) in React. It empowers you to manage navigation, define routes, and create a seamless user experience for your web app. In this document, we'll explore the core concepts of React Router:
  
  **Navigation with React Router:**
- **Basic routing:** Handle navigation between different views based on URL changes. For example, route to a "/products" page to display product listings and "/product/:id" to show a specific product detail.
- **Link component:** Use the `Link` component to declaratively define navigation links within your components. Clicking a `Link` triggers navigation without a full page reload, enhancing user experience.
- **Programmatic navigation:** Navigate programmatically using the `useNavigate` hook to redirect users based on actions within your application.
  
  **Nested Routes and Route Parameters:**
- **Nested routes:** Create hierarchical route structures to represent complex application sections. Imagine having `/categories/:category/products` to navigate through product categories and individual products.
- **Route parameters:** Capture dynamic parts of URLs using placeholders like `:id` in route paths. These parameters are accessible within your components to handle dynamic content rendering.
  
  **Route Guards and Lazy Loading:**
- **Route guards:** Control access to specific routes based on conditions like authentication status or permissions. This allows you to protect sensitive areas of your application.
- **Lazy loading:** Improve initial load times by loading components only when necessary. With lazy loading, components for specific routes are loaded upon navigation, reducing the initial bundle size and enhancing performance.
  
  **Example:**
  
  Consider an e-commerce application with these routes:
- `/`: Home page
- `/products`: Product listing page
- `/products/:id`: Product detail page
- `/cart`: Shopping cart page
  
  Here's a simplified example using React Router v6:
  
  **JavaScript**
  
  ```jsx
  import { BrowserRouter, Routes, Route, Link } from 'react-router-dom';
  
  function App() {
  return (
  <BrowserRouter>
    <nav>
      <Link to="/">Home</Link>
      <Link to="/products">Products</Link>
      <Link to="/cart">Cart</Link>
    </nav>
    <Routes>
      <Route path="/" element={<Home />} />
      <Route path="/products" element={<ProductList />} />
      <Route path="/products/:productId" element={<ProductDetails />} />
      <Route path="/cart" element={<Cart />} />
    </Routes>
  </BrowserRouter>
  );
  }
  
  function Home() {
  // ... Home page content
  }
  
  function ProductList() {
  // ... Product listing logic and rendering
  }
  
  function ProductDetails({ match }) {
  // Access product ID from match.params.productId
  // ... Product detail logic and rendering
  }
  
  function Cart() {
  // ... Cart functionality and items display
  }
  
  ```