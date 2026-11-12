# React Questions and Answers

### 1. Can you explain the advantages of using JSX?

JSX is a syntax extension which lets developers write declarative React
components by combining markup and JavaScript logic. It has several
advantages such as readability, easy component composition, and a
familiar way to describe the UI. It also allows developers to embed
JavaScript expressions directly into the markup.

### 2. What is the difference between Virtual DOM and Real DOM?

Real DOM is a tree-like representation of the document present in the
browser, where each node represents an actual document element. Whereas
the Virtual DOM is a lightweight JavaScript representation of the UI.
React uses it to determine what needs to change in the actual DOM when
the application state or props change.

### 3. What is a bundler? Explain Webpack.

A bundler is a build tool which combines application modules and their
dependencies into optimized files that can be served to the browser. It
starts from one or more entry points and follows the dependency graph to
determine which files are required.

Webpack is a popular JavaScript bundler. It can process JavaScript, CSS,
images, and other assets using loaders and plugins. Create React App
used Webpack internally, but Create React App is now deprecated for new
projects.

### 4. What is Vite?

Vite is a frontend build tool which provides a fast development server
and an optimized production build. During development, it serves source
files using native ES modules, which avoids bundling the entire
application before the server starts. For production, it bundles and
optimizes the application.

### 5. What is Babel?

Babel is a JavaScript compiler which transforms modern JavaScript and
JSX into JavaScript that can run in the target environment. React
developers commonly use it to transform JSX into JavaScript function
calls. Babel does not bundle application files; that is the
responsibility of a bundler or build tool.

### 6. What is a React element?

A React element is a plain JavaScript object that describes what should
appear on the screen. It contains information such as the element type,
props, and children. React uses these element descriptions to update the
UI. A React element is not the same as an actual DOM element.

### 7. What causes a component to re-render?

A React component can re-render when its state changes, when its parent
re-renders and passes new props, or when a context value it uses
changes. A re-render means React calls the component again to calculate
the next UI. It does not necessarily mean that React updates the actual
DOM.

### 8. What is the difference between functional and class components?

Functional components are JavaScript functions that return React
elements. They use Hooks to manage state and other React features. Class
components are ES6 classes that extend `React.Component` and use methods
such as `render()` and lifecycle methods. Functional components are the
recommended approach for new React code.

### 9. Why should React component names start with a capital letter?

JSX treats names starting with lowercase letters as built-in HTML
elements, such as `div` or `button`. Names starting with an uppercase
letter are treated as JavaScript component references. Therefore, custom
React components should start with a capital letter.

### 10. What is ReactDOM?

ReactDOM is a package that provides the methods required to render React
components into the browser DOM. In modern React applications,
`createRoot()` from `react-dom/client` is commonly used to create a root
and render the application inside a DOM element.

### 11. What is state in React?

State is data managed by a component which can change over time and
affect what is displayed on the screen. When state is updated using the
appropriate React state setter, React schedules a re-render so the UI
can reflect the new value.

### 12. What are props in React?

Props are inputs passed from a parent component to a child component.
They allow components to be reusable and configurable. Props are
read-only from the receiving component's perspective; a child should not
directly modify the props it receives.

### 13. What is the difference between state and props?

Props are passed to a component by its parent, whereas state is managed
within the component using React state features. Props are read-only
inputs, while state can be updated by the component. Changes to either
can cause a component to re-render.

### 14. What is the difference between JSX and HTML?

JSX looks similar to HTML, but it is JavaScript syntax and follows
JavaScript naming conventions. For example, JSX uses `className` instead
of `class`, `htmlFor` instead of `for`, and camelCase for most event
handlers, such as `onClick`. JSX expressions are written inside curly
braces.

### 15. What are PropTypes?

PropTypes is a library used to specify the expected types of props
passed to a component. It can warn developers in the browser console
when a component receives props of an unexpected type. PropTypes are
optional and are not a replacement for TypeScript or runtime data
validation.

### 16. What is setState in React?

`setState` is a method used in class components to update state. It
schedules an update rather than changing the state immediately. React
may batch multiple state updates for performance. When the next state
depends on the previous state, the functional form of `setState` should
be used.

### 17. How does the useState Hook work?

`useState` is a Hook used to add state to functional components. It
returns an array containing the current state value and a setter
function. Calling the setter schedules a re-render with the updated
state. State updates may be batched, so the state variable does not
change immediately in the currently running code.

### 18. Why should state not be mutated directly?

React state should be treated as immutable. Directly changing an object
or array in state does not tell React that an update has happened and
can lead to unexpected behavior. Instead, create a new object or array
with the required changes and pass it to the state setter.

### 19. How do you handle form validation in React?

Form validation can be handled by checking input values when the user
types or submits the form. In a controlled form, input values are stored
in React state and updated through event handlers. Validation logic can
check conditions such as required fields, valid email formats, and
minimum lengths, then display appropriate error messages.

### 20. What is the difference between controlled and uncontrolled components?

In a controlled input, React state is the source of truth for the input
value. The value is passed through the `value` prop and updated using an
event handler. In an uncontrolled input, the DOM manages the value,
which can be accessed using a ref. Controlled inputs are useful when the
UI needs to respond to or validate input changes.

### 21. Why are keys used in React lists?

Keys help React identify which items have changed, been added, or been
removed when rendering a list. They should be unique among the siblings
in that list and should remain stable between renders. A database ID is
generally a good key. Array indexes should be avoided when the list can
be reordered, inserted into, or deleted from.

### 22. What are lifecycle methods in React?

Lifecycle methods are special methods available in class components that
run at different stages of a component's existence. The main stages are
mounting, updating, and unmounting. Examples include
`componentDidMount`, `componentDidUpdate`, and `componentWillUnmount`.
In functional components, similar side-effect behavior is commonly
handled using `useEffect`.

### 23. What is the Context API?

The Context API allows data to be shared across a component tree without
passing props manually through every intermediate component. A context
is created using `createContext`, a provider makes its value available
to descendants, and components can read that value using `useContext`.
It is useful for values such as themes, locale, or authenticated user
information.

### 24. What is React Fragment?

A Fragment lets developers group multiple React elements without adding
an extra DOM element. It is useful when a component needs to return
multiple sibling elements. Fragments can be written using `<></>` or
`<React.Fragment>`. The explicit form supports a `key` when rendering a
list of fragments.

### 25. How can you render a list of elements in React?

Lists are commonly rendered using JavaScript array methods such as
`map()`. The `map()` method returns a new array of React elements, and
each element should have a stable, unique key among its siblings.

``` jsx
const names = ["John", "Ron", "Wanda"];

function NameList() {
  return (
    <ul>
      {names.map((name) => (
        <li key={name}>{name}</li>
      ))}
    </ul>
  );
}
```

### 26. What are React Hooks?

Hooks are functions that let functional components use React features
such as state, context, refs, and effects. Common Hooks include
`useState`, `useEffect`, `useContext`, `useRef`, and `useMemo`. Hooks
allow developers to reuse stateful logic through custom Hooks.

### 27. What is the useEffect Hook?

`useEffect` is a Hook used to synchronize a component with external
systems, such as APIs, subscriptions, timers, or browser APIs. It runs
after React commits the render. Its dependency array controls when the
effect is re-run, and it can return a cleanup function to undo or
release the work performed by the effect.

### 28. What is the useRef Hook?

`useRef` is a Hook that returns a mutable ref object whose `current`
property can be changed without causing a re-render. It is commonly used
to access DOM elements or store values that need to persist between
renders but do not affect the UI.

### 29. What is the useMemo Hook?

`useMemo` is a Hook that caches the result of a calculation between
renders. React recalculates the value when one of its dependencies
changes. It is mainly used to avoid expensive calculations when
necessary; it should not be added to every calculation by default.

### 30. What is the useCallback Hook?

`useCallback` is a Hook that caches a function definition between
renders until one of its dependencies changes. It can be useful when
passing callbacks to memoized child components or when a function is a
dependency of another Hook. It is a performance optimization, not a
requirement for every function.

### 31. What is the useReducer Hook?

`useReducer` is a Hook used to manage state through a reducer function.
The reducer receives the current state and an action, then returns the
next state. It is useful when state logic is complex or when several
related state updates need to be handled in a predictable way.

### 32. What is the difference between a DOM element and a React element?

A DOM element is an actual object representing a node in the browser's
document tree. A React element is a lightweight JavaScript object that
describes what React should render. React uses these descriptions to
create or update the corresponding DOM elements.

### 33. How do you handle errors in React?

Errors in React can be handled using JavaScript techniques such as
`try...catch` for errors in regular functions and `try...catch` around
asynchronous operations. For errors that occur while rendering a
component tree, React provides Error Boundaries. Error Boundaries catch
rendering errors in their descendant components and display fallback UI.

### 34. What are Error Boundaries?

Error Boundaries are React components that catch JavaScript errors in
their child component tree during rendering and certain lifecycle
methods. They prevent the entire application from crashing and allow
fallback UI to be displayed. Traditionally, Error Boundaries are
implemented using class components with `getDerivedStateFromError` and
optionally `componentDidCatch`. They do not catch errors in event
handlers or ordinary asynchronous callbacks.

### 35. What are the Rules of Hooks?

There are two main Rules of Hooks: 1. Only call Hooks at the top level
of a React function component or a custom Hook. Do not call them inside
loops, conditions, or nested functions. 2. Only call Hooks from React
function components or custom Hooks, not from regular JavaScript
functions.

These rules ensure that React calls Hooks in the same order on every
render.

### 36. What is React StrictMode?

`StrictMode` is a development-only tool that helps identify potential
problems in a React application. It can re-run certain functions and
effects in development to expose bugs such as impure rendering and
missing effect cleanup. It does not affect the production build or
render any additional UI.

### 37. What is the purpose of a production build?

A production build prepares the application for deployment. It optimizes
and bundles the code, removes development-only checks where appropriate,
and can minify assets to reduce file size and improve loading
performance. The output is intended to be served to users.

### 38. What is the difference between development and production builds?

A development build is designed to make application development easier.
It usually includes helpful warnings, debugging information, and faster
feedback during development. A production build is optimized for end
users, with features such as minification and reduced development
overhead to improve performance and loading time.

### 39. What is the difference between development and production environments?

A development environment is used by developers to build, test, and
debug an application. It commonly enables detailed logs, source maps,
and development tools. A production environment is where the application
is made available to users and is configured for stability, security,
and performance. A production build is the optimized output; the
production environment is where that output runs.
