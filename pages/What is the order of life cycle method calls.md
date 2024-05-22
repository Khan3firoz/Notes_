# What is the order of life cycle method calls in Class Based Components #React 
heading:: 1

Created: February 9, 2024 12:41 AM
Updated: February 9, 2024 12:42 AM

Here's a shorter and clearer breakdown of lifecycle method calls in React class-based components:

**Mounting:**
- **constructor (optional):** Initializes state and binds methods (avoid in modern React).
- **static getDerivedStateFromProps (optional):** Updates state based on new props before rendering.
- **render():** Generates the JSX displayed on the screen.
- **componentDidMount():** Called after component is inserted into the DOM (fetch data, set up subscriptions).
  
  **Updating:**
- **static getDerivedStateFromProps (optional):** Updates state based on new props/state changes.
- **shouldComponentUpdate (optional):** Controls if component needs to re-render based on new props/state.
- **getSnapshotBeforeUpdate (optional):** Captures DOM info before update (like scroll position).
- **render():** Generates updated JSX based on new props/state.
- **componentDidUpdate():** Called after component updates in the DOM (perform actions based on changes).
  
  **Unmounting:**
- **componentWillUnmount():** Cleans up resources before component is removed from the DOM.
  
  **Remember:**
- Functional components with hooks like `useState` and `useEffect` are preferred in modern React development.
- Use lifecycle methods cautiously and avoid deprecated ones like `componentWillReceiveProps` and `componentWillUpdate`.