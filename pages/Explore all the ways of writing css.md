# Explore all the ways of writing css. #React 
heading:: 1

Created: February 8, 2024 12:59 AM
Updated: February 11, 2024 11:18 AM

**Methods for Integrating CSS in React:**

1. **Inline Styles:**
	- Styles are defined directly within JSX tags using the `style` attribute.
	- Pros: Convenient for small styles or one-off uses.
	- Cons: Can lead to verbose code and difficulty in styling multiple components.
	- Example:
	  
	  **JavaScript**
	  
	  ```
	  return <h1 style={{ color: 'red', fontSize: '2em' }}>Inline style</h1>;
	  
	  ```
	  
	  2. **External Stylesheets:**
	- Separate CSS files are created and linked to your React components using the `<link>` tag in the HTML head.
	- Pros: Maintainable, scalable, and promotes code separation.
	- Cons: Requires additional files and linking processes.
	- Example:
	  
	  **JavaScript**
	  
	  ```
	  import './myStyles.css';
	  
	  return <h1 className="heading">External stylesheet</h1>;
	  
	  ```
	  
	  3. **CSS Modules:**
	- CSS files are created with the `.module.css` extension.
	- Local scope: Styles are scoped to the component using them, preventing conflicts.
	- Dynamic class names: React generates unique class names based on the CSS module class names, ensuring they won't collide with global styles.
	- Pros: Encapsulation, avoids global namespace pollution, and supports dynamic styling.
	- Cons: Slightly more complex setup.
	- Example:
	  
	  **JavaScript**
	  
	  ```
	  import styles from './MyComponent.module.css';
	  
	  return <h1 className={styles.heading}>CSS Modules</h1>;
	  
	  ```
	  
	  4. **CSS-in-JS Libraries:**
	- CSS logic is integrated directly within JavaScript using libraries like Styled Components, Emotion, JSS, or Aphrodite.
	- Pros: Component-oriented styling, dynamic styles based on props or state, theming capabilities.
	- Cons: Additional learning curve, potential performance overhead with large stylesheets.
	- Example (using Styled Components):
	  
	  **JavaScript**
	  
	  ```
	  import styled from 'styled-components';
	  
	  const StyledHeading = styled.h1`
	    color: blue;
	    font-size: 2em;
	  `;
	  
	  return <StyledHeading>Styled Components in JSX</StyledHeading>;
	  
	  ```
	  
	  5. **Global Stylesheets:**
	- A single CSS file is created to define global styles that apply to all components.
	- Use with caution: Avoid overriding component-specific styles.
	- Example:
	  
	  **CSS**
	  
	  ```
	  /* global.css */
	  body {
	    font-family: sans-serif;
	  }
	  
	  ```
	  
	  
	  **Choosing the Right Method:**
- For small-scale projects or isolated styles, inline styles or external stylesheets may suffice.
- For larger projects, CSS Modules or CSS-in-JS libraries provide better maintainability and encapsulation.
- Use global styles sparingly and strategically.