# How will useEffect behave if we don't add a dependency array ? #React 
heading:: 1

Created: February 9, 2024 12:34 AM
Updated: February 9, 2024 12:35 AM

When you use the `useEffect` hook in React without specifying a dependency array, it leads to a specific behavior:

**Execution:**
- The effect function inside `useEffect` **runs after every single render**, regardless of whether the component's state or props have changed.
- This behavior can be confusing and often leads to unintended side effects or infinite loops.
  
  **Reasoning:**
- React relies on dependencies to optimize re-renders. Without a dependency array, React assumes the effect depends on everything and triggers it after every render.
- This is because React doesn't have a way to know when the effect becomes irrelevant due to changes in the component's state or props.
  
  **Potential Issues:**
- **Performance:** Unnecessary re-renders caused by the effect can significantly impact performance, especially for expensive effect functions or in large components.
- **Memory leaks:** If the effect creates subscriptions or side effects that are not cleaned up properly, it can lead to memory leaks over time.
- **Infinite loops:** If the effect triggers state or prop updates, it can create an infinite loop as the update will cause another render, triggering the effect again.
  
  **Best Practices:**
- **Always specify a dependency array:** Include all state variables, props, and other values used by the effect function within the dependency array.
- **Empty array for cleanup effects:** If the effect only needs to run once for cleanup (e.g., removing event listeners), use an empty `[]` dependency array.
  
  **Example:**
  
  Consider this example:
  
  **JavaScript**
  
  ```
  function MyComponent() {
  const [count, setCount] = useState(0);
  
  useEffect(() => {
  document.title = `Count: ${count}`; // Update document title
  });
  
  // ...
  
  return (
  // ...
  );
  }
  
  ```
  
  Without a dependency array, the `useEffect` hook will update the document title after every render, even if the `count` value hasn't changed. This can cause unnecessary re-renders and performance issues.
  
  Adding a dependency array like `[count]` ensures the effect only re-runs when the `count` value changes:
  
  **JavaScript**
  
  ```
  function MyComponent() {
  const [count, setCount] = useState(0);
  
  useEffect(() => {
  document.title = `Count: ${count}`; // Update document title
  }, [count]);
  
  // ...
  
  return (
  // ...
  );
  }
  
  ```