# What is props in React? #React
heading:: 1

Created: February 8, 2024 12:48 AM
Updated: February 11, 2024 11:18 AM

**React Props: Data Transfer Between Components**

In React, props enable data and functionality transfer from parent to child components, fostering reusable UI components.

**Props Features:**
- **Immutable:** Props can't be directly modified in the receiving component.
- **Hierarchical:** Parents pass props to children, who may pass them to their descendants.
- **Data type flexibility:** Props can contain various data types, including primitives, objects, arrays, and functions.
  
  **Props Usage:**
  
  1. **Parent component definition:**
	- Use the `propName` attribute in the child's JSX tag.
	- Assign a value or expression to `propName`.
	  2. **Child component access:**
	- Destructure props in the component's function for clarity.
	- Use destructured prop names to access the data.
	  
	  **Example:**
	  
	  ```jsx
	  // Parent (App.js)
	  function App() {
	  const title = "My Awesome App";
	  const data = [1, 2, 3];
	  const handleClick = () => console.log("Button clicked!");
	  
	  return (
	  <div>
	  <HeaderComponent title={title} />
	  <List data={data} handleClick={handleClick} />
	  </div>
	  );
	  }
	  
	  // Children (HeaderComponent.js, List.js)
	  function HeaderComponent({ title }) {
	  return <h1>{title}</h1>;
	  }
	  
	  function List({ data, handleClick }) {
	  return (
	  <ul>
	  {data.map((item) => (
	  <li key={item}>{item}</li>
	  ))}
	  <button onClick={handleClick}>Click Me</button>
	  </ul>
	  );
	  }
	  
	  ```
	  
	  **Advanced Prop Use:**
- **Default props:** Use `defaultProps` for fallback values.
- **PropTypes:** Improve type safety and error checking.
- **Spread operator:** Pass multiple props with `{...object}` syntax.
- **Children prop:** Use `children` prop to receive nested content.