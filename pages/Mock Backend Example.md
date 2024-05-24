- #Angular
- A mock backend is a simulated server environment created within a frontend application to mimic the behavior of a real backend server. It intercepts HTTP requests made by the frontend application and provides predefined responses, allowing frontend developers to work independently of the actual backend implementation. Mock backends are commonly used during development and testing phases when the real backend is unavailable or incomplete.
- ```javascript
  import { Injectable } from '@angular/core';
  import { HttpClient, HttpHeaders } from '@angular/common/http';
  import { Observable, of } from 'rxjs';
  
  @Injectable({
    providedIn: 'root'
  })
  export class MockBackendService {
    constructor(private http: HttpClient) { }
  
    registerUser(user): Observable<any> {
      // Simulate registering user by returning a mock response
      return of({ success: true, message: 'User registered successfully' });
    }
  
    authenticateUser(credentials): Observable<any> {
      // Simulate authenticating user by returning a mock response
      return of({ success: true, token: 'fake-jwt-token' });
    }
  
    getUserById(id): Observable<any> {
      // Simulate retrieving user data by returning a mock response
      const user = { id: 1, username: 'john_doe', email: 'john@example.com' };
      return of(user);
    }
  
    updateUser(id, userData): Observable<any> {
      // Simulate updating user data by returning a mock response
      return of({ success: true, message: 'User updated successfully' });
    }
  
    deleteUser(id): Observable<any> {
      // Simulate deleting user by returning a mock response
      return of({ success: true, message: 'User deleted successfully' });
    }
  }
  
  ```