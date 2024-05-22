# What is Optional Chaining? #React 
heading:: 1

Created: February 9, 2024 12:24 AM
Updated: February 9, 2024 12:25 AM

Optional chaining, introduced in ECMAScript 2020, is a powerful operator that simplifies accessing nested properties in objects where some levels might be undefined or null. It avoids the need for explicit checks before each access, improving code readability and preventing errors.

Here's how it works:

**Syntax:**

```jsx
object?.property1?.property2?....

```

**Breakdown:**
- `object`: The starting point of the property chain.
- `?.`: The optional chaining operator.
- `property1`, `property2`: Names of nested properties you want to access.
  
  **Behavior:**
- If `object` is undefined or null, the chain stops right there and returns `undefined`.
- Otherwise, it proceeds to access `property1`, and if it's undefined or null, the chain again stops and returns `undefined`.
- This behavior continues for subsequent properties in the chain.
- If all properties exist, the final value is returned.
  
  **Benefits:**
- **Safer**: No more errors from accessing properties of undefined or null objects.
- **Concise**: Avoids nested if statements or ternary operators for checking null/undefined.
- **Readable**: Makes code easier to understand and maintain.
  
  **Example:**
  
  ```jsx
  const user = { address: { city: "New York" } };
  
  // Old way, prone to errors if address is null:
  const city = user.address && user.address.city; // Can throw TypeError if address is null
  
  // Optional chaining, safe and concise:
  const city = user?.address?.city; // Returns undefined if address or city is null
  
  // Using with functions:
  const greet = user?.greet?.(); // Calls only if greet function exists on user
  
  ```