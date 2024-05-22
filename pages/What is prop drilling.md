# What is prop drilling? #React 
heading:: 1

Created: February 9, 2024 12:43 AM
Updated: February 9, 2024 12:44 AM

Prop drilling in React is like playing telephone with data: you whisper it down the line, component by component, until it reaches its destination. This can get messy!

**Imagine:** You need to send "weather data" to a button component 3 levels down. You pass it from parent to child, to child's child, and so on.

**Problems:**
- **Repetitive:** Writing `prop={data}` everywhere gets tedious.
- **Hard to maintain:** Changing data flow means updating every component in the chain.
- **Component coupling:** They become reliant on receiving specific data and how it's passed.
  
  **Better ways:**
  
  1. **State Management:** Libraries like Redux store data globally, accessible by any component.
  2. **Context API:** Share data across components without drilling, like a magical bulletin board.
  3. **Higher-Order Components (HOCs):** Wrap components with pre-configured data and logic.
  4. **Component Composition:** Break down complex components into smaller, self-contained pieces.
  
  **Remember:** Avoid prop drilling for a cleaner, more maintainable app!