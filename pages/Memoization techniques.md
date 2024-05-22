# Memoization techniques #WebDev 
heading:: 1

Created: February 9, 2024 12:57 AM
Updated: February 9, 2024 12:58 AM
- ## **Memoization Techniques: Boost Performance by Remembering Results**
  heading:: 2
  
  Memoization is an optimization technique used to speed up functions by storing and reusing the results of previous calculations for the same inputs. This can significantly improve performance, especially for functions that involve expensive computations or repetitive calculations.
  
  Here are some common memoization techniques:
  
  **1. Caching:**
- Store the results of function calls in a dedicated cache object, using the input as the key.
- When the same input is encountered again, retrieve the result from the cache instead of recalculating.
  
  **Example (using a simple cache object):**
  
  **JavaScript**
  
  ```
  const cache = {};
  
  function fibonacci(n) {
  if (n === 0 || n === 1) {
  return n;
  }
  if (cache[n]) {
  return cache[n];
  } else {
  const result = fibonacci(n - 1) + fibonacci(n - 2);
  cache[n] = result;
  return result;
  }
  }
  
  ```
  
  **2. Dynamic Programming:**
- Build up the solution to a problem incrementally, storing intermediate results at each step.
- This avoids redundant calculations for subproblems with overlapping inputs.
  
  **Example (dynamic programming for knapsack problem):**
  
  **JavaScript**
  
  ```
  function knapsack(weights, values, capacity) {
  const dp = Array(capacity + 1).fill(0);
  
  for (let i = 1; i <= capacity; i++) {
  for (let j = 0; j < weights.length; j++) {
    if (weights[j] <= i) {
      dp[i] = Math.max(dp[i], dp[i - weights[j]] + values[j]);
    }
  }
  }
  
  return dp[capacity];
  }
  
  ```
  
  **3. Higher-Order Functions (HOFs):**
- Use HOFs like `memoize` (from libraries like lodash) to automatically wrap functions and memoize their results.
  
  **Example (using lodash memoize):**
  
  **JavaScript**
  
  ```
  const memoizedFibonacci = _.memoize(fibonacci);
  
  ```
  
  **4. JavaScript Decorators (experimental):**
- Decorators (experimental feature) can be used to automatically memoize functions.
  
  **Example (using the experimental @memo decorator):**
  
  **JavaScript**
  
  ```
  @memo
  function memoizedFibonacci(n) {
  // ... implementation
  }
  
  ```
  
  **Choosing the Right Technique:**
- The best technique depends on the specific problem and context.
- Caching is simple but might not be suitable for dynamic problems.
- Dynamic programming excels in solving optimization problems with overlapping subproblems.
- HOFs and decorators offer convenience but might have larger library dependencies.