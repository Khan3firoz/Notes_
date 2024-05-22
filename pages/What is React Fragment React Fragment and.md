# What is <React.Fragment></React.Fragment> and <></> ? #React 
heading:: 1

Created: February 8, 2024 12:39 AM
Updated: February 11, 2024 11:12 AM

Both `<React.Fragment></React.Fragment>` and `<>` are ways to group multiple JSX elements without adding an extra DOM node to the rendered HTML. While they achieve the same purpose, they have some differences:

**1. <React.Fragment></React.Fragment>:**
- This is the more explicit way of representing a fragment. It's written in JSX syntax just like any other component.
- While not strictly necessary in most cases, it can be useful for:
	- **Clarity:** It explicitly conveys the intent of grouping elements without adding a DOM node.
	- **Compatibility:** It works in older React versions that might not support the shorthand syntax.
	  
	  **2. <> and </>:**
- This is a shorthand syntax introduced in React 16.2. It's more concise and less verbose than the full tag format.
- It's the preferred way to create fragments in modern React development.
- However, it has some limitations:
	- It cannot have attributes or keys attached to it.
	- It might be less clear to developers unfamiliar with modern React syntax.
	  
	  **Examples:**
	  
	  ```
	  // Using React.Fragment
	  return (
	  <React.Fragment>
	  <h1>Title</h1>
	  <p>Content</p>
	  </React.Fragment>
	  );
	  
	  // Using shorthand syntax
	  return (
	  <>
	  <h1>Title</h1>
	  <p>Content</p>
	  </>
	  );
	  
	  ```