# React Interview Questions🎯

- ReactJS has emerged as one of the biggest libraries used by developers and businesses in the past few years.
- It's the second most-used framework in 2022 & is a high-paying skill.
<br> <br> 


Here I'm listing all the concepts you must know to Ace your React Interviews.
<br>

- [What is React?](#what-is-react)
- [What is JSX?](#what-is-jsx)
- [What are Keys?](#what-are-keys)
- [Virtual DOM Vs. Real DOM?](#differentiate-between-virtual-dom-and-real-dom)
- [Features of React](#what-are-the-features-of-react)
- [What are Components?](#what-are-components)
- [Functional Vs. Class Components](#differentiate-between-functional-and-class-components)
- [What is State?](#what-is-state)
- [What are Props?](#what-are-props)
- [Prop drilling?](#what-is-prop-drilling)
- [Lifecycle Methods](#what-are-lifecycle-methods)
- [React Router](#what-is-react-router)
- [Higher Order Components](#what-are-higher-order-components)
- [React Hooks](#what-are-react-hooks)
- [How to prevent re-renders?](#how-to-prevent-re-renders)
- [Different ways to style a React component?](#what-are-the-different-ways-to-style-a-react-component)
- [Techniques to optimize React app performance?](#what-are-the-techniques-to-optimize-react-app-performance)
- [How to pass data between React components?](#how-to-pass-data-between-react-components)
- [Conditional rendering](#what-is-conditional-rendering)
- [Redux](#what-is-redux)
- [Controlled Vs. Uncontrolled components](#what-are-controlled-and-uncontrolled-components)
- [Pure Components](#what-are-pure-components)
- [Strict Mode](#what-is-strict-mode)

<br>

### What is JSX?

- JSX stands for JavaScript XML
- It allows us to write HTML inside JavaScript and place them in the DOM without using functions like appendChild( ) or createElement( )
- JSX provides syntactic sugar for React.createElement( ) function

### What are Keys?

- special string attribute that needs to be included when using lists of elements
- help react identify which elements were added, changed or removed
- uniqueness of each element

### Differentiate between Virtual DOM and Real DOM?

| Virtual DOM | Real DOM |
| ------------- | ------------- |
| It updates slowly | It updates faster  |
| Can directly update HTML  | Can't directly update HTML  |
| Creates a new DOM if element updates | Updates the JSX if element updates   |
| DOM manipulation is very expensive |  DOM manipulation is very easy |
| Too much memory wastage |  No memory wastage |

### What is React?

- React is an open-source front-end JavaScript library, used for building reusable user interfaces components of mobile and web applications

### What are the features of React?

- uses VirtualDOM instead of RealDOM
- supports server-side rendering
- follows Unidirectional data flow or data binding
- uses reusable/composable UI components to develop the view

### What are Components?
- Component can be declared in several different ways. It can be a class with a render() method or it can be defined as a function. In either case, it takes props as an input, and returns a tree as the output.
1. **Functional** **Components:** This is the simplest way to create a component. Those are pure JavaScript functions that accept props object as the first parameter and return React elements.
```js
function Greeting({ message }) {
  return <h1>{"Hello, ${message}"}</h1>

} 
```
2. **Class** **Components:** You can also use ES6 class to define a component. The above function component can be written as:
```js
class Greeting extends React.Component {
  render() {
    return <h1>{`Hello, ${this.props.message}`}</h1>
  }
}
```

### Differentiate between Functional and Class components?

| Class component | Functional component|
| ------------- | ------------- |
| Stateful components | Stateless components |
| React lifecycle methods are used | React lifecycle methods  cannot be used |
| Hooks are not used | Hooks can be easily used in functional components to make them Stateful |
| requires you to extend from React. Component and create a render function which returns a React element | they're JavaScript functions that accepts props as an argument and returns a React element(JSX) |

### What is State?
State of a component is an object that holds some information that may change over the lifetime of the component.

- every component in react has a built-in state object, which contains all the property values that belong to that component.
- the state object controls the behaviour of a component. Any change in the property values of the state object leads to the re-rendering of the component.
- State is similar to props, but it is private and fully controlled by the component i.e., it is not accessible to any other component till the owner component decides to pass it.

```js
export default function App() {
  const [count, setCount] = useState(0);

function handleClick(){
  setCount(count + 1);
}

  return (
    <div className="App">
     <button onClick={handleClick}>Clicked {count} times</button>
    </div>
  );

}
```

### What are Props?
- we use props in React to pass data from one component to another (from a parent component to a child component(s))
- props is just a shorter way of saying properties
- they are useful when you want the flow of data in your app to be dynamic

### What is Prop drilling?
- pass data from a component that is higher in the hierarchy to a component that is deeply nested.
- so we pass props from a source component and keep passing the prop to the next component in the hierarchy till we reach the deeply nested component.
- **disadvantage:** components that should otherwise be not aware of the data have access to the data.

### What are Lifecycle Methods?
- every React Component has a lifecycle of its own
- it's a series of methods that are invoked in different stages of the component’s existence
- 4 Stages of a Component's Lifecycle are:

**Initialization**
- stage where the component is constructed with the given Props and default state
- This is done in the constructor of a Component Class

**Mounting**
- when an instance of a component is being created & inserted into the DOM

**Updating**

- when a component is being re-rendered as a result of changes to either of its props or state
- component is updated and the application is repainted

**Unmounting**

- when a component is removed from the DOM

### What is React Router?
- Routing is a process in which a user is directed to different pages based on their action or request
- React router is a standard library used in React applications to handle routing and allow navigation between views of various components

**Main Component of React Router**

- **BrowserRouter:** It’s a router implementation **to keep your UI in sync with the URL**. It is the **parent component** that is used to store all of the other components.
- **Routes:** chosen based on the best match instead of being traversed in order.
- **Route:** conditionally shown component that **renders some UI when its path matches the current URL.**
- **Link:** used to create links to different routes and implement navigation around the application. It works like `<a>`

### What are Higher Order Components?
- function that takes a component as an argument and returns a new component
```jsx
const NewComponent = higherOrderComponent(orginalComponent)
```
- for reusing component
- to share common functionality between the components
- created an arrow function `UpdatedComponent` which takes `OriginalComponent` as an argument & returns a `NewComponent`
```jsx
import React from "react";

const UpdatedComponent = (OriginalComponent) => {
  class NewComponent extends React.Component {
    render() {
      return <OriginalComponent />;
    }
  }
  return NewComponent;
};
```

### What are React Hooks?
- functions that let us “hook into” React state and lifecycle features from a functional component
- **useState** - used to manage the state in your component. Returns a stateful value and an updater function to update it.
- **useEffect** - to perform **side effects** like → API calls, data fetching, direct DOM updates, timers like setTimeout()
- **useContext** - used for creating common data that is to be accessed by the components hierarchy without having to pass the props down to each level
- **useReducer** - useState alternative to help with complex state management
- **useRef** - permit creating a reference to the DOM element directly within the functional component
- **useMemo** - It returns a memoized value that helps in performance optimisations
- **useCallback** - It returns a memorized version of a callback to help a child component not re-render unnecessarily


### How to prevent re-renders?
**Reason for re-renders in React:**

- occurs when props or the state of the component has been changed.
- Re-rendering components that are not updated, affects the performance of an application.
        
**Use React.memo()** to prevent re-rendering on React function components.

### What are the different ways to style a React component?
1. **Inline Styling:** make sure the value of style is a JavaScript object
```js
<h3 style={{ color: "Yellow" }}>This is a heading</h3>
```
2. **JavaScript object:** create a separate JavaScript object and set the desired style properties, use this object as the value of the inline style attribute
```js
class RandomComponent extends React.Component {

 headingStyles = {
   color: "blue",
   fontSize: "48px"
 };

 render() {
   return (
     <div>
       <h3 style={this.headingStyles}>This is a heading</h3>
     </div>
   );
 }
}
```
3. **CSS Stylesheet:** create a separate CSS file, write all the styles for the component inside it, import it inside the component file
```js
import './RandomComponent.css';

class RandomComponent extends React.Component {
 render() {
   return (
     <div>
       <h3 className="heading">This is a heading</h3>
     </div>
   );
 }
}
```
4. **CSS Modules:** create a file with “.module.css”‘ extension, styles.module.css
```js
.paragraph{
 color:"red";
 border:1px solid black;
}
```

### What are the techniques to optimize React app performance?
1. **Using useMemo()**
- sometimes a CPU-Expensive function gets called repeatedly due to re-renders of a component, which can lead to slow rendering
- useMemo( ) hook can be used to cache such functions by calling them only when needed

2. **Using React.PureComponent**
- checks the state and props of a component to know whether the component should be updated
- instead of using the simple React.Component, we can use React.PureComponent to reduce the re-renders of a component unnecessarily

3. **Maintaining State Colocation**
- process of moving the state as close to where you need it
- when we have unnecessary states inside the parent component it makes the code less readable and harder to maintain.
- having many states inside a single component leads to unnecessary re-renders for the component.
- It is better to shift states which are less valuable to the parent component, to a separate component.
    
4. **Lazy Loading**
- technique to reduce the load time of a React app. Lazy loading helps reduce the risk of web app performances to a minimum

### How to pass data between React components?
1. Parent —> Child (using props)
```js
import Child from "./Child";

const Parent = () => {
  return (
    <div>
      <Child name="Namya" />
    </div>
  );
};

export default Parent;
```
```js
import React from "react";

const Child = (props) => {
  return <div>Hi my name is {props.name}!</div>;
};

export default Child;
```
2. Child —> Parent (using functions)
```js
import React, { useState } from "react";
import Child from "./Child";

const Parent = () => {
  const [word, setWord] = useState("Parent");
  return (
    <div>
      <h1>{word}</h1>
      <Child changeWord={(word) => setWord(word)} />
    </div>
  );
};

export default Parent;
```
```js
import React, { useState } from "react";
import Child from "./Child";

const Parent = () => {
  const [word, setWord] = useState("Parent");
  return (
    <div>
      <h1>{word}</h1>
      <Child changeWord={(word) => setWord(word)} />
    </div>
  );
};

export default Parent;
```

### What is Conditional rendering?
- dynamic output of user interface markups based on a condition state
- works in the same way as JavaScript conditions
- using conditional rendering, it is possible to toggle specific application functions, API data rendering, hide or show elements, decide permission levels, authentication handling, and so on
- different approaches: if-else conditional logic, ternary operators

### What is Redux?
- handling multiple states from multiple components efficiently can become challenging when the application grows in size
- being a state management library, Redux will basically store and manage all the application's states
- components dispatch a certain thing known as Actions
- these Actions reach Reducers, Reducers go to Central Store (which manages all the state of the application)
- these Central Store once they’re being changed they send a trigger to Subscription
- subscription then passes the updated states as props to the components
- Components → Dispatch  Action → Reducer → Central Store → send Trigger to Subscription → passes the updated states as props to the components

### What are Controlled and Uncontrolled Components?
- in a controlled component, form data is handled by a React component
- in uncontrolled components, form data is handled by the DOM itself

### What are Pure components?
If a component renders the same output for the same state and props, then it is considered as Pure component

### What is strict mode?
- highlight potential problems in an application
- performs additional checks
- `<React.StrictMode>` tags need to be added


