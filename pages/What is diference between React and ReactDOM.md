# What is difference between React and React DOM #React 
heading:: 1

Created: February 7, 2024 12:25 AM
Updated: February 11, 2024 11:10 AM

**React** is, at its core, a library for building **user interfaces**.

It introduces the concept of components, which allow developers to craft reusable and self-contained UI elements.

These components define how a user interface should appear based on given inputs (props and state).

**React** operates with a virtual representation of the DOM, known as the **Virtual DOM**, which is an abstraction of the actual browser’s DOM.

**ReactDOM**, on the other hand, acts as the glue between React’s **Virtual DOM** and the actual browser’s DOM.

It provides the means to render **React components** into the DOM.

The primary method it offers is `ReactDOM.render()`, which is used to take a **React component** and render it into a specified DOM node.

Additionally, **ReactDOM** provides utilities for directly interacting with the DOM, like `findDOMNode()` (though its use is often discouraged in favor of more “React-ish” approaches).

Importantly, **ReactDOM** is specific to web browsers.

The reason for this separation is **React’s design philosophy** to be platform-agnostic.

While **ReactDOM** deals with web-specific rendering, there are other renderers like **React Native** (for mobile apps) or **ReactVR** (for virtual reality) that leverage the core **React library** to target different platforms.