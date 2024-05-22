# Controlled vs Uncontrolled components. #React 
heading:: 1

Created: February 9, 2024 12:53 AM
Updated: February 9, 2024 12:54 AM

In React, components can be classified as either **controlled** or **uncontrolled**, representing how they manage their state and interact with user input. Understanding these distinctions is crucial for building efficient and maintainable React applications.

**Controlled Components:**
- **State management:** Controlled components rely on React state to manage their values.
- **User input:** Input changes trigger events like `onChange` which update the component's state, reflecting the new value.
- **Value prop:** Controlled components receive the current value as a prop from a parent component.
- **Benefits:**
	- Easier to reason about data flow and maintain consistent state.
	- Enables validation and form validation logic on the parent component.
	- Suitable for dynamic forms and complex interactions.
- **Example:** Imagine a text input where the value is stored in the component's state and updated based on user typing.
  
  **Uncontrolled Components:**
- **State management:** Uncontrolled components manage their own internal state, often using DOM elements directly.
- **User input:** Input changes directly modify the DOM element's value, and retrieval happens using refs.
- **Value prop:** Uncontrolled components typically don't receive a `value` prop.
- **Benefits:**
	- Simpler for basic input fields without complex state management needs.
	- More performant in some scenarios due to avoiding unnecessary re-renders.
- **Example:** A static text field displaying information that doesn't change based on user interaction.
  
  **Things to consider:**
- **Suitability:** Choose controlled components for forms, dynamic data, and complex interactions. Use uncontrolled components for simpler inputs with static values.
- **Maintainability:** Controlled components promote centralized state management, potentially aiding maintainability in large applications.
- **Complexity:** Uncontrolled components can be easier for basic cases but might require more intricate logic for complex scenarios.