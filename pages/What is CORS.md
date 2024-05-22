# What is CORS? #WebDev 
heading:: 1

Created: February 9, 2024 12:28 AM
Updated: February 9, 2024 12:28 AM

Cross-Origin Resource Sharing (CORS) is a mechanism that allows web pages to request restricted resources from a different domain than the one that served the web page. In simpler terms, it helps websites communicate with each other across domain boundaries in a secure way.

Imagine you have two websites:
- **Site A:** Hosting your main application.
- **Site B:** An API providing data or functionality.
  
  If Site A wants to fetch data from Site B's API, CORS comes into play. By default, browsers restrict such cross-origin requests due to security concerns. CORS allows Site B to specify which origins (like Site A) are allowed to access its resources and under what conditions.
  
  Here's how it works:
  
  1. **Request:** Site A sends a request to Site B's API.
  2. **Preflight (optional):** If Site B uses certain HTTP methods or headers, it receives a preflight request first. This allows Site B to check if the actual request is allowed before processing it.
  3. **Response:** Site B sends a response back to Site A, including CORS headers. These headers specify:
	- **Origin:** Which origins are allowed to access the resource (e.g., `` for all, specific domain names).
	- **Methods:** Allowed HTTP methods (e.g., GET, POST).
	- **Headers:** Allowed additional headers in the request.
	- **Credentials:** Whether requests can send cookies or other credentials.
	  4. **Access:** If the request meets the specified conditions, the browser allows Site A to access the resource from Site B.
	  
	  **Benefits of CORS:**
- **Enables communication between different domains:** Allows building richer and more integrated web applications.
- **Improves security:** CORS allows controlled access, preventing unauthorized requests and potential security vulnerabilities.