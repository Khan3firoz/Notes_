# What is the difference between JS expression and JS statement #Javascript 
heading:: 1

Created: February 9, 2024 12:26 AM
Updated: February 9, 2024 12: 26 AM

The key difference between a JS expression and a JS statement lies in their purpose and outcome:

**1. Purpose:**
- **Expressions:** Calculate or evaluate to a value. Their primary role is to provide data used elsewhere in your code.
- **Statements:** Perform actions or define instructions for the JavaScript engine to execute. They don't directly produce values but rather cause something to happen.
  
  **2. Outcome:**
- **Expressions:** Always result in a value, even if it's `undefined`. This value can be used in assignments, function calls, comparisons, etc.
- **Statements:** Don't directly return a value. Their impact lies in the actions they perform, like declaring variables, printing messages, looping through data, etc.
  
  **Examples:**
- **Expressions:**
	- `1 + 2` (evaluates to 3)
	- `'Hello' + ' World'` (evaluates to "Hello World")
	- `x * y` (evaluates to the product of x and y)
	- `true || false` (evaluates to true)
- **Statements:**
	- `let age = 25;` (declares a variable and assigns a value)
	- `console.log('This is a message');` (prints a message to the console)
	- `for (let i = 0; i < 5; i++) { ... }` (loop that executes code 5 times)