# React Topics

This technical paper briefly discusses core React and related concepts. The concepts and their explanations are given in the QA format.

### What is React?
React is a frontend JS library for building single-page applications divided into declarative components. React uses a concept called the virtual DOM for precise and cheaper re-renders.  

### What are JSX, components, and props?
**JSX:** JSX stands for JavaScript XML. It is a way to write HTML markup inside JavaScript. React uses Bable/Esbuild to translate JSX into native JS code so that the runtime environments (Browsers/Node) can run JSX.   

**Components:** Components are JS functions that return JSX to render a UI component. React uses state to manage the rendering of components.  

**Props:** Props are properties that are received by components as parameters and passed as HTML properties. They make a component reusable and configurable. Props are immutable when React Strict Mode is on. However, we shouldn't change the props values anyways.  

### What is Babel, and what role does it play in React?
Babel is a build tool used by React to translate JSX and ES6 code into native JS code so that the browser can run it. However, Babel is no longer in use after CRA's deprecation. React (with Vite) uses Esbuild in place of Babel.  

### What is the difference between Virtual DOM & Real DOM?
The DOM is the final render tree, while the virtual DOM is an in-memory copy of the DOM. When a component's state changes, React detects the change, creates a copy of the virtual DOM, and compares the differences between the virtual DOM and the snapshot through a process called reconciliation. Once the differences are established, React updates the DOM and saves the snapshot as the original virtual DOM.  

### What is a bundler?
A bundler is a build tool that combines different files of different formats into fewer, larger files so that the browser can download them efficiently with fewer calls.  

### Why are we not using Create React App but Vite for React projects?
We use Vite instead of CRA because of its speed and optimization. For example, CRA builds the whole application on every run, whereas Vite optimizes it and runs the server in a split second. CRA's Webpack crawls every single file before running the server. Vite uses the browser's ability to intercept import statements and compiles only the required files.  

### Diff. between Class & Functional components
Class components are an old and not recommended way of writing component code. Although they achieve the same functionality as functional components, they add complexity. Class and functional components differ in their implementation in various aspects such as syntax, props, lifecycle, etc.  

### What are hooks in React?
Hooks are functions provided by React and other libraries to components to enable them to use React features. Various hooks serve different purposes, such as state management, side effects, memoization, etc.  

### How to pass data from one component to another component?
There are two ways we can pass data down to componenets; Prop drilling and using context API. Prop drilling is passing data down through each level to the targeted component. Context API creates a context at the parent level, and all its children can use the passed value (data) directly by using the useContext hook. Both of them are usefull depending on the usecase.  

### What is lifting state up?
Lifting state up means managing state in the parent component when its children rely on the same state rather than creating separate states in the children components.  

### How to use event listeners in the component?
React wraps browser events in synthetic events with a consistent API across browsers. You attach handlers with camelCase props like onClick, onChange, onSubmit, onKeyDown, onMouseEnter, and onFocus.







