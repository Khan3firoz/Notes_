# {TitleComponent} vs {<TitleComponent/>} vs {<TitleComponent></TitleComponent>} in JSX #React 
heading:: 1

Created: February 8, 2024 12:12 AM
Updated: February 11, 2024 11:11 AM

The three expressions you provided in JSX represent different ways to reference or use a component called `TitleComponent`:

**1. {TitleComponent}:**
- This refers to the `TitleComponent` itself, without rendering it. It's simply the **name of the component**, similar to referencing a variable.
- You can use this notation when passing the component as a prop to another component or using it in conditional expressions.
  
  **2. {<TitleComponent/>}:**
- This **renders the `TitleComponent` without any children**. The closing tags `</TitleComponent>` are optional in this case.
- This is the standard way to use a component in JSX and display its output on the screen.
  
  **3. {<TitleComponent></TitleComponent>}:**
- This also **renders the `TitleComponent`, but with no children** placed between the opening and closing tags.
- This has the same effect as `{<TitleComponent/>}`, but the explicit closing tags might be useful for readability in certain scenarios.