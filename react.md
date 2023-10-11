## React

> What is the React ?

- **Library**
  - A JavaScript library for build both web and native user interfaces
- **Use Case**
  - Single Page Application (SPA)
    - A web application that loads a single HTML page and dynamically updates that page
  - Progressive Web Application (PWA)
    - A type of web application that uses modern web technologies to provide an app-like experience
- **Company**
  - Created by Facebook in 2011
  - Now maintained by a community of developers

## Syntax

### JSX

> What is the JSX ?

- **Stand For**
  - JavaScript XML
- **Definition**
  - Html-like
    - Is a syntax extension for Javascript that lets you write HTML-Like Markup inside JS file
  - Prefer
    - Although there are other ways to write components, most React developers prefer the conciseness of JSX, and most codebases use it
- **Convert**
  - JSX can be converted to JS using a transpiler, such as Babel.
  - This allows you to use JSX even in browsers that do not support it natively.

```js
const element = <h1>Hello, world!</h1>;

// This code would render an `h1` element with the text "Hello, world!" to the DOM.
```

> Do we have to use JSX format for React files?

- Don't Need
  - you do not have to use JSX format for React files.
- Pure
  - You can write React components in pure JavaScript,
- Easier
  - Many people find JSX to be more expressive and easier to read and maintain.

> what is different between `JSX vs JS` ?

- **Syntax**
  - JS
    - JavaScript
  - JSX
    - HTML-like
- **Use case**
  - JS
    - General-purpose programming language
  - JSX
    - Building React components

```js
// JSX
const element = <h1>Hello, world!</h1>;

// JS -> If don't use of Jsx syntax shoul use of createElement
const element = React.createElement("h1", null, "Hello, world!");
```

## Component

> How to create components in React ?

- **Ways**
  - Functional
    - They are just JavaScript **functions** that return an element and **simpler** to create and use
    - That accept **props** object as the first parameter and **return** React elements to render
  - Class
    - They are more **complex**, but they offer more **features**, such as state and lifecycle method

```js
// way 1 -> Funcional Component
function Button() {
  return <button>Click me!</button>;
}

// way 2 -> Class Component
class Button extends React.Component {
  render() {
    return <button onClick={this.handleClick}>Click me!</button>;
  }

  handleClick() {
    // Do something when the button is clicked
  }
}
```

> What is the difference between Element and Component?

- **Definition:**
  - Element:
    - A plain object describing what should appear on the screen in terms of DOM nodes or other components.
  - Component:
    - A reusable piece of code defining how a UI segment should look and behave.
- **Methods:**
  - Element:
    - Does not have any inherent methods.
  - Component:
    - Can have state and lifecycle methods.
- **Mutability:**
  - Element:
    - Once an element is created, it cannot be mutated.
  - Component:
    - Can be altered even after its creation.

```js
function Button() {
  // Button is an element
  return <button>Click me!</button>;
}

// App is a component (functional)
const App = () => {
  return (
    <div>
      <Button />
    </div>
  );
};
```

### List

#### Class

#### Function

#### Pure

> what is `Pure component` ?

- Render
  - Pure components are a type of React component that only **re-render** when their inputs **change**
- Performance
  - This improve the performance of your application by reducing the number of re-renders that occur.
- Create
  - To create a pure component, you can extend the `React.PureComponent` class.
- Compare
  - This class implements a `shouldComponentUpdate()` method that compares the current props and state to the previous props and state. If the props and state are the same, the component will not re-render.

```js
class PureButton extends React.PureComponent {
  render() {
    return <button>{this.props.text}</button>;
  }
}
```

#### Difference

> what is difference between `class` and `functinoal` component ?

- **State Management**
  - **Class:**
    - Suitable for managing complex local state and lifecycle methods.
    - Maintain stateful logic within the component.
  - **Function:**
    - Use hooks like `useState` and `useEffect` for managing local state and side effects.
    - Perfect for simpler state management needs.
- **Lifecycle Methods**
  - **Class:**
    - Has access to lifecycle methods like `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount`.
    - Useful for operations like data fetching, subscriptions, or manual DOM manipulations.
  - **Function:**
    - Utilize the `useEffect` hook to perform side effects and cleanup.
    - Replaces most lifecycle methods and offers a more declarative approach.
- **Readability and Simplicity**
  - **Class:**
    - Can become verbose with lifecycle methods and class-based syntax.
    - Might be harder to read for simple components.
  - **Function:**
    - Concise and easy to read, especially for presentation-only components.
    - Hooks provide a simpler and more predictable way to handle component logic.
- **Performance:**
  - **Class:**
    - Slightly heavier in terms of memory usage and initialization time.
    - Unoptimized re-renders might cause performance issues.
  - **Function:**
    - Lightweight and optimized for performance.
    - Hooks enable efficient re-renders and updates, improving overall performance.
- **Compatibility and Future-Proofing:**
  - **Class:**
    - Stable and widely used, especially in older React applications.
    - Might continue to receive support but considered a legacy approach.
  - **Function:**
    - The modern and recommended approach, especially with the widespread adoption of hooks.
    - Future React features and optimizations are likely to be focused on functional components and hooks.

> When to use a Class Component over a Function Component?

- **State and Lifecycle methods:**
  - In older versions , if need to state and lifecycle should use of class , but now you can use of functional component
- **State**
  - when need to manage state within the component
- **Respond**
  - when need to respond to events the component's lifecycle

### Data

#### Props

> What are props in React?

- **Short For**
  - Properties
- **Communication**:
  - React components use props to communicate with each other.
  - They serve as a medium through which data flows in a React application.
- **Data Flow**:
  - Props allow the flow of information from parent components to their child components.
  - This mechanism enables the passing of specific data without altering the child components directly.
- **Flexible Values**:
  - While resembling HTML attributes, props in React are more versatile.
  - They are not limited to strings; you can pass various JavaScript values, including objects, arrays, and functions. This flexibility makes props a powerful tool for building dynamic and interactive React applications.

```js
// Parent component
const App = () => {
  // step 1 : Define data value (this value can be any JavaScript value)
  const user = {
    name: "Bard",
    age: 2,
  };

  return (
    <div>
      // Step 2: Pass data as props to child
      <ChildComponent user={user} />
    </div>
  );
};

// Child component
const ChildComponent = ({ user }) => {
  // step 3 : // Step 3: Receive props in child
  return (
    <div>
      // step 4 : Use props to render the component
      <h1>Hello, {user.name}!</h1>
      <p>You are {user.age} years old.</p>
    </div>
  );
};
```

#### State

> what is the `State` ?

- Store
  - state can hold any kind of javascript value including object
- Update
  - Immutability
    - When updating objects in React state, it's crucial to maintain immutability. This means not changing objects directly that are stored in the state.
  - Creating Copies
    - To update an object in the state, you should create a new object or make a copy of an existing one. The updated copy is then set as the new state.
- Re-render
  - Components re-render when the state changes
- Manage
  - Class Component:
    - Use `this.state` for state management.
  - Functional Component:
    - Utilize React hooks like `useState` for managing state in functional components.

```js
// Class Component
class ClassComponent extends Component {
  state = {
    count: 0, // State using class component state
  };

  // Handles incrementing the count
  handleIncrement = () => {
    this.setState((prevState) => ({
      count: prevState.count + 1,
    }));
  };

  render() {
    return (
      <div>
        <h2>Class Component</h2>
        <h1>Count: {this.state.count}</h1>
        <button onClick={this.handleIncrement}>Increment</button>
      </div>
    );
  }
}

// Functional Component
const FunctionalComponent = () => {
  const [count, setCount] = useState(0); // State using useState hook

  // Handles incrementing the count
  const handleIncrement = () => {
    setCount(count + 1);
  };

  return (
    <div>
      <h2>Functional Component with useState Hook</h2>
      <h1>Count: {count}</h1>
      <button onClick={handleIncrement}>Increment</button>
    </div>
  );
};
```

> Why should we not update the state directly?

- **Clarity and Readability**:
  - **Immutability**:
    - Ensures clear and predictable state changes.
    - Improves code readability and maintainability.
- **Optimized Performance**:
  - **Prevents Unnecessary Rerenders**:
    - Immutable state avoids unnecessary component renders.
    - Optimizes application performance.
- **Efficient Debugging**:
  - **Traceable Changes**:
    - Immutable state facilitates easy tracking of changes.
    - Simplifies debugging processes.
- **Seamless Integration**:
  - **Library Compatibility**:
    - Immutability seamlessly integrates with state management libraries.
    - Enhances efficiency and development speed.

| **Aspect**        | **Direct Change**                    | **useState Hook**                                     |
| ----------------- | ------------------------------------ | ----------------------------------------------------- |
| **Correctness**   | Incorrect; no guaranteed re-renders. | Correct; ensures reactivity and UI updates.           |
| **Reactivity**    | No reactivity; UI may not update.    | Reactivity maintained; component re-renders properly. |
| **Immutability**  | Violates immutability principle.     | Preserves immutability; state updated immutably.      |
| **Debugging**     | Harder to trace state changes.       | Easier debugging; state changes are explicit.         |
| **Best Practice** | Not recommended in React.            | Standard and preferred method in modern development.  |
| **Rendering**     | UI may not reflect state changes.    | UI updates reliably with state changes.               |

```js
import React, { useState } from "react";

const StateChangeComponent = () => {
  // State variable using useState hook
  const [count, setCount] = useState(0);

  // 👎 Incorrect way
  const incrementCountDirectly = () => {
    count++; // This directly modifies the state (incorrect way)
    console.log("Incorrect count (direct change):", count);
    // Note: Directly changing state like this does not trigger re-renders or update UI
  };

  // 👍 Correct way
  const incrementCountCorrectly = () => {
    setCount(count + 1); // This updates the state correctly
    console.log("Correct count (useState hook):", count + 1);
    // Note: State changes using setCount trigger re-renders and update UI
  };

  return (
    <div>
      <h1>State Change Example</h1>
      <p>Count: {count}</p>
      <button onClick={incrementCountDirectly}>Increment Directly</button>
      <button onClick={incrementCountCorrectly}>Increment Correctly</button>
    </div>
  );
};

export default StateChangeComponent;
```

#### Difference

> What is difference between Props and State ?

- **Similarities**
  - both `state` and `props` are plain JavaScript objects and used to manage the data of a component,
- **Difference**
  - **Immutable**
    - **Props**:
      - Immutable; they cannot be modified or changed by the component receiving them.
    - **State**:
      - Mutable; can be changed using the `setState()` method, leading to re-renders.
  - **Re-render**
    - **Props**
      - when changed by parent component , cause to re-render child component
    - **State**
      - when changed the component will re-render whenever its state changes.
  - **Source**:
    - **Props**:
      - Received from parent components or external sources, allowing communication between components.
    - **State**:
      - Internal to the component, representing its own data that can change over time.
  - **Usage**:
    - **Props**:
      - passing data from parent to child components, enabling customization of child components.
    - **State**:
      - managing internal component data, handling dynamic content, form inputs, and etc.
  - **Test**:
    - **Props**:
      - Props are easier to test because they are immutable and passed from parent to child components.
    - **State**:
      - State is more difficult to test because it is mutable and internal to the component

| **Feature**    | **Props**                             | **State**                               |
| -------------- | ------------------------------------- | --------------------------------------- |
| **Mutability** | Immutable                             | Mutable (via `setState()`)              |
| **Re-render**  | On parent change                      | On internal state change                |
| **Source**     | External, parent components           | Internal component data                 |
| **Usage**      | Data passing, customization           | Managing internal data, dynamic content |
| **Testing**    | Easier (immutable, parent-child flow) | More complex (mutable, internal scope)  |

## Value

### Reference

> What is the use of refs?

- **Remember**
  - When you want a component to “remember” some information,
- **Render**
  - When you don’t want that information to trigger new renders, you can use a ref.
- **Direct Access**
  - Refs allow you to access DOM Element directly
- **Use Case**
  - which can be useful for certain task such as focusing an input element or animating an element
- **Control DOM events**
  - Refs allow you to attach event listeners to DOM elements and remove them when necessary. This can be useful for tasks such as implementing custom drag-and-drop functionality.
- **Integration Library**
  - Some libraries require refs to access DOM elements. Such as if you create a chart with libraries, you may need to pass a ref to the DOM element where you want to render the chart.
- **Use**
  - To use a ref in a functional component, you can use the `useRef()` hook.

> How to create Refs ?

- **Class components:**
  - To create a ref in a class component, you can use the `createRef()` method.
  - This method returns a new ref object, which you can then assign to a property on your component instance.

```js
class MyComponent extends React.Component {
  constructor(props) {
    super(props);

    this.inputRef = React.createRef();
  }

  render() {
    return (
      <div>
        <input ref={this.inputRef} />
      </div>
    );
  }
}
```

- **Functional components:**
  - To create a ref in a functional component, you can use the `useRef()` hook.
  - This hook returns a mutable object with a `.current` property, which is initially set to `null`.

```js
import React, { useRef } from "react";

const MyComponent = () => {
  const inputRef = useRef();

  return (
    <div>
      <input ref={inputRef} />
    </div>
  );
};
```

- **Access**
  - You can access the DOM element it refers to by using the `.current` property.

```js
inputRef.current.focus();
```

## Hooks

### UseState

> What is the purpose of callback function as an argument of `setState()`?

- **Purpose**
  - **Previous State**
    - The callback function receives the previous state, enabling state updates based on its current value
  - **Consistency**
    - Ensures state remains consistent, even with multiple updates before re-rendering.
  - **Race Conditions**
    - Prevents race conditions by guaranteeing a single state update, regardless of multiple rapid changes
  - **Performance.**
    - The callback function allows you to batch state updates together, which can improve performance by reducing the number of times that React has to re-render the component.

```js
import React, { useState } from "react";

const MyComponent = () => {
  const [count, setCount] = useState(0);

  const handleClick = () => {
    // Update the state based on the previous state
    setCount((prevState) => prevState + 1);
  };

  return (
    <div>
      <button onClick={handleClick}>Increment count</button>
      <h1>Count: {count}</h1>
    </div>
  );
};

export default MyComponent;
```

### UseEffect

### UseRef

- **Return Object**
  - This hook returns a mutable object with a `.current` property, which is initially set to `null`.
- **Manage Data**
  - You can use state to manage the data in your application, and React will take care of updating the DOM automatically.
- **Access Dom**
  - Refs are especially useful for tasks that require imperative DOM access, such as focusing an input element or animating an element.
- **Clean Up**
  - When using refs, it is important to clean them up when they are no longer needed. This can be done by using the `useEffect()` hook.

```js
import React, { useRef } from "react";

const MyComponent = () => {
  const inputRef = useRef();

  const focusInput = () => {
    inputRef.current.focus();
  };

  return (
    <div>
      <input ref={inputRef} />
      <button onClick={focusInput}>Focus input</button>
    </div>
  );
};
```

## Render

### Client

### Server

### List

> Why is it important to use key props in React lists?

- **Identify**
  - Key help react Identify which item have changed , are added or are removed
- **Preservation**
  - Key ensure that the state of component in the list is preserved correctly
- **Re-render**
  - Without keys , react may re-render the components unnecessarily , causing unexpected behavior
- **Reconciliation**
  - Component with different keys , allowing react to avoid unnecessary re-render and reconciliation
- **Efficiently**
  - Keys enable React to update the DOM efficiently , reducing the time taken for re-renders

```jsx
const items = [
  { id: 1, text: "Item 1" },
  { id: 2, text: "Item 2" },
  { id: 3, text: "Item 3" },
];

const ListComponent = () => {
  return (
    <ul>
      {items.map((item) => (
        // key prop is set to unique id of each item
        <li key={item.id}>{item.text}</li>
      ))}
    </ul>
  );
};
```

## Event

> What is the difference between HTML and React event handling ?

- **Basic Concept**
  - **HTML**: Uses inline attributes in HTML elements.
  - **React**: Functions are passed as props in JSX elements.

```jsx
// Html
<button onclick="handleClick()">Click Me</button>

// React
<button onClick={handleClick}>Click Me</button>
```

- **Syntax**
  - **HTML**: Inline event handler attributes.
  - **React**: CamelCase event handler names as props in JSX.

```js
// Html
<button onclick="handleClick()">Click Me</button>

// React
<button onClick={handleClick}>Click Me</button>
```

- **Event Object**
  - **HTML**: Event object is automatically passed.
  - **React**: Event object must be explicitly passed if needed.

```jsx
// Html
<button onclick="handleClick(event)">Click Me</button>

// React
<button onClick={(e) => handleClick(e)}>Click Me</button>
```

- **Binding `this`**
  - **HTML**: `this` refers to the triggering element.
  - **React**: Requires manual binding in class components or closures in functional components.

```jsx
// Html
<button onclick="handleClick(this)">Click Me</button>

// React
<button onClick={this.handleClick.bind(this)}>Click Me</button>
```

- **Preventing Default Behavior**
  - **HTML**: `event.preventDefault()`.
  - **React**: Same approach, can be done in both class and functional components.

```jsx
// Html
<a href="#" onclick="handleClick(event)">Click Me</a>

// React
<a href="#" onClick={(e) => { e.preventDefault(); handleClick(e); }}>Click Me</a>
```

## Dom

### Real

> What is Real DOM ?

- **Stand For**
  - Document Object Model
- **Represent**
  - The DOM is simple words represents the UI of your application
- **Update**
  - when is a change in the state of your application UI , the DOM get updated to represent that change
- **Performance**
  - For catch is frequently manipulating the DOM affects performance , making it slow

### Virtual

> What is Virtual DOM?

- **Lightweight**
  - The Virtual DOM is a lightweight representation the real DOM
- **Tree Data Structure**
  - It is a tree data structure that contains all of the elements in your React application.
- **Faster**
  - The Virtual DOM is much faster to update than the real DOM,
- **Performant**
  - It makes React applications very performant.

```jsx
// React Virtual DOM
const virtualElement = (
  <div>
    <h1>Hello, Virtual DOM!</h1>
    <p>This is a virtual representation of the UI.</p>
  </div>
);
```

> How Virtual DOM works?

1. **Representation Creation**:
   - React **creates** a Virtual DOM (VDOM) when a component is **rendered**.
2. **Differential Comparison**:
   - When a component's state or props **change**, React generates a **new** VDOM representation.
   - For Identify **Differences** compares it with the previous VDOM using a diffing **algorithm**
3. **Efficient DOM Updates**:
   - React updates only the **specific** parts of the real DOM that have changed, minimizing **manipulations**.
   - This targeted approach significantly enhances application **performance**.
