# What is async and await? #Javascript 
heading:: 1

Created: February 9, 2024 12:29 AM
Updated: February 9, 2024 12:30 AM

Async and await are keywords in JavaScript that help you write asynchronous code in a more synchronous-like style. Here's a breakdown:

**Async:**
- **Purpose:** Marks a function as **asynchronous**. This means the function can potentially pause its execution while waiting for something to happen, like fetching data from an API.
- **Behavior:** An `async` function always returns a Promise, even if it doesn't explicitly use one. This Promise resolves with the value returned from the function or rejects if an error occurs.
  
  **Await:**
- **Purpose:** Used **inside an `async` function** to pause its execution and wait for a Promise to resolve or reject.
- **Behavior:** The `await` keyword pauses the function until the Promise it's waiting on resolves or rejects. Once the Promise settles, the resolved value (or the error) becomes the result of the `await` expression.
  
  **Benefits of using async/await:**
- **Improved readability:** Makes asynchronous code look more like synchronous code, leading to easier understanding and maintenance.
- **No need for nested callbacks:** Eliminates the need for complex callback chains, which can be difficult to read and debug.
- **Error handling:** Can handle errors gracefully using `try...catch` blocks within the `async` function.
  
  **Example:**
  
  ```jsx
  async function fetchData() {
  try {
  const response = await fetch('https://api.example.com/data');
  const data = await response.json();
  return data;
  } catch (error) {
  console.error('Error fetching data:', error);
  // Handle error gracefully
  }
  }
  
  fetchData()
  .then(data => {
  console.log('Data:', data);
  })
  .catch(error => {
  console.error('Error:', error);
  });
  
  ```
  
  In this example, the `fetchData` function is `async` and uses `await` to wait for the `fetch` and `json` promises to resolve before returning the data. This makes the code look more like synchronous code while still handling asynchronous operations effectively.
  
  **Remember:**
- `await` can only be used inside `async` functions.
- While `async/await` simplifies asynchronous code, it's important to understand the underlying Promise mechanism for effective error handling and advanced use cases.