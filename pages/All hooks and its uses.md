# All hooks and its uses #React 
heading:: 1

Created: February 9, 2024 12:23 AM
Updated: February 9, 2024 12:24 AM

Here's a list of built-in React Hooks and their uses with examples:

**State Management:**
- **useState:** Manages state within a component.
	- **Example:** Managing a counter:
	  
	  **JavaScript**
	  
	  ```
	  function Counter() {
	  const [count, setCount] = useState(0);
	  
	  const handleClick = () => setCount(count + 1);
	  
	  return (
	  <div>
	  <p>You clicked {count} times</p>
	  <button onClick={handleClick}>Click me</button>
	  </div>
	  );
	  }
	  
	  ```
- **useReducer:** Manages complex state with multiple values or sub-states.
	- **Example:** Managing a shopping cart with items and total price:
	  
	  **JavaScript**
	  
	  ```
	  function Cart() {
	  const initialState = { items: [], total: 0 };
	  
	  const reducer = (state, action) => {
	  switch (action.type) {
	  case 'ADD_ITEM':
	  return {
	    ...state,
	    items: [...state.items, action.payload],
	    total: state.total + action.payload.price,
	  };
	  // ...other actions
	  }
	  };
	  
	  const [state, dispatch] = useReducer(reducer, initialState);
	  
	  // ...component logic
	  
	  }
	  
	  ```
	  
	  **Side Effects:**
- **useEffect:** Performs side effects like fetching data, subscriptions, and DOM manipulation.
	- **Example:** Fetching data on component mount:
	  
	  **JavaScript**
	  
	  ```
	  function UserList() {
	  const [users, setUsers] = useState([]);
	  
	  useEffect(() => {
	  fetch('https://api.example.com/users')
	  .then(res => res.json())
	  .then(data => setUsers(data));
	  }, []);
	  
	  // ...component logic
	  
	  }
	  
	  ```
- **useLayoutEffect:** Similar to useEffect, but runs after DOM updates for synchronizing layout-related side effects.
  
  **Other Hooks:**
- **useContext:** Accesses context values from anywhere in the component tree.
	- **Example:** Accessing theme context to set font size:
	  
	  **JavaScript**
	  
	  ```
	  function MyComponent() {
	  const theme = useContext(ThemeContext);
	  
	  return (
	  <h1 style={{ fontSize: theme.fontSize }}>Hello World</h1>
	  );
	  }
	  
	  ```
- **useRef:** Creates a mutable ref object to hold values that persist between renders.
	- **Example:** Storing a DOM element reference for focusing:
	  
	  **JavaScript**
	  
	  ```
	  function TextInput() {
	  const inputRef = useRef(null);
	  
	  const focusInput = () => {
	  inputRef.current.focus();
	  };
	  
	  return (
	  <div>
	  <input ref={inputRef} />
	  <button onClick={focusInput}>Focus Input</button>
	  </div>
	  );
	  }
	  
	  ```
- **useCallback:** Memoizes a callback function to avoid unnecessary re-renders.
	- **Example:** Preventing re-rendering expensive functions used in event handlers:
	  
	  **JavaScript**
	  
	  ```
	  function MyComponent() {
	  const expensiveFunction = useCallback(() => {
	  // ...expensive calculation
	  }, []);
	  
	  const handleClick = () => expensiveFunction();
	  
	  // ...component logic
	  
	  }
	  
	  ```
- **useMemo:** Memoizes a computed value to avoid unnecessary re-calculations.
	- **Example:** Memoizing derived data from props:
	  
	  **JavaScript**
	  
	  ```
	  function MyComponent({ data }) {
	  const formattedData = useMemo(() => {
	  // ...format data
	  }, [data]);
	  
	  // ...component logic
	  
	  }
	  
	  ```
- **useImperativeHandle:** Customizes the instance value exposed to parent components using ref.
- **useTransition:** Manages state transitions with animations.