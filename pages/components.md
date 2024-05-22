# components #React 
heading:: 1

Created: February 7, 2024 11:17 AM
Updated: February 11, 2024 11:11 AM

A **component** is a self-contained block of code that renders UI and handles user interactions. Think of them as building blocks for UI. Components can nest inside each other, creating hierarchical UIs. Child components receive props from parent components, facilitating data flow.

**Types:**
- **Functional Components:** Defined as JavaScript functions that return JSX (JavaScript XML) describing the UI. Simple and widely used for presentational logic.
  
  {:height 33, :width 656}
- ![638429015387829908.png](../assets/638429015387829908_1715415481409_0.png)
- **Class Components:** Defined as JavaScript classes that extend React.Component. More complex but offer features like lifecycle methods and state management.
	- ![638429015836244917.png](../assets/638429015836244917_1715415540242_0.png)
	- **State Components:** Use internal state (managed with hooks) for dynamic behavior.
	- **Higher-Order Components (HOCs):** Add functionality to existing components without modifying their code.
	  
	  **Advantages of Using Components:**
- **Reusability:** Reduce code duplication and maintain consistency.
- **Maintainability:** Complex UIs become easier to understand and manage.
- **Testability:** Isolate components for focused testing.
- **Declarative Nature:** Focus on what and not how UI renders.