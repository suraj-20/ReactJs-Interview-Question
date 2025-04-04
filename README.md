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