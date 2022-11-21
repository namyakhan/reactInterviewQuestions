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
- [What is Prop drilling?](#what-is-prop-drilling)


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




