# What is the difference between Named Export, Default export and * as export? #NodeJs 
heading:: 1

Created: February 8, 2024 12:50 AM
Updated: February 8, 2024 12:51 AM

**Named Exports:**
- Export multiple distinct components or functions using `export`.
- Import these named exports with their corresponding names.
  
  **Example:**
  
  ```jsx
  // myComponent.js
  export function MyComponent() {...}
  export function AnotherComponent() {...}
  
  // anotherFile.js
  import { MyComponent, AnotherComponent } from './myComponent';
  
  ```
  
  **Default Export:**
- `export default` exports a single component or function.
- When importing, no curly braces or specific name needed.
  
  **Example:**
  
  ```jsx
  // myComponent.js
  export default function MyDefaultComponent() {...}
  
  // anotherFile.js
  import DefaultComponent from './myComponent';
  
  ```
  
  **`as export`:**
- This syntax imports all exports in a single namespace. Not recommended, can cause confusion in larger projects.
  
  **Example:**
  
  ```jsx
  // myComponent.js
  export function MyComponent() {...}
  
  // anotherFile.js
  import * as allExports from './myComponent';
  
  ```
  
  **Key Considerations:**
- Named exports offer clarity and control.
- Default exports can cause conflicts if overused.
- Avoid `as export` unless necessary.
  
  **Best Practices:**
- Use named exports most of the time.
- Use default exports sparingly.
- Avoid `as export` in modern React development.