## TypeScript

> What is TypeScript ?

- **Definition**
  - **Microsoft**
    - Open-source language developed and maintained by Microsoft.
  - **JavaScript**
    - All JavaScript code is valid TypeScript.
  - **Creation**
    - Developed to overcome JavaScript limitations for large-scale applications at Microsoft.
- **Property**
  - **Static Typing**
    - Introduces static typing, enabling type specification for variables, parameters, and return values.
    - Type annotations enhance clarity and catch type-related errors.
  - **Compilation**
    - Requires compilation to JavaScript before execution.
    - TypeScript compiler (tsc) translates .ts files to .js for compatibility with any JavaScript runtime.

>     What is the Benefit of TypeScript ?

- **Catch Error Development**
  - TypeScript enforces static types, catching errors during development.
- **Early Error Detection:**
  - Errors are caught during development, providing immediate feedback.
- **Code Readability:**
  - Clearer code structure with explicit type information.
- **Improved Code Quality:**
  - Type annotations lead to cleaner, self-documenting code.
- **Reduced Debugging:**
  - Type-related errors caught early, reducing debugging time.
- **Enhanced Tooling:**
  - Robust tooling with autocompletion and intelligent code analysis.
- **Collaboration and Maintainability:**
  - Easier collaboration and maintenance in larger projects.

> What is the different between Javascript and Typescript ?

- **Type System:**
  - **JS:** Dynamically typed, types determined at runtime.
  - **TS:** Statically typed, types checked at compile-time.
- **Error Handling:**
  - **JS:** Errors often discovered at runtime, can lead to unexpected behavior.
  - **TS:** Errors caught during development, providing early feedback and stability.
- **Tooling:**
  - **JS:** Limited tooling support for code analysis and autocompletion.
  - **TS:** Robust tooling support, including autocompletion, type inference, and intelligent code analysis.
- **Development Speed:**
  - **JS:** Faster initial development due to fewer constraints.
  - **TS:** Slightly slower start due to type annotations, but faster debugging and maintenance.
- **Usage:**
  - **JS:** Widely used for front-end and back-end web development.
  - **TS:** Commonly used for large-scale applications, especially where type safety and maintainability
- **Code Readability:**
  - **JS:** Type information not explicitly stated, leading to potential ambiguity.
  - **TS:** Clearer understanding of data structures and function parameters due to type annotations.

| **Aspect**         | **JavaScript**     | **TypeScript**                   |
| ------------------ | ------------------ | -------------------------------- |
| **Type System**    | Dynamic at runtime | Static, checked at compile-time  |
| **Error Handling** | Runtime discovery  | Development-time catching        |
| **Tooling**        | Limited support    | Robust, including autocompletion |
| **Dev Speed**      | Fast development   | Slightly slower due to typing    |
| **Usage**          | Web development    | Large-scale applications         |
| **Readability**    | Less explicit      | Clear with type annotations      |

### Module

> What are the differences between External and Ambient module ?

- **Definition**
  - **External Modules:**
    - Also known as "file modules," each file represents one module.
  - **Ambient Modules:**
    - Defined using the `declare module` syntax.
- **Usage**
  - **External Modules:**
    - Widely used in TypeScript projects.
  - **Ambient Modules:**
    - Provided by library developers or community contributions.
- **Creation**
  - **External Modules:**
    - Created via `import` and `export` keywords in TypeScript files.
    - Automatically generated with new TypeScript files.
  - **Ambient Modules:**
    - Declared in `.d.ts` files.
- **Use Cases**
  - **External Modules:**
    - Organizes related functionalities.
    - Enhances code organization, reuse, and maintainability.
  - **Ambient Modules:**
    - Interfaces TypeScript with existing JavaScript libraries.
    - Facilitates static type checking and IDE autocompletion.
- **Integration**
  - **External Modules:**
    - Seamlessly integrates within TypeScript projects.
    - Supports modular and structured development.
  - **Ambient Modules:**
    - Integrates TypeScript with existing JavaScript libraries.
- **Syntax and Declaration**
  - **External Modules:**
    - Utilizes `import` and `export` keywords.
  - **Ambient Modules:**
    - Utilizes the `declare module` syntax in `.d.ts` files.

| Aspect          | External Modules     | Ambient Modules             |
| --------------- | -------------------- | --------------------------- |
| **Definition**  | One module per file. | Type info for libraries.    |
| **Usage**       | Widely used.         | Provided by devs/community. |
| **Creation**    | `import/export`.     | Declared in `.d.ts` files.  |
| **Use Cases**   | Code organization.   | Interface with JS libs.     |
| **Integration** | Seamless.            | Integrates with JS.         |

### Compile

> Do TypeScript files need compilation ?

- **Yes, TypeScript files need compilation.**
  - TypeScript files need to be compiled into Js before they can be run in a browser or on a server.
  - Browsers and Node.js understand JavaScript, not TypeScript directly.
  - TypeScript code (.ts files) must be compiled into JavaScript (.js files) for execution.
  - Compilation catches type errors and allows for better code optimization.
  - The TypeScript compiler, `tsc`, is used to transpile TypeScript code into JavaScript.

## Type

### Basic

#### Number

> What is the Number type in TS ?

- **Definition:**
  - Represents numeric values, both integers and floating-point numbers, in TypeScript.
- **Usage:**
  - **Numeric Data:**
    - Used to store and manipulate numeric data.
    - Supports whole numbers as well as decimal numbers.
- **Example:**

```typescript
let age: number = 30;
let pi: number = 3.14;
```

#### String

> What is the String type in TS ?

- **Definition:**
  - Represents a sequence of characters or text.
- **Usage:**
  - **Textual Data:**
    - Used to store and manipulate textual data.
    - Commonly used for storing names, addresses, messages, and other forms of text.
- **Example:**
  `typescript
	let username: string = "JohnDoe";
	let message: string = "Hello, TypeScript!";
	`

#### Boolean

> What is the Boolean type in TS ?

- **Definition:**
  - Represents a logical value indicating `true` or `false`.
- **Usage:**
  - **Logical Values:**
    - Used to store and manipulate true/false conditions.
    - Essential for decision-making and conditional statements in programming.
- **Example:**
  ```typescript
  let isActive: boolean = true;
  if (isActive) {
    console.log("The system is active.");
  } else {
    console.log("The system is inactive.");
  }
  ```

#### Array

> What is the Array type in TS ?

- **Definition**
  - Represents a collection of elements of the same type or a union of multiple types.
- **Usage**
  - **Lists of Elements:**
    - Used to store and manipulate lists of items, such as numbers, strings, or custom objects.
- **Example**

```typescript
let numbers: number[] = [1, 2, 3, 4, 5];
let names: string[] = ["Alice", "Bob", "Charlie"];
```

#### Tuple

> What is the Tuple type in TS ?

- **Definition:**
  - Represents an ordered array where the type of a fixed number of elements is known, but need not be the same.
- **Usage:**
  - **Ordered Elements:**
    - Used to create a collection of items where each element has a specific type and a fixed position.
- **Example:**

```typescript
let person: [string, number] = ["Alice", 30];
```

#### Enum

> What is the Enum type in TS ?

- **Definition**
  - A set of named constants representing distinct numeric values.
- **Usage**
  - **Named Constants:**
    - Used to define a collection of related values.
    - Provides a way to represent a group of numeric or string values in a more readable and self-documenting way.
- **Example**

```ts
enum Direction {
  Up = "UP",
  Down = "DOWN",
  Left = "LEFT",
  Right = "RIGHT",
}
```

#### Void

> What is the void type in TS ?

- **Definition**
  - **Absence Any Type**
    - Represents the absence of any type
- **Usage**

  - **Don't Return In Function**
    - Commonly used as the return type for functions that do not return a value.

- **Example**

```ts
function logMessage(message: string): void {
  console.log(message);
}
```

#### Never

> What is the void type in TS ?

- **Definition**
  - **Absence Any Type**
    - Represents values that never occur
- **Usage**
  - **No Return Value:**
    - Commonly employed as the return type for functions that do not yield a value.
    - Can be used for functions that always throw errors or enter infinite loops.
- **Example**

```ts
function throwError(message: string): void {
  throw new Error(message);
}
```

#### Unknown

> What is the Unknow in TS ?

- **Definition:**
  - It represents a value whose type is not known at compile time.
- **Usage:**
  - **Dynamic Data:**
    - Used when the type of a variable is not known in advance, such as values obtained from user input or third-party APIs.
    - Requires type checking or assertions before performing operations on variables of type `unknown`.
- **Example:**

```typescript
let userInput: unknown = getUserInput(); // Obtaining user input, type is unknown

if (typeof userInput === "string") {
  // Type narrowing through type checking
  let length: number = userInput.length; // Valid, as userInput is now known to be a string
}

let stringValue: string = userInput as string; // Type assertion to assign unknown to a string
```

#### Null

> What is the Null type in TS ?

- **Definition:**
  - Represents a reference that doesn't point to any object.
- **Usage:**
  - **Null Value:**
    - Used to indicate the absence of a value or a null object reference.
    - Often used in scenarios where a value is intentionally missing or not applicable.
- **Example:**

```typescript
let data: string | null = null;
```

#### Undefined

> What is the Undefined type in TS ?

- **Definition:**
  - Represents a variable that has been declared but hasn't been assigned a value yet.
- **Usage:**
  - **Default Initial Value:**
    - Used when a variable is declared but not yet assigned a specific value.
    - Commonly seen in scenarios where a variable's value will be determined later.
- **Example:**

```typescript
let data: number | undefined;
```

> How check type null or undefined in ts ?

- **Operators:**
  - Equality ( == and === )
    - Used for direct equality checks.
  - Typeof (`typeof`):
    - Acts as a type guard to narrow down the type.
  - Instanceof (`instanceof`)
    - Checks if an object is an instance of a particular class or constructor function.
  - Optional Chaining (`?.`)
    - Safely accesses nested properties, handling `null` or `undefined` values.
  - Non-null Assertion (`!`)
    - Asserts that a value is non-null or non-undefined.

```js
// Equality Operator
if (variable == null) {
  // variable is either null or undefined
}

// Typeof Operator
if (typeof variable === 'undefined' || variable === null) {
  // variable is either null or undefined
}

// Instanceof Operator
if (variable instanceof Object && variable === null) {
  // variable is null
}

// Optional Chaining Operator
if (variable?.property?.nestedProperty === null) {
  // variable or property or nestedProperty is null or undefined
}


// Non-null Assertion
function doSomething(variable: string | null | undefined) {
  const length: number = variable!.length;
  // Here, you assert that variable is non-null and non-undefined
}
```

### Advanced

#### Generic

> What is the Generic Type ?

- **Definition**
  - Represents a type that can work with multiple data types without specifying a concrete type beforehand.
- **Usage**
  - **Flexible Data Structures:**
    - Used to create functions, classes, or interfaces that work with different data types.
    - Enables type safety while providing flexibility in handling various data structures.
- **Example**

```typescript
function identity<T>(arg: T): T {
  return arg;
}

let output: number = identity(42);
let name: string = identity("Alice");
```

#### Union

> What is the Union Type in TS ?

- **Definition:**
  - Represents a type that can hold values of multiple specified types.
- **Usage:**
  - **Combining Types:**
    - Used to define a variable or parameter that can accept values of more than one data type.
    - Enables flexibility when a value can be of different types at different points in the program.
- **Example:**

```typescript
let result: number | string;
result = 42; // Valid, as `result` can hold numbers
result = "hello"; // Valid, as `result` can also hold strings
```

#### Discriminated Unions

> What is the Discriminated Unions type in TS ?

- **Definition:**
  - Represents a composite type where each object discriminates between different possible types using a common property.
- **Usage:**
  - **Discriminating Property:**
    - Used to define a shared property, often called a discriminant, that determines the specific type of an object within the union.
    - Enables precise type checking and narrowing down the possible types based on the discriminant property's value.
- **Example:**

```typescript
interface Square {
  kind: "square";
  size: number;
}

interface Circle {
  kind: "circle";
  radius: number;
}

type Shape = Square | Circle;

function area(shape: Shape): number {
  switch (shape.kind) {
    case "square":
      return shape.size * shape.size;
    case "circle":
      return Math.PI * shape.radius * shape.radius;
  }
  return 0; // Default case for exhaustive checks
}
```

#### Intersection

> What is the Intersection type in TS ?

- **Definition:**
  - Represents a type formed by combining multiple types, creating a new type that has all the properties and methods of the intersected types.
- **Usage:**
  - **Combining Types:**
    - Used to create a new type that includes common properties and methods from multiple existing types.
    - Enables composing complex types from simpler ones, ensuring that the resulting type has all the features of its constituents.
- **Example:**

```typescript
interface Car {
  brand: string;
  speed: number;
}

interface Electric {
  batteryLife: number;
}

type ElectricCar = Car & Electric;
let myCar: ElectricCar = {
  brand: "Tesla",
  speed: 120,
  batteryLife: 300,
};
```

#### Type Guards

> What is the Type Guards in TS ?

- **Definition:**
  - Type guards are expressions or functions that TypeScript uses to narrow down the type of a variable within a specific block of code.
- **Usage:**
  - **Narrowing Types:**
    - Used to perform runtime checks to determine if a variable is of a specific type.
    - Enables TypeScript to infer and narrow down the type of a variable within conditional blocks, ensuring type safety.
- **Example:**

```typescript
function isNumber(value: any): value is number {
  return typeof value === "number";
}

let result: any = 42;

if (isNumber(result)) {
  // Inside this block, 'result' is narrowed down to type 'number'
  console.log(result.toFixed(2));
} else {
  console.log("Not a number");
}
```

#### Interface

> What is the Type Interface in TS ?

- **Definition:**
  - A way to define a contract in your code. It defines the structure that an object must adhere to.
- **Usage:**
  - **Blueprint for Objects:**
    - Used to define the shape of an object, specifying the properties and their types.
    - Provides a clear and descriptive way to establish the structure of objects.
- **Example:**

```typescript
interface Person {
  firstName: string;
  lastName: string;
  age: number;
  sayHello: () => void;
}

let person: Person = {
  firstName: "John",
  lastName: "Doe",
  age: 30,
  sayHello: function () {
    console.log("Hello!");
  },
};
```

#### Type Aliases

> What is the Type Aliases in Ts ?

- **Definition**
  - Allow developers to create custom names for existing types, making complex types more readable and self-descriptive.
- **Usage**
  - **Custom Type Names:**
    - Used to define a custom name for a specific type or a union of types.
    - Enhances code readability and maintains type information in a more expressive manner.
- **Example**

```typescript
type Point = {
  x: number;
  y: number;
};

type Shape = "circle" | "square" | "triangle";

let origin: Point = { x: 0, y: 0 };
let shapeType: Shape = "circle";
```

#### Type Assertions

> What is the Type Assertions in TS ?

- **Definition:**
  - A way to explicitly specify the type of a value, allowing developers to treat a variable as a different type than what TypeScript's static type checking system infers.
- **Usage:**
  - **Overriding Inference:**
    - Used to assert that a value is of a specific type, overriding TypeScript's type inference.
    - Typically used when developers have more knowledge about the type of a variable than TypeScript can infer.
- **Example:**

```typescript
let value: any = "Hello, TypeScript!";
let length: number = (value as string).length;
```

## JavaScript

### Declaration

> What is the Declaration file in TS ?

- **Definition**
  - **Extension**
    - Declaration file usually with a `.d.ts` extension
  - **Type JavaScript**
    - It provides type information about the types that exist in external JavaScript code.
- **Purpose:**
  - **Type Annotations:**
    - Enables static type checking and autocompletion in TypeScript.
  - **Integration**
    - Integrating TypeScript with external JavaScript libraries, ensuring type safety.

> How Create a Declaration File ?

- **Creation:**
  - **Manual:** Create a `.d.ts` file with type annotations for JavaScript code.
  - **Automatic Tools:** Use tools like `dtslint` or DefinitelyTyped for automated generation.
- **Example:**
  - **Scenario:** Integrating a JavaScript library into a TypeScript project.
  - **Steps:**
    - Create a `.d.ts` file.
    - Define types and structures used in the library.
    - Export necessary types for use in TypeScript files.

## Config

> What is a tsconfig.json file ?

- **Indicate Root file**
  - The presence of this file in the directory implies that it is the TypeScript project root.
- **Specifies Option Required**
  - This file where you may specify several options to inform the compiler how to compile a project.
