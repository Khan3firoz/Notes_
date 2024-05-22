# API integration #React 
heading:: 1

Created: February 9, 2024 12:57 AM
Updated: February 9, 2024 12:57 AM
- ## **API Integration in React: Fetching Data & Handling Asynchrony**
  heading:: 2
  
  React allows seamless integration with APIs to fetch data and power your application. Here's a breakdown of key concepts and an example:
  
  **Fetching Data:**
- **`fetch` API:** Built-in browser API for making HTTP requests and retrieving data (JSON format preferred).
- **Axios:** Popular library offering a simpler and more user-friendly interface over `fetch`, often used for complex API interactions.
  
  **Example (using `fetch` to fetch a list of users):**
  
  **JavaScript**
  
  ```
  function UsersList() {
  const [users, setUsers] = useState([]);
  const [isLoading, setIsLoading] = useState(true);
  const [error, setError] = useState(null);
  
  useEffect(() => {
  const fetchData = async () => {
    try {
      const response = await fetch('https://api.example.com/users');
      if (!response.ok) {
        throw new Error(`Error fetching users: ${response.statusText}`);
      }
      const data = await response.json();
      setUsers(data);
    } catch (error) {
      setError(error.message);
    } finally {
      setIsLoading(false);
    }
  };
  
  fetchData();
  }, []);
  
  return (
  <div>
    {isLoading && <p>Loading users...</p>}
    {error && <p>Error: {error}</p>}
    {users.length > 0 && (
      <ul>
        {users.map((user) => (
          <li key={user.id}>{user.name}</li>
        ))}
      </ul>
    )}
  </div>
  );
  }
  
  ```
  
  **Explanation:**
- `useEffect` hook triggers data fetching on component mount.
- `fetch` request retrieves data from the API.
- Error handling checks for successful response and potential errors.
- State variables manage loading state (`isLoading`), fetched data (`users`), and any errors (`error`).
- Conditional rendering displays loading message, error message, or fetched user list.
  
  **Asynchronous Operations:**
- API calls involve fetching data asynchronously, meaning they take time to complete.
- React handles this using hooks like `useEffect` and state management to update the UI when data is available.
  
  **Handling Loading States and Errors:**
- Indicate loading states while data is being fetched (e.g., loading spinners).
- Display clear error messages if API calls fail, guiding users.