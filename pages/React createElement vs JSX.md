# React.createElement vs JSX #React 
heading:: 1

Created: February 7, 2024 11:14 AM
Updated: February 11, 2024 11:11 AM

Both **React.createElement** and **JSX** are ways to create elements in React, but they differ in their syntax and approach:
- **React.createElement:**
	- Function: This is the core building block for creating elements in React.
	- It takes three arguments:
	- Element type: The type of element you want to create, like 'div', 'p', or a custom component, e.g.
- ![638429013187956865.png](../assets/638429013187956865_1715415641515_0.png)
- **JSX:**
	- Syntax extension: A syntax extension for JavaScript that allows writing HTML-like markup within your code.
	- Conciseness: More concise and readable than **React.createElement**.
	- Compiles to: Under the hood, JSX gets transformed into calls to **React.createElement** during the build process.
	- ![638429013455219094.png](../assets/638429013455219094_1715415676969_0.png)**
	-
- Key Differences:**
	- Readability: JSX is generally considered more readable due to its HTML-like syntax.
	- Verbosity: **React.createElement** requires more code, while JSX is more concise.
	- Flexibility: Both methods offer equal flexibility in creating elements.
	- Preference: Using JSX or **React.createElement** is a matter of personal preference and team conventions.