# What is lifting the state up? #React 
heading:: 1

Created: February 9, 2024 12:44 AM
Updated: February 9, 2024 12:44 AM

Lifting the state up in React is a technique for sharing data between multiple components that need it. Instead of each component having its own local state, the shared data is moved to the closest common ancestor of those components. This common ancestor then becomes the "single source of truth" for the data, and it passes the data down to the components that need it as props.

**Benefits of lifting the state up:**
- **Reduces redundancy:** Avoids duplicating state in multiple components, preventing inconsistencies and simplifying code.
- **Improves maintainability:** Makes it easier to update and manage shared data in one place.
- **Simplifies reasoning:** Ensures components don't have to worry about how other components might modify their local state.
  
  **When to lift the state up:**
- When two or more components need the same data to render or update.
- When a change in the data would affect multiple components.
- When managing complex state becomes difficult within individual components.
  
  **How to lift the state up:**
  
  1. **Identify the shared data:** Determine the data that multiple components need access to.
  2. **Find the closest common ancestor:** Locate the component that is the parent of all components that need the data.
  3. **Move the state up:** Transfer the shared data to the state of the common ancestor.
  4. **Pass the data down:** Use props to provide the shared data to the components that need it.
  
  **Example:**
  
  Imagine you have an application with a counter component that displays a number and two button components, one to increment and one to decrement the number. Traditionally, you might manage the count state in each button component. However, lifting the state up would move the count to the parent component that contains both buttons, making it the "single source of truth" and avoiding potential inconsistencies.