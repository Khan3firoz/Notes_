# What are various ways to add images into our App? Explain with code examples [[React]] 
heading:: 1

Created: February 9, 2024 12:31 AM
Updated: February 9, 2024 12:32 AM

Various ways to add images into a React app, incorporating code examples and best practices:

**1. Direct import from the public folder (for small static images):**
- Place your image in the `public` folder.
- Import it directly in your component:
  
  ```jsx
  import React from 'react';
  import logo from './public/logo.png';
  
  function MyComponent() {
  return (
  <div>
    <img src={logo} alt="Logo" />
  </div>
  );
  }
  
  ```
  
  **2. Import from the src folder (for larger, bundled images):**
- Place your image in the `src` folder (preferably within a component folder).
- Import it in your component:
  
  ```jsx
  import React from 'react';
  import myImage from './components/MyComponent/image.jpg';
  
  function MyComponent() {
  return (
  <div>
    <img src={myImage} alt="My Image" />
  </div>
  );
  }
  
  ```
  
  **3. Using require with Webpack (for older projects):**
- Import the image using `require`:
  
  ```jsx
  import React from 'react';
  import myImage from './components/MyComponent/image.jpg';
  
  function MyComponent() {
  return (
  <div>
    <img src={require(myImage)} alt="My Image" />
  </div>
  );
  }
  
  ```
  
  **4. Dynamically fetching images from URLs:**
- Fetch the image using `fetch` or a library like `axios`:
  
  ```jsx
  import React, { useState, useEffect } from 'react';
  
  function MyComponent() {
  const [imageUrl, setImageUrl] = useState('https://example.com/image.jpg');
  
  useEffect(() => {
  // Fetch image URL from an API or other source
  const fetchImageURL = async () => {
    // ... fetch logic
    setImageUrl(fetchedUrl);
  };
  fetchImageURL();
  }, []);
  
  return (
  <div>
    <img src={imageUrl} alt="Fetched Image" />
  </div>
  );
  }
  
  ```
  
  **5. Using image optimization libraries:**
- Consider using libraries like `image-webpack-loader` or `next/image` (in Next.js) to optimize image sizes and loading strategies.
  
  **Best practices:**
- **Optimize image sizes:** Use tools like `jpegoptim` or `pngcrush` to reduce file sizes without significant quality loss.
- **Consider lazy loading:** Load images only when they become visible in the viewport to improve initial page load performance.
- **Use descriptive alt text:** Provide meaningful alt text for accessibility and SEO purposes.
- **Choose the right approach:** Select the method that best suits your image usage patterns and project setup.