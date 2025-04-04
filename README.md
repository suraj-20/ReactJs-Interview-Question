# ReactJs-Interview-Question

## Q.1 What is ReactJs ?

React is a Javascrip library used for developing user interface. It is used for developing single page application and allow's developer to build reusable UI componenets. React was developed and maintained by Facebook and is widely used for building complex UI for web applications.

## Q.2 What is JSX?

JSX is a syntax extension for Javascript, used with react to describe the structure of User Interfaces. It allows developers to write HTML-like code within Javascript, making it easier to write and understand React components. Javascript is transpiled to plain Javascript, which can be understood by the browsers, by using a tool like Babel.

```bash
import React from 'react';

const ExampleFunctionalComponent = (props) => {
  return (
    <div>
      <h1>Hello, {props.name}!</h1>
      <p>This is an example of a functional React component written in JSX.</p>
    </div>
  );
};

export default ExampleFunctionalComponent;
```

## Q.3 What is React.Fragment?

React.Fragment is a special component in React that allows us to group a list of children without adding extra nodes to the DOM.

```bash
import React from 'react';

const ExampleFunctionalComponent = (props) => {
  return (
    <React.Fragment>
      <h1>Hello, {props.name}!</h1>
      <p>This is an example of a functional React component written in JSX.</p>
    </React.Fragment>
  );
};

export default ExampleFunctionalComponent;
```

## Q.4 What is state and props?

In React, both state and props are used to manage or render component. However, they are used for different purposes and have different characteristics.

Props (short for poperties) are a way of pasing data from parent component to child component. Props are read-only, which means that the child component cannot modify the props it recieve from the parent component. Props are used to pass data and/or function that a child component is needs to perform its job.

State is a way of managing component's internal state or data. The state is managed within the component and can be modified by the component itself. The state is used to keep track of changing information within component, such as the value of the text input and the status of the toggle switch.

Summary:

Props are used to pass data from parent component to a child component and are read-only.

State is used to manage component's internal state and can be modified by the component.

## Q.5 What are the Reack Hooks?

Hooks are a feature in React that allows you to add state and other React features to functional components. Hooks make it possible to add these features to functional components as well, making them a more versatile and flexible way to build components in React.

There is the list of React Hooks - 

React provides several built-in hooks that can use in your functional components:

- useState: allows you to add state to your functional components

```bash

import React, { useState } from 'react';

function ExampleComponent() {
  // Declare a state variable called "count" and initialize it to 0
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>Click me</button>
    </div>
  );
}

export default ExampleComponent;

```

- useRef: Allows you to access and modify the value of a DOM node or a React component instance. The useRef hook is a way to access the value of a DOM element or a component instance in React. It is often used to store a reference of a DOM element so that you can access its properties and methods such as its position, size, or to manipulate its style, or to store a reference to a component instance to access its methods, such as to trigger a re-render.

```bash

import React, {useRef, useEffect} from 'react';

function TextInput() {
    const inputRef = useRef(null);

    useEffect(() => {
        inputRef.current.focus();
    }, []);

    return <input type='text' ref={inputRef} />;
}

export default TextInput;

```

- useEffect: Allows you to perform side effects in your functional components, such as API calls or updating the document title.

```bash

import React, {useState, useEffect} from 'react';

function ExampleComponent() {
    const [count, setCount] = useState(0);

    useEffect(() => {
        document.title = `You clicked ${count} times`;
    });

    return (
        <div>
            <p>You clicked {count} times</p>
            <button onClick{() => setCount(count + 1)}>Click me</button>
        </div>
    );
}

export default ExampleComponent;

```

Note that the effect function will run every time the component renders, which includes both initial render and any subsequent updates. If you only want the effect to run on certain updates, you can provide an array of dependencies as the second argument to useEffect. The effect function will only run if one of the dependencies has changed.

```bash
import React, {useState, useEffect} from 'react';

function ExampleComponent() {
    const [count, setCount] = useState(0);

    useEffect(() => {
        document.title = `You clicked ${count} times`;
    },[count]); // Only re-run the effect if count changes

    return (
        <div>
            <p>You clicked {count} times</p>
            <button onClick{() => setCount(count + 1)}>Click me</button>
        </div>
    );
}

export default ExampleComponent;

// This helps to optimize the performance of your component by avoiding unnecessary updates.
```

- useContext: used to access data from a Context in a React application.

- useReducer: Allows you to manage state with a reducer function in your functional components. It provides a way to handle complex state updates in a predictable and organized manner and is often used as an alternative to useState.

```bash
import React, {useReducer} from 'react';

function reducer(state, action) {
    switch (action.type) {
        case 'increment':
            return { count: state.count + 1};
        case 'decrement': 
            return { count: state.count - 1};
        default:
        throw new Error();
    }
}

function counter() {
    const [state, dispatch] = useReducer(reducer, {count: 0});

    return (
        <>
            <p>Count: {state.count}</p>
            <button onClick={() => dispatch({ type: 'decrement' })}>-</button>
            <button onClick={() => dispatch({ type: 'increment' })}>+</button>
        </>
    );
}

export defult Counter;
```

- useCallback: allows you to memorize your callback functions for performance optimization. The callback hook is a way to optimize performance in React by memoizing a function. When a function is memoized, it means that its result is cahced and reused between render cycles, instead of being recalculated every time the component re-renders. Thsi can be usefull for functions that are passed as props to child components, to avoid unnecessary re-render of those components.

```bash
import React, {useState, useCallback} from 'react';

function Counter() {
    const [count, setcount] = useState(0);

    const increment = usecallback(() => {
        setCount((c) => c+ 1);
    }, [setCount]);

    return (
        <>
            <p>Count: {count}</p>
            <button onClick={increment}>Increment</button>
        </>
    );
}

export default Counter;
```

- useMemo: Allows you to memoize values computed in your functional components for performance optimization. The useMemo hook is a way to optimize performance in React by memoizing a value. When a value is memoized, it mean sthat its result is cached and reused between render cycles, instead of being recalculated every time the component re-renders. This can be usefull for optimizing expensize calcualtions, such as filtering or mapping over large data sets, or complex calculations that are used in the render methods.

```bash
import React, { useState, useMemo } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  const doubleCount = useMemo(() => count * 2, [count]);

  return (
    <>
      <p>Count: {count}</p>
      <p>Double Count: {doubleCount}</p>
      <button onClick={() => setCount((c) => c + 1)}>Increment</button>
    </>
  );
}

export default Counter;

```

## Q.6 useState vs useRef ?

useState is used to manage state in a functional component, while useRef is used to store a reference to a DOM element or a component instance.

## Q.7 useCallback vs useMemo?

useCallback is used to memoize callback functions. This is helpfull when you have a component that renders often and you want to prevent it from re-creating the function on every render.

useMemo is used to momoize a value. This is helpful when you have a component that perform an extensize calculation on render and you want to prevent it from re-calculating the value on every redner.

## Q.8 useState vs useReducer?

useState is a simple hook that is suitable for managing small amount of state, while useReducer is more powerful hook that is recommended for managing complex state and enforcing strict state transition logic.
