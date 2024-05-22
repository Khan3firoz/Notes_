# Component Composition #React 
heading:: 1

Created: February 8, 2024 12:34 AM
Updated: February 11, 2024 11:12 AM

Component composition is a fundamental concept in React that allows you to build complex user interfaces by combining smaller, reusable components. It's like assembling Lego bricks to create intricate structures. By thinking in terms of smaller, focused components, you gain several benefits:

**1. Reusability:** You can write a component once and use it in multiple places in your application, reducing code duplication and maintenance overhead.
**2. Modularity:** Each component has a clear responsibility, making your code easier to understand and test.
**3. Maintainability:** As your application grows, you can easily modify or replace individual components without affecting the rest of the codebase.
**4. Performance:** Breaking down the UI into smaller pieces can improve rendering performance.

Here are some key ways to achieve component composition in React:

**1. Nesting Components:**

The most basic form of composition is nesting components. Child components receive props from their parent components, allowing them to customize their behavior based on the context.

**JavaScript**

```
function App() {
return (
<div>
<HeaderComponent title="My Cool App" />
<MainContent>
  <Article title="First Article" content="This is some content" />
  <Article title="Second Article" content="More content here" />
</MainContent>
<Footer />
</div>
);
}

function HeaderComponent(props) {
return <h1>{props.title}</h1>;
}

// ... and so on for other components

```

**2. Passing Props:**

Props are the mechanism for passing data between components. Parent components pass down data and functionality as props to their child components.

**JavaScript**

```
function Greeting(props) {
return <p>Hello, {props.name}!</p>;
}

function App() {
return <Greeting name="World" />;
}

```

**3. Higher-Order Components (HOCs):**

HOCs are functions that take a component and return a new component with enhanced functionality. They're useful for adding common behaviors like authentication, caching, or data fetching to existing components without modifying their code.

**JavaScript**

```
const withAuth = (Component) => {
// Add authentication logic here
return (props) => {
// Check if user is authenticated
if (isAuthenticated()) {
return <Component {...props} />;
} else {
return <Redirect to="/login" />;
}
};
};

const MyProtectedComponent = withAuth(MyRegularComponent);

```

**4. Render Props:**

Render props involve passing a function as a prop to a child component, giving the child control over what gets rendered. This can be useful for creating components that can render different content based on the context.

**JavaScript**

```
function MyContainer(props) {
return (
<div>
{props.render({ data: "some data" })}
</div>
);
}

function MyChild(props) {
return <h2>{props.data}</h2>;
}

<MyContainer render={(data) => <MyChild {...data} />} />

```

By mastering these techniques, you can unlock the power of component composition in React and build applications that are elegant, maintainable, and scalable. Remember, the key is to break down complex problems into smaller, manageable pieces and focus on composing them in a meaningful way.