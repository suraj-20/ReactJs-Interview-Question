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