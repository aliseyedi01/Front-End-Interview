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

> what are the Benefits of Reacts ?

- **Universal Application:**
  - Supports both client-side and server-side rendering, ensuring versatile deployment options.
- **Efficient Testing:**
  - Facilitates unit testing and integrates seamlessly with tools like Jest, simplifying the testing process.
- **Component-Based:**
  - Promotes code reusability and maintainability through modular, self-contained UI components.
- **Virtual DOM:**
  - Enhances performance by updating only changed parts of the DOM, improving user experience.
- **JSX (JavaScript XML):**
  - Allows writing HTML-like code in JavaScript, enhancing readability and simplifying UI management.
- **Easy Integration:**
  - Easily integrates into existing projects, enabling incremental upgrades and A/B testing.
- **Developer Tools:**
  - Offers powerful tools like React DevTools for component inspection, state tracking, and debugging, enhancing productivity.
- **Performance Optimization:**
  - Utilizes virtual DOM, memoization, and PureComponent for efficient rendering, with tools like React Profiler for performance tuning.
- **React Native:**
  - Enables cross-platform mobile app development, saving time by sharing code between web and mobile applications.

> What are the limitations of React?

- **Limited Scope**:
  - React serves as a view library, not a comprehensive framework, requiring additional components for complete application development.
- **Integration Complexity**:
  - Integrating React into traditional MVC frameworks demands extra configuration and setup efforts.
- \*_JSX Complexity:_
  - JSX, while powerful, can be complex and challenging to understand, especially for developers accustomed to traditional HTML and JavaScript.
- **SEO Challenges:**
  - React applications are primarily rendered on the client side, which can be a challenge for search engine optimization (SEO) as search engines might have difficulty crawling and indexing content.
- **Performance Optimization:**
  - While React's virtual DOM helps improve performance, improper usage of state and props can still lead to inefficient renders, affecting the overall application performance.
- **Compatibility Issues:**
  - React's fast-paced development can lead to compatibility issues when upgrading to newer versions, requiring developers to update their codebase and dependencies frequently.
- **Lack of Opinionated Structure:**
  - React leaves a lot of architectural decisions to developers, which can lead to inconsistency and lack of standardized patterns in larger teams and projects.
- **Large Bundle Size:**
  - React applications, especially when not optimized properly, can result in large bundle sizes, impacting the initial loading time and user experience, particularly on slower internet connections or mobile devices.

## JSX

> What is the JSX ?

- **Stand For**
  - JavaScript XML
- **Html-like**
  - Is a syntax _extension_ for Javascript that lets you write _HTML-Like_ Markup inside JS file
- **Prefer**
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

#### Functional

#### Pure

> what is `Pure component` ?

- **Re-render**
  - Pure components are a type of React component that only **re-render** when their inputs **change**
- **Imporve Performance**
  - This improve the performance of your application by reducing the number of re-renders that occur.
- **Create**
  - To create a pure component, you can extend the `React.PureComponent` class.
- **Compare**
  - This class implements a `shouldComponentUpdate()` method that compares the current props and state to the previous props and state. If the props and state are the same, the component will not re-render.

```js
class PureButton extends React.PureComponent {
  render() {
    return <button>{this.props.text}</button>;
  }
}
```

#### High-Order

> What is the `HOC` ?

- **Stand For**
  - Hight Order Component
- **Input & Return Component**
  - A React component that takes another component as input and returns a new component as output.
- **New Component**
  - Return a new component with : Additional props and Enhanced behavior
- **Functional Composition**
  - That leverage the principle of functional composition by : Wrapping component , Adding extra feature or behaviors
- **Pure Component**
  - Both HOCs and Pure Components in React share the similarity of enhancing component functionality without altering the original component's behavior.
  - HOCs wrap components, adding features, while Pure Components optimize rendering without altering behavior.

```jsx
import React from "react";
import { useAuth } from "./useAuth";

function AuthenticatedComponent(Component) {
  const user = useAuth();

  if (!user) {
    return <div>Please log in to access this page.</div>;
  }

  return <Component />;
}

function App() {
  return (
    <AuthenticatedComponent>
      <h1>This is a protected page.</h1>
    </AuthenticatedComponent>
  );
}
```

> What are the use Cases of HOC ?

- **Reusability:**
  - HOCs encapsulate common logic, enabling multiple components to share it without redundancy, promoting code reusability and maintainability.
- **Conditional Rendering:**
  - HOCs can conditionally render components based on factors such as authentication status or user permissions, allowing dynamic component behavior.
- **Data Fetching:**
  - HOCs handle data fetching operations, making API calls and passing data as props to components.
  - This separation keeps data logic separate from presentation logic.
- **State Management:**
  - HOCs manage stateful logic, handling form inputs, managing local component state, or even integrating with state management libraries. Components remain focused on rendering.
- **Props Manipulation:**
  - HOCs can modify or enhance component props before rendering, injecting additional props or transforming existing ones, allowing for flexible component interfaces.
- **Route Protection:**
  - HOCs can protect routes by checking user authentication or authorization.
  - If a user lacks access rights, the HOC can redirect them to a login page or another appropriate route, ensuring security.

> What similarities exist between HOCs and Pure Components?

- **Enhancement Without Modification:**
  - Both HOCs and Pure Components enhance functionality without altering the core behavior of the original component.
- **Reusability:**
  - Both concepts promote code reuse and modularity in React applications, ensuring efficient and clean component design.
- **Efficient Rendering:**
  - Both techniques optimize rendering.
  - HOCs can prevent unnecessary renders by memoizing components, and Pure Components ensure efficient re-rendering through shallow prop and state comparisons.

```javascript
// HOC -> enhanced functionality without altering the wrappedComponent
const withLogging = (WrappedComponent) => {
  return (props) => {
    console.log(`Component is rendered with props:`, props);
    return <WrappedComponent {...props} />;
  };
};

// Pure Component -> preventing unnecessary re-renders based on props changes
const PureComponentExample = React.memo(({ data }) => {
  return <div>{data}</div>;
});
```

#### Fragment

> What are fragments?

- **Group Element**
  - Lets you group elements without a wrapper node.
- **Avoid Adding Unnecessary Node**
  - To avoid adding unnecessary nodes to the DOM while grouping multiple elements
  - Provides a cleaner way to structure components without introducing extra divs or other elements.
- **Syntax**
  - Using Angle Brackets (Shorthand Syntax)
  - Using `<Fragment>` Syntax

```jsx
// way 1
<>
	<h1>Hello</h1>
	<p>React Fragments</p>
</>

// way 2
<Fragment key={post.id}>
	<h1>Hello</h1>
	<p>React Fragments</p>
</Fragment>
```

> What are the Benefit Fragment ?

- **No Extra DOM Nodes:**
  - Fragments don't create an extra DOM node in the output, resulting in cleaner HTML structure.
- **Improved Performance:**
  - Avoiding unnecessary parent elements can improve the performance, especially in large applications.
- **Cleaner Component Structure:**
  - Fragments allow components to have a cleaner structure by eliminating the need for wrapping divs or other elements.
- **Faster Rendering:**
  - Fragments contribute to faster rendering in React applications.
  - By eliminating the need for extra DOM nodes, can render more quickly.

#### Suspense

>     What is the `Suspense` ?

- **Fallback**
  - lets you display a fallback until its children have finished loading.
- **Blank Screen**
  - This can be useful for preventing users from seeing a blank screen while data is loading, or for handling errors that occur while loading data.

```js
const MyComponent = () => {
  const [data, setData] = useState(null);

  useEffect(() => {
    // Load data from an API
    fetch("/api/data")
      .then((response) => response.json())
      .then((data) => setData(data));
  }, []);

  if (data === null) {
    return <div>Loading...</div>;
  }

  return <div>{data.message}</div>;
};

const App = () => {
  return (
    <Suspense fallback={<div>Loading...</div>}>
      <MyComponent />
    </Suspense>
  );
};
```

#### StrictMode

> what is the `StrictMode` ?

- **Common Bug**
  - lets you find common bugs in your components early during development.
- **Development**
  - A development mode only feature that checks for potential problems in an application.
- **Render UI**
  - It does not render any visible UI or impact the production build.
- **Check**

  - It activates additional checks and warnings for its descendant components.

- StrictMode can be used to identify a number of potential issues, including:
  - Components with unsafe life cycles
  - Legacy string ref API usage
  - Warning about deprecated APIs
  - Detecting unexpected mutations
  - Detecting unexpected side effects

To use StrictMode, simply wrap your application in a `<StrictMode>` component. For example:

```js
import React from "react";
import ReactDOM from "react-dom";
import StrictMode from "react-strict-mode";

const App = () => {
  return (
    <StrictMode>
      <h1>My Application</h1>
    </StrictMode>
  );
};

ReactDOM.render(<App />, document.getElementById("root"));
```

> what are the benefits of `StrictMode` ?

- **Identify Problems**
  - To identify potential problems in your code early on, before they cause problems for your users.
- **Robust Code**
  - It can help you to write more robust and reliable code.
- **Catch Error**
  - It can help you to catch errors that would be difficult to find otherwise.

> Why does strict mode render twice in React?

- **Identify Problems**
  - React StrictMode renders components twice in development mode to identify potential problems
- **Difficult bug**
  - This can be useful for catching bugs that would be difficult to find otherwise.
- **Side Effects**
  - This is used to detect accidental side effects in the render phase.

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

- **Before**
  - In older versions , if need to _state_ and _lifecycle_ should use of class
- **Now**
  - Now you for state and lifecycle , you can use of _Hooks_ and _Functional Component_

### Data

#### Props

> What are props in React?

- **Short For**
  - Properties
- **Communication**:
  - React components use props to communicate with each other.
  - They serve as a medium through which data flows in a React application.
- **Flow**:
  - Props allow the flow of information from parent components to their child components.
  - This mechanism enables the passing of specific data without altering the child components directly.
- **Values**:
  - While resembling HTML attributes, props in React are more versatile.
  - They are not limited to strings; you can pass various values, including objects, arrays, and functions.
  - This flexibility makes props a powerful tool for building dynamic and interactive React applications.

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

> why can't update props in react ?

- **Pure Function**
  - To ensure that components are pure functions, meaning that they should always return the same output given the same input.
- **Predict Behavior**
  - If we could update props, it would be difficult to predict the behavior of a component, as it could depend on the state of the component at any given time.
- **Easier Test**
  - If we could update props, it would be more difficult to understand how a component works and to write tests for it.
- **useState**
  - Can use the `useState` hook to track the state of a component and update it independently of props.

```js
function Counter(props) {
  const [count, setCount] = useState(props.count);

  return (
    <div>
      <h1>Count: {count}</h1>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

> What is `props drilling `

- **Pass Data through Component**
  - Is a technique in react where a prop is passed down from parent to its child component
- **Challenges and Difficulties**
  - lead to code that is difficult to read and maintain, especially when the component hierarchy is deep.
- **Finding a Better Way**
  - **Context API:**
    - Allows you to share data across components without explicitly passing props.
    - It's especially useful when dealing with global data or themes.
  - **State Management Libraries :**
    - Redux
      - that provides a predictable and unidirectional data flow.
    - MobX
      - that uses observables to automatically track state changes and update components.
    - Recoil
      - that provides a flexible and easy-to-use API for managing state.
    - Zustand
      - lightweight library that leverages Hooks and the Context API to manage global state.
    - RxJS
      - that can be used for managing state in complex and dynamic applications.

```js
// Step of Props Drilling 👇
// Parent component
const Parent = ({ theme }) => {
  return (
    <div>
      <Child theme={theme} />
    </div>
  );
};

// Child component
const Child = ({ theme }) => {
  return (
    <div>
      <GrandChild theme={theme} />
    </div>
  );
};

// GrandChild component
const GrandChild = ({ theme }) => {
  return (
    <div style={{ backgroundColor: theme }}>
      <h1>Hello, world!</h1>
    </div>
  );
};

// Render the app
function App() {
  return <Parent theme="light" />;
}
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

- **Reactivity**:
  - **Direct**:
    - No reactivity; UI may not update.
  - **Hook**:
    - Reactivity maintained; component re-renders properly.
- **Render**:
  - **Direct**:
    - Changing state directly does not trigger rendering.
  - **Hook**:
    - Changing state with `setState` hook triggers rendering.
- **Debug**:
  - **Direct**:
    - Harder to trace state changes.
  - **Hook**:
    - Easier debugging; state changes are explicit.
- **Immutability**:
  - **Direct**:
    - Violates immutability principle.
  - **Hook**:
    - Preserves immutability; state is updated immutably.

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

#### Element

> what is `Element` in React ?

- **Definition**:
  - An element in React represents a lightweight, plain JavaScript object that describes a component instance or a native DOM component (e.g., `<div>` or `<span>`).
- **Immutability**
  - Elements in React are immutable. Once an element is created, it cannot be changed or modified. Any updates require creating a new element.
- **Create**
  - Elements are the building blocks of React applications, representing the structure of the UI.
  - They are created using JSX syntax or `React.createElement()` function.

```jsx
// JSX sytanx
const element = <div>Hello, World!</div>; // JSX syntax

// React.createElement function
const element = React.createElement("div", null, "Hello, World!");
```

- **Render**
  - Elements are used in the `ReactDOM.render()` method to render the UI on the DOM.

```jsx
const element = <div>Hello, World!</div>;
ReactDOM.render(element, document.getElementById("root"));
```

- **Composition**
  - Elements are composed within components to create complex UI structures.

```jsx
const MyComponent = () => {
  return (
    <div>
      <h1>Hello, World!</h1>
      <p>This is a React element.</p>
    </div>
  );
};
```

#### Difference

> What is difference between Props and State ?

- **Similarities**

  - both `state` and `props` are plain JavaScript objects and used to manage the data of a component,

- **Difference**
  - **Immutable**
    - **Props**
      - Immutable; they cannot be modified or changed by the component receiving them.
    - **State**
      - Mutable; can be changed using the `setState()` method, leading to re-renders.
  - **Re-render**
    - **Props**
      - when changed by parent component , cause to re-render child component
    - **State**
      - when changed the component will re-render whenever its state changes.
  - **Source**
    - **Props**
      - Received from parent components or external sources
    - **State**
      - Internal to the component, representing its own data that can change over time.
  - **Usage**
    - **Props**:
      - passing data from parent to child components, enabling customization of child components.
    - **State**
      - managing internal component data, handling dynamic content, form inputs, and etc.
  - **Test**
    - **Props**
      - Props are easier to test because they are immutable and passed from parent to child components.
    - **State**
      - State is more difficult to test because it is mutable and internal to the component

| **Feature**    | **Props**                             | **State**                               |
| -------------- | ------------------------------------- | --------------------------------------- |
| **Mutability** | Immutable                             | Mutable (via `setState()`)              |
| **Re-render**  | On parent change                      | On internal state change                |
| **Source**     | External, parent components           | Internal component data                 |
| **Usage**      | Data passing, customization           | Managing internal data, dynamic content |
| **Testing**    | Easier (immutable, parent-child flow) | More complex (mutable, internal scope)  |

> what is difference between `Element` and `Component` ?

- **Create**
  - **Element**
    - Created using JSX or `React.createElement()`.
  - **Component**
    - Defined as functions.

```jsx
// Element
const element = <div>Hello, World!</div>; //JSX
const element = React.createElement("div", null, "Hello, World!"); //React.createElement()

// Component
const MyComponent = () => {
  return <div>Hello, World!</div>;
};
```

- **Usage**:
  - **Element**:
    - Describes what appears on the screen.
    - Often returned by components.
  - **Component**:
    - Building blocks of React applications.
    - Can have their own state and lifecycle methods.

```jsx
// Element
const content = <h1>Hello, World!</h1>;
const element = <div>{content}</div>;

// Component
const GreetingComponent = ({ name }) => {
  return <h1>Hello, {name}!</h1>;
};
```

- **Reusability**
  - **Element**
    - Basic and singular, not reusable.
  - **Component**
    - Reusable across the application.
    - Can be composed and combined with other components.

```jsx
// Element
const element = <div>Hello, World!</div>;

// Component
const Avatar = () => <img src="avatar.jpg" alt="User Avatar" />;
const UserProfile = ({ username }) => {
  return (
    <div>
      <Avatar />
      <GreetingComponent name={username} />
    </div>
  );
};
```

- **Composition**
  - **Element**
    - Used within components or directly in the render method.
  - **Component**
    - Composable, allowing complex UI structures by combining multiple components.

```jsx
// Element
const element = <div>Hello, {content}</div>;

// Component
const PageLayout = () => {
  return (
    <div>
      <HeaderComponent />
      <SidebarComponent />
      <MainContentComponent />
    </div>
  );
};
```

- **State Management**
  - **Element**
    - Stateless, does not have its own state.
  - **Component**
    - Can hold and manage local state using `useState()` hook or `this.state` (in class components).

```jsx
// Element
const element = <div>Hello, World!</div>;

// Component
const Counter = () => {
  const [count, setCount] = useState(0);
  // ...
};
```

### Condition

> What are inline conditional expressions?

- **Definition**:
  - A _concise_ way for rendering different content or components conditionally based on a given condition.
  - It replaces the need for `if` statements or blocks.
- **Use**
  1. Ternary Operator
     - The ternary conditional operator (`condition ? trueExpression : falseExpression`)
     - Allows rendering different content based on a condition.
  2. Logical && Operator
     - The logical `&&` operator (`condition && trueExpression`)
     - Renders content only if the condition is `true`.

```jsx
// Condition Expressions
const isLoggedIn = true;
return (
  <div>
    // way 1 : use of Ternary Operator
    {isLoggedIn ? <WelcomeComponent /> : <LoginComponent />}
    // way 2 : use of Logical && Operator
    {isLoading && <LoadingComponent />}
  </div>
);
```

- **Benefits**:
  - **Conciseness**: Inline conditionals reduce code verbosity, enhancing readability.
  - **Readability**: Simplifies JSX, particularly for straightforward conditional rendering.
- **Use Cases**:
  - **Conditional Rendering**: Renders components based on dynamic conditions like user authentication.
  - **Optional UI Elements**: Hides/shows UI components for an improved user experience.

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

> what is the `useEffect ?`

- **Side Effect**
  - Is a React hook that lets you perform side effects in your function components.
  - Side effects are any operations that can potentially change the state of the world outside of the component, such as making HTTP requests, setting timeouts, or updating the DOM
- **Render**
  - That called after the component has rendered and its DOM nodes have been updated.
- **Argument** - Function - A function that contains the side effects you want to perform. - Array  
   - An array of dependencies. - The dependencies are used to determine whether the effect should be re-run
- **External System**
  - Lets you synchronize a component with an external system.
- **Use**
  - It is important to understand how to use `useEffect` correctly to avoid creating performance problems or memory leaks.

```jsx
import React, { useState, useEffect } from "react";

function App() {
  const [users, setUsers] = useState([]);

  useEffect(() => {
    fetch("https://api.github.com/users")
      .then((response) => response.json())
      .then((data) => setUsers(data));
  }, []);

  return (
    <ul>
      {users.map((user) => (
        <li key={user.id}>{user.name}</li>
      ))}
    </ul>
  );
}
```

> What is Usage of useEffect ?

- **Make HTTP requests**
  - Fetch data from an API
  - Update the state of the component based on the response
- **Set timeouts**
  - Trigger a function after a certain amount of time
  - Create animations or other effects
- **Update the DOM**
  - Add, remove, or modify elements in the DOM
  - Change the CSS of elements
- **Subscribe to events**
  - Listen for events such as clicks, mouse moves, and keyboard presses
  - Update the state of the component based on the events
- **Clean up any side effects that you created**

  - Unsubscribe from events
  - Cancel timeouts
  - Remove elements from the DOM

- **Making Http Request**

```jsx
import React, { useState, useEffect } from "react";

function App() {
  const [users, setUsers] = useState([]);

  useEffect(() => {
    fetch("https://api.github.com/users")
      .then((response) => response.json())
      .then((data) => setUsers(data));
  }, []);

  return (
    <ul>
      {users.map((user) => (
        <li key={user.id}>{user.name}</li>
      ))}
    </ul>
  );
}
```

- **Set Timeout**

```jsx
import React, { useEffect } from "react";

function App() {
  useEffect(() => {
    setTimeout(() => {
      // Do something after 5 seconds.
    }, 5000);
  }, []);

  return (
    <div>
      <h1>This will be rendered after 5 seconds.</h1>
    </div>
  );
}
```

- **Update Dom**

```jsx
import React, { useEffect } from "react";

function App() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    document.title = `Count: ${count}`;
  }, [count]);

  return (
    <div>
      <h1>Count: {count}</h1>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

- **Subscribe to Event**

```jsx
import React, { useEffect } from "react";

function App() {
  const [isOnline, setIsOnline] = useState(false);

  useEffect(() => {
    window.addEventListener("online", () => setIsOnline(true));
    window.addEventListener("offline", () => setIsOnline(false));

    return () => {
      window.removeEventListener("online", () => setIsOnline(true));
      window.removeEventListener("offline", () => setIsOnline(false));
    };
  }, []);

  return (
    <div>
      <h1>Is online: {isOnline}</h1>
    </div>
  );
}
```

- **Clean Up SideEffect**

```jsx
useEffect(() => {
  window.addEventListener("online", () => setIsOnline(true));
  window.addEventListener("offline", () => setIsOnline(false));

  return () => {
    window.removeEventListener("online", () => setIsOnline(true));
    window.removeEventListener("offline", () => setIsOnline(false));
  };
}, []);
```

### UseLayoutEffect

> What is the `useLayoutEffect`

- **UseEffect**
  - Is a version of useEffect that fires before the browser repaints the screen.
  - It hurt performance. Prefer useEffect when possible.
- **Synchronously**
  - It Run Synchronously after all DOM mutations have been committed
  - This means that the effect will be run before the browser has a chance to repaint the screen.
- **Immediate DOM Update**
  - Is useful for tasks that require immediate DOM layout update , such as measuring the size of a element or positioning an element relative to another element
- **Block Browser**
  - It is important to note that It can block the browser from repainting the screen.
  - It can lead to performance problems, especially on mobile devices.

> what is the use case of `useLayoutEffect` ?

- **Measuring size**
  - Get the height and width of an element before or after it is rendered.
- **Positioning**
  - Position a navigation bar relative to the top of the page.
- **Animating**
  - Animate the width of a progress bar as it fills up.
- **Scrolling**

  - Scroll a list element to the top when a new item is added.

- Measuring Size Element

```jsx
import React, { useState, useLayoutEffect } from "react";

function App() {
  const [width, setWidth] = useState(0);
  const [height, setHeight] = useState(0);

  useLayoutEffect(() => {
    const element = document.querySelector("#element");
    setWidth(element.clientWidth);
    setHeight(element.clientHeight);
  }, []);

  return (
    <div>
      <div id="element">This is the element.</div>
      <p>Width: {width}px</p>
      <p>Height: {height}px</p>
    </div>
  );
}
```

- Positioning an element relative to another element:

```jsx
import React, { useState, useLayoutEffect } from "react";

function App() {
  const [tooltipPosition, setTooltipPosition] = useState({ top: 0, left: 0 });

  useLayoutEffect(() => {
    const tooltipElement = document.querySelector("#tooltip");
    const targetElement = document.querySelector("#target");

    if (tooltipElement && targetElement) {
      const tooltipRect = tooltipElement.getBoundingClientRect();
      const targetRect = targetElement.getBoundingClientRect();

      setTooltipPosition({
        top: targetRect.top + targetRect.height,
        left: targetRect.left + targetRect.width / 2 - tooltipRect.width / 2,
      });
    }
  }, [tooltipPosition]);

  return (
    <div>
      <div id="target">This is the target element.</div>
      <div
        id="tooltip"
        style={{ position: "absolute", top: tooltipPosition.top, left: tooltipPosition.left }}
      >
        This is the tooltip.
      </div>
    </div>
  );
}
```

- Animating an element:

```jsx
import React, { useState, useLayoutEffect } from "react";

function App() {
  const [progress, setProgress] = useState(0);

  useLayoutEffect(() => {
    const progressBar = document.querySelector("#progress-bar");

    progressBar.style.width = `${progress}%`;
  }, [progress]);

  return (
    <div>
      <div
        id="progress-bar"
        style={{ width: `${progress}%`, height: "10px", backgroundColor: "red" }}
      ></div>
    </div>
  );
}
```

- Scrolling an element to a specific position:

```jsx
import React, { useState, useLayoutEffect } from "react";

function App() {
  const [list, setList] = useState(["Item 1", "Item 2", "Item 3"]);
  const [selectedIndex, setSelectedIndex] = useState(0);

  useLayoutEffect(() => {
    const listElement = document.querySelector("#list");

    listElement.scrollTop = selectedIndex * listElement.scrollHeight;
  }, [selectedIndex]);

  return (
    <div>
      <ul id="list">
        {list.map((item, index) => (
          <li key={index}>{item}</li>
        ))}
      </ul>
    </div>
  );
}
```

> What is Difference between `useEffect` and `useLayoutEffect` ?

- **When it Runs:**
  - **useEffect**:
    - Asynchronously after DOM mutations are committed.
    - Suitable for tasks not requiring immediate layout calculations.
  - **useLayoutEffect**:
    - Synchronously after DOM mutations are committed.
    - Ideal for immediate layout-sensitive tasks.
- **DOM Update:**
  - **useEffect**:
    - For side effects without immediate DOM layout needs.
  - **useLayoutEffect**:
    - For side effects needing immediate DOM layout updates.
- **Performance Impact:**
  - **useEffect**:
    - Lower impact, optimizing browser rendering.
  - **useLayoutEffect**:
    - Executes synchronously, potentially blocking rendering.
- **Use Case:**
  - **useEffect**:
    - Suits non-layout-dependent tasks like data fetching or timers.
  - **useLayoutEffect**:
    - For layout-sensitive tasks, such as accurate DOM measurements.
- **Recommendation:**
  - **useEffect**:
    - Prefer when synchronous rendering isn't critical.
  - **useLayoutEffect**:
    - Use for tasks requiring synchronous layout calculations.

| Aspect                 | **useEffect**                            | **useLayoutEffect**                         |
| ---------------------- | ---------------------------------------- | ------------------------------------------- |
| **When it Runs**       | Asynchronously after DOM mutations       | Synchronously after DOM mutations           |
| **DOM Update**         | For non-immediate DOM layout needs       | For immediate DOM layout updates            |
| **Performance Impact** | Lower impact, doesn't block rendering    | Higher impact, can block rendering          |
| **Use Case**           | Data fetching, timers, non-layout tasks  | Accurate DOM measurements, layout-sensitive |
| **Recommendation**     | When synchronous rendering isn't crucial | For tasks requiring synchronous layout      |

### UseMemo

> what is the `UseMemo` ?

- **Cache Result**
  - Cache the result of a calculation between re-renders
  - Returns the cached result when the inputs to the function have not changed.
- **Memorize Component**
  - That is used for memoization in functional components.
  - Memoize a value (usually a computed value) so that it is not re-computed on every render
- **Help Performance**
  - Optimize the performance of your application by memoizing the result of expensive function calls and preventing unnecessary re-computations.
- **Expensive Calculations**
  - It's particularly useful for avoiding expensive calculations or computations that involve heavy processing.

> What is Usage `useMemo` ?

- **Optimizing Computations**
  - memoize expensive calculations or functions, preventing unnecessary re-execution.
- **Derived Data**
  - Memoize data derived from props or state, ensuring it's recalculated only when dependencies change.
- **Preventing Unnecessary Renders**
  - Memoize values used in rendering logic, avoiding unnecessary component re-renders.
- **Callback Functions**
  - Memoize callback functions to prevent re-creation, especially when passed as props.
- **API Calls:**
  - Memoize functions making API calls, preventing redundant requests on re-renders.
- **Component Instances**
  - Memoize components to prevent re-rendering unless dependencies change, optimizing complex components.

> what is benefit of `useMemo` ?

- **Performance Optimization:**
  - `useMemo` optimizes performance by caching expensive calculations.
  - It ensures that these calculations are only executed when their dependencies change, preventing unnecessary and costly computations.
- **Avoiding Unnecessary Renders:**
  - By memoizing values, `useMemo` prevents unnecessary component re-renders.
  - When values remain unchanged, React skips rendering, improving the efficiency of the application and providing a more responsive user experience.

### UseCallBack

> What is the `useCallBack`

- **Cache Function**
  - A React Hook that lets you cache a function definition between re-renders.
- **Return Memorized Function**
  - It returns a memoized callback functions .
  - This means that the function will only be recreated if one of its dependencies changes
- **Preventing Unnecessary re-renders**
  - This can be useful for preventing unnecessary re-renders of components

> What is the usage of `useCallBack` hook ?

- **Caching Functions:**
  - When caching functions , ensuring consistent references across re-renders.
- **Optimizing Performance:**
  - Optimizes rendering performance, especially when functions are passed to child components.
- **Preventing Unnecessary Re-renders:**
  - Prevents unnecessary re-renders of child components by stabilizing function references.
- **Preventing Excessive `useEffect` Calls:**
  - Functions used inside `useEffect` can be wrapped with `useCallback`
  - For prevent the effect from firing too often due to function reference changes.
  - This is particularly useful when functions are used as dependencies inside effects.
- **Optimizing Custom Hooks:**
  - In custom Hooks, it's recommended to wrap functions returned by this Hook
  - This allows to optimize their code by memoizing the functions if needed.

> What is the difference between `useMemo` and `useCallBack` ?

- **Similarities**

  - **Optimize Performance**
    - react hook that can be used to optimize the performance by memorizing values of functions
  - **Function , Array**
    - Accept a function and an array of dependencies as arguments, but return different things.

- **Differences**
  - **Return**
    - **useMemo**
      - memorized value
    - **useCallBack**
      - memorized callBack function
  - **Use Case**
    - **useMemo**
      - Caching expensive calculations or objects
    - **useCallBack**
      - preventing unnecessary re-renders when passing callback functions

| Feature   | useMemo                                   | useCallback                                                       |
| --------- | ----------------------------------------- | ----------------------------------------------------------------- |
| Returns   | Memoized value                            | Memoized callback function                                        |
| Use cases | Caching expensive calculations or objects | Preventing unnecessary re-renders when passing callback functions |

```js
import React, { useMemo, useCallback } from "react";

const MyComponent = () => {
  const [selectedNum, setSelectedNum] = useState(100);

  const expensiveCalculation = useMemo(() => {
    // Perform an expensive calculation here
    return result;
  }, [selectedNum]);

  const handleClick = useCallback(() => {
    // Do something with the expensive calculation here
  }, [expensiveCalculation]);

  return (
    <div>
      <p>The result of the expensive calculation is: {expensiveCalculation}</p>
      <button onClick={handleClick}>Click me!</button>
    </div>
  );
};
```

### UseRef

> What is the `useRef` hook ?

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

### UseContext

> What is the `useContext` ?

- **Definition**
  - **Hooks**
    - is a React Hook that lets you read and subscribe to context from your component.
    - that allows functional components to access the context values provided by a nearest `Context.Provider` component in the component tree above them.
  - **Simplifies**
    - It simplifies the process of consuming context values without the need for a `Context.Consumer` component.
- **Benefits**
  - **Simplified Context Consumption:**
    - Simplifies the process of consuming context values, making the code more concise and readable
  - **Functional Component Integration:**
    - It seamlessly integrates with functional components, enabling developers to leverage the power of hooks for managing context data within the component.

```javascript
import React, { useContext } from "react";

// Context creation
const MyContext = React.createContext();

// Provider component
const MyProvider = ({ children }) => {
  const contextValue = "Hello from Context!";
  return <MyContext.Provider value={contextValue}>{children}</MyContext.Provider>;
};

// Functional component consuming context
const MyComponent = () => {
  const contextData = useContext(MyContext);
  return <div>{contextData}</div>;
};

// App usage
function App() {
  return (
    <MyProvider>
      <MyComponent />
    </MyProvider>
  );
}
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

> Why should not use index as key in React ?

- **Bad performance:**
  - When use index , React re-render the entire list even if only a single item in the list changes.
  - React cannot track which items in the list have changed if the keys are just indices.
- **Unstable keys:**
  - The index of an item in a list can change if you add or remove items from the list.
  - This can cause React to re-render the wrong items, which can lead to unexpected behavior.
- **Difficult to debug:**
  - If you are using index as key, it can be difficult to debug why React is re-rendering certain items.
  - Index of an item in a list can change, so you cannot simply look at the key to determine which item is being re-rendered.

> When can use index and unique as key in react ?

|            | **Index Key**         | **Unique Key**    |
| ---------- | --------------------- | ----------------- |
| **Static** | For static data.      | For dynamic data. |
| **Order**  | Order doesn't matter. | Order-sensitive.  |
| **ID**     | No unique IDs.        | Unique IDs.       |

- **Index Key**
  - **Static Data:**
    - Used when the data is static and does not change.
  - **Order Independence:**
    - when the order of items does not matter, and operations like filtering are not happened
  - **ID Absence:**
    - Appropriate when there is no unique identifier (ID) available for each item in the list.
- **Unique Key**
  - **Dynamic Data:**
    - When the data is dynamic and may change.
  - **Order Sensitivity:**
    - When operations like sorting, filtering, removing, or adding items are expected.
  - **ID Availability:**
    - When there is a unique identifier for each item in the list.

## Event

> What is the difference between HTML and React event handling ?

- **Basic**
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
  - **HTML**: use `return false;`
  - **React**: use `e.preventDefault()`

```html
<!-- HTML -->
<a href="#" onclick="handleClick();">Click Me</a>

<script>
  function handleClick() {
    console.log("The link was clicked");
    return false;  👈
  }
</script>
```

```jsx
// React
const MyComponent = () => {
  const handleClick = (e) => {
    e.preventDefault(); 👈
    console.log("The link was clicked");
  };

  return (
    <a href="#" onClick={handleClick}>
      Click Me
    </a>
  );
};
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
   - React _creates_ a Virtual DOM (VDOM) when a component is _rendered_.
2. **Differential Comparison**:
   - When a component's state or props _change_, React generates a _new_ VDOM representation.
   - For Identify _Differences_ compares it with the previous VDOM using a diffing _algorithm_
3. **Efficient DOM Updates**:
   - React updates only the _specific_ parts of the real DOM that have changed, minimizing _manipulations_.
   - This targeted approach significantly enhances application _performance_.

> what is the reconciliation ?

- **Definition**
  - **Updating**
    - React's reconciliation algorithm compares new and previous virtual DOM trees, updating only necessary parts in the actual DOM
  - **Re-render**
    - Minimizes unnecessary re-renders, optimizing overall application performance.
- **Benefits**
  - **Efficiency**
    - Reduces unnecessary DOM manipulations, enhancing application responsiveness.
  - **Performance**
    - Efficiently identifies DOM elements to update based on component state or props changes, ensuring optimal rendering performance
  - **User Experience**
    - Optimizes rendering process, ensuring smooth user experience and improved responsiveness.

### Different

> What is difference between Virtual and Real DOM ?

- **Definition:**
  - **Real**
    - Actual representation of the web page's structure in the browser's memory.
  - **Virtual**
    - Lightweight copy of the web page structure implemented in JavaScript as a tree.
- **Manipulation:**
  - **Real:**
    - Expensive manipulation operations.
  - **Virtual:**
    - Efficient and easy manipulation.
- **Memory:**
  - **Real:**
    - Results in significant memory wastage.
  - **Virtual:**
    - Minimizes memory wastage.
- **Element Updates:**
  - **Real:**
    - Creates new elements if an update is required.
  - **Virtual:**
    - Updates elements in the tree structure if changes occur.
- **HTML:**
  - **Real:**
    - Allows direct HTML updates.
  - **Virtual:**
    - Doesn't allow direct HTML updates.

| **Aspect**       | **Real**                                     | **Virtual**                                 |
| ---------------- | -------------------------------------------- | ------------------------------------------- |
| **Definition**   | Actual representation of web page in memory. | Lightweight copy of web page in JavaScript. |
| **Manipulation** | Expensive manipulation operations.           | Efficient and easy manipulation.            |
| **Memory**       | Results in significant memory wastage.       | Minimizes memory wastage.                   |
| **Element **     | Creates a new DOM if element updates         | Updates the JSX if element updates.         |
| **HTML**         | Allows direct HTML updates.                  | Doesn't allow direct HTML updates.          |

## Context

> What is Context ?

- **Share Data**
  - It enables components to share state or methods with their children, even if they are not directly related.
- **Sharing Without Passing**
  - a feature that allows data to be passed through the component tree without explicitly passing props down at every level.

> How use of `Context` In React ?

- **Step**
  - **Create a Context.**
    - Create a Context using the `createContext()` function.
    - This takes the initial value of the Context as a parameter and returns the Context created.
  - **Provide the Context.**
    - Wrap your root component with the `Provider` component,
    - With this Component passing the context value as a prop
  - **Consume the Context.**
    - Consume the context in any descendant component using the `useContext()` hook.

```jsx
// Stp 1 : Create a context for the current theme.
const ThemeContext = createContext({ theme: "light" });

// Stp 2 : Create a provider component that provides the context value.
const ThemeProvider = ({ children }) => {
  const [theme, setTheme] = useState("light");

  return <ThemeContext.Provider value={theme}>{children}</ThemeContext.Provider>;
};

// Stp 3 : Create a consumer component that consumes the context value.
const ThemeConsumer = ({ children }) => {
  const theme = useContext(ThemeContext);

  return <div style={{ backgroundColor: theme }}>{children}</div>;
};

// Stp 4 : Render the app.
function App() {
  return (
    <ThemeProvider>
      <ThemeConsumer>
        <h1>Hello, world!</h1>
      </ThemeConsumer>
    </ThemeProvider>
  );
}
```

> What is the Usage Context ?

- **Theme and User Authentication:**
  - Context is often used for providing themes or user authentication status across the application without the need to pass this information through props at each level.
- **Language Preferences:**
  - Language preferences, such as localization settings, can be managed using context to ensure consistent language usage across various components.
- **Application State Management:**
  - Context can be employed for managing global application state, making it accessible to multiple components without the complexity of prop drilling.

> what are the benefit `Context` ?

- **Simplified Data Sharing:**
  - Context simplifies the process of sharing data between components, especially when dealing with deeply nested components or components that are not directly related.
- **Reduced Prop Drilling:**
  - It helps eliminate prop drilling by providing a direct way to access context data without passing it through intermediate components.
- **Cleaner Component Hierarchy:**
  - Context promotes a cleaner and more organized component hierarchy by decoupling the data-sharing logic from the components themselves.

## Redux

### Introduce

> What is Redux?

- **Design Pattern**
  - A predictable state container for JavaScript apps based on the _Flux design pattern_.
- **Behave Consistent**
  - It helps you write applications that behave consistently, run in different environments (client, server, and native), and are easy to test.
- **Manage State**
  - An open-source JavaScript library for managing the state of an application.
- **Size / Dependency**
  - It is tiny (about 2kB) and has no dependencies.
- **Common Library**
  - It is commonly used with libraries/frameworks like React for building user interfaces.

> What is the Core of `Redux` ?

- **Store:**
  - **Object**
    - Redux stores the _state_ of the entire application in a single JavaScript object.
- **Actions:**
  - **Object**
    - Actions are plain JavaScript objects that describe what happened in the application.
  - **Information**
    - They are the only source of **information** for the store.
  - **Type**
    - Actions must have a type property that indicates the type of action being performed.
  - **Payload**
    - Actions can also have additional data called the **payload**.
- **Reducers:**
  - **Pure function**
    - Reducers are pure functions that specify how the application's state changes in response to actions sent to the store.
  - **Previous/New State**
    - Reducers take the previous state and an action as arguments and return the **new** state.
    - They should not modify the previous state directly but return a new state object.
- **Dispatch:**
  - **Method**
    - Dispatch is a method used to send actions to the Redux store.
  - **Update**
    - When an action is dispatched, the store's reducer function is called, and the state is updated based on the action.
- **Selectors:**
  - **Function**
    - Selectors are functions that extract specific pieces of data from the store state.
  - **Shape**
    - They are used to encapsulate the shape of the state and are helpful to avoid accessing the state shape directly from components.

> what are the Benefits of `Redux` ?

- **Predictable State Management:**
  - Redux provides a predictable state container, making it easier to understand how data changes in the application over time.
- **Centralized State:**
  - By storing the application state in a single store, it becomes easier to manage and debug the application's data.
- **Time-Travel Debugging:**
  - Redux allows developers to trace state changes over time, enabling powerful debugging capabilities.
- **Middleware Support:**
  - Redux middleware can be used to perform tasks like logging actions, making asynchronous requests, etc., before they reach the reducer.

> When to use Redux ?

- **Manage State**
  - Redux is beneficial for complex applications where managing state across multiple components becomes challenging.
- **Not Directly**
  - It's particularly useful when there is a need to share state between multiple components that are not directly connected in the component tree.
- **Complex App**
  - Redux is not necessary for all applications and might introduce unnecessary complexity in simpler projects.
  - Consider using local component state in simpler cases.

### Differenct

> What is the difference between React context and React Redux?

- **Similarities**

  - React context and React Redux are two different ways to manage state in React applications.

- **Features**
  - **Context:**
    - Built-in feature in React
  - **Redux:**
    - Third-party library
- **Performance:**
  - **Context:**
    - May lead to unnecessary re-renders in larger component trees
  - **Redux:**
    - Optimized for efficient re-renders, enhancing overall performance
- **Debugging and DevTools:**
  - **Context:**
    - Limited debugging capabilities, basic inspection of component state
  - **Redux:**
    - Offers powerful tools like time-travel debugging for tracing state changes
- **Middleware Support:**
  - **Context:**
    - Lacks middleware support for handling asynchronous actions
  - **Redux:**
    - Supports middleware, enabling advanced tasks like logging and API calls
- **Use Cases:**
  - **Context:**
    - Sharing state in closely related or shallowly nested components
    - Small-scale applications where simplicity is paramount
  - **Redux:**
    - Large-scale applications with complex state management needs
    - Projects demanding predictability, centralized state, and advanced debugging

| Feature                       | React context | React Redux         |
| ----------------------------- | ------------- | ------------------- |
| **State management paradigm** | Built-in      | Third-party library |
| **Predictable state**         | No            | Yes                 |
| **Centralized state**         | No            | Yes                 |
| **Time-travel debugging**     | No            | Yes                 |
| **Middleware support**        | No            | Yes                 |
| **Complexity**                | Simpler       | More complex        |

### Dispatch

> Can I dispatch an action in reducer?

- **Anti Pattern**
  - Dispatching an action within a reducer is an **anti-pattern**.
- **State Object**
  - Your reducer should be _without side effects_, simply digesting the action payload and returning a new state object.
- **Side Effect**
  - Adding listeners and dispatching actions within the reducer can lead to chained actions and other side effects.

> What is tips for avoiding dispatching actions in reducers ?

- **Use middleware:**
  - Middleware can be used to perform side effects before or after actions are dispatched to the reducer.
  - For example, middleware can be used to log actions, make asynchronous requests, or update the user interface.
- **Move logic to components:**
  - If you need to perform side effects in response to an action, consider moving the logic to a component.
  - This will help to keep the reducer pure and predictable.
- **Use selectors:**
  - Selectors are functions that can be used to extract specific pieces of data from the store state.
  - Selectors can be used to avoid dispatching actions unnecessarily.

### Action

### Store

> How to access Redux store outside a component?

1. **Using the `useSelector` hook:**
   - `useSelector` hook allows you to access the Redux store state from anywhere in your application

```js
import { useSelector } from "react-redux";

const MyFunction = () => {
  const count = useSelector((state) => state.count);

  // Do something with the count variable
};
```

2. **Using the `store` object:**
   - You can also access the Redux store state directly using the `store` object.

```js
import { store } from "./store";

const MyFunction = () => {
  const count = store.getState().count;

  // Do something with the count variable
};
```

- Examples use outside a component :
  - Perform an **asynchronous operation**, such as making an **HTTP** request.
  - **Update** the state of the application based on a user interaction, such as a click **event**.
  - **Log** the state of the application for debugging purposes.

### Reducer

## Library

### Intl

> What is the `React Intl`

- **Definition**
  - **Internationalization**
    - Is a Library for Internationalization in React applications
  - **Component / APIs**
    - It Provides a set of Component and APIs to format dates , numbers and string , as well as pluralization and translations
- **Key Features**
  - **Formatting**
    - Formats dates and numbers based on specified locales and rules for cultural appropriateness.
  - **Pluralization**
    - Handles message variations based on item count (zero, one, or multiple items).
  - **Translations Management**
    - Defines and manages translation messages, enabling seamless language switching.
  - **Context-Based Formatting**
    - Utilizes `IntlProvider` context for consistent formatting.

### Router

> What is React Router?

- **Definition:**
  - **Navigation / Routing:**
    - Library for managing navigation and routing in React applications.
  - **SPAs:**
    - Enables the creation of Single-Page Applications (SPAs) by handling browser history and rendering components based on the URL.
- **Usage:**
  - **Dynamic UIs:**
    - create dynamic user interfaces where components change based on the URL
  - **Complex Applications:**
    - Ideal for complex applications with multiple views and nested components, simplifying the management of various UI states.
  - **Mobile Apps:**
    - Utilized in mobile applications built with React Native, ensuring seamless navigation between screens.
- **Benefits:**
  - **Improved User Experience:**
    - Provides a smooth navigation experience, reducing page reloads and enhancing interactivity in SPAs.
  - **Enhanced SEO:**
    - Enables server-side rendering, improving search engine optimization by ensuring that search engines can crawl the application's content.
  - **State Preservation:**
    - Maintains UI state during navigation, ensuring that users don't lose their data or context when moving between different views.
  - **Community and Support:**
    - Being a widely adopted library, React Router benefits from a large community, ensuring continuous support, updates, and a wealth of resources.

### Flux

> what is `Flux` ?

- **Design Paradigm**
  - An application design paradigm use as replacement for the more traditional MVC pattern
- **Unidirectional DataFlow**
  - That uses _unidirectional_ data flow to improve the predictability and maintainability
- **Framework / Library**
  - Is not a framework or a library but a new kind of architecture that complement react and the concept of unidirectional data flow
  - Although Flux is a design pattern and not tied to any specific library, there are several libraries available that implement the Flux architecture like : fluxxor , flux and etc.
  - In React 15 , before use of redux library , use of library such as flux
- **React**
  - Facebook uses this pattern internally when working with React

> How `Flux` work ?

- **Include**

  - **Store:**
    - The store is a single object that contains all of the application's state.
  - **Actions:**
    - Actions are objects that represent changes to the state of the application.
  - **Dispatcher:**
    - The dispatcher is responsible for dispatching actions to the store.
  - **Views:**
    - Views are responsible for rendering the UI of the application.
    - They subscribe to the store for changes to the state, and they re-render when the state changes.

- **Steps:**

1. A view dispatches an action to the dispatcher.
2. The dispatcher dispatches the action to the store.
3. The store updates the state and notifies all of the subscribed views.
4. The views re-render to reflect the new state.

- **Example:**

1. The user clicks a button to increment a counter.
2. The button view dispatches an `INCREMENT_COUNTER` action to the dispatcher.
3. The dispatcher dispatches the `INCREMENT_COUNTER` action to the store.
4. The store updates the counter state and notifies all of the subscribed views.
5. The counter view re-renders to reflect the new counter state.

## Test

### Jest

> what is `Jest` ?

- **Facebook**
  - Jest is popular javascript testing framework maintained by Facebook
- **JavaScript**
  - A JavaScript testing framework designed to ensure the correctness of any JavaScript codebase.
- **Popular**
  - Used by many JavaScript libraries and frameworks, including React, Angular, Vue, and Node.js.
- **Serverless**
  - It is also a popular choice for testing serverless applications and cloud functions.
- **Benefit**
  - **Speed:**
    - Is very fast, thanks to its use of a snapshot testing architecture.
  - **Accuracy:**
    - provides comprehensive and accurate feedback on your tests, including stack traces and diff output.
  - **Ease of use:**
    - Jest is easy to learn and use, even for beginners.
  - **Flexibility:**
    - Test a wide variety of JavaScript code, including unit tests, integration tests, and end-to-end tests.
