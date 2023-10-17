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

- **Static Typing:**
  - TypeScript enforces static types, catching errors during development.
- **Early Error Detection:**
  - Errors are caught during development, providing immediate feedback.
- **Improved Code Quality:**
  - Type annotations lead to cleaner, self-documenting code.
- **Enhanced Tooling:**
  - Robust tooling with autocompletion and intelligent code analysis.
- **Refactoring Support:**
  - Safer refactoring due to clear type annotations.
- **Collaboration and Maintainability:**
  - Easier collaboration and maintenance in larger projects.
- **Code Readability:**
  - Clearer code structure with explicit type information.
- **Reduced Debugging:**
  - Type-related errors caught early, reducing debugging time.

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

## Type

### Basic

#### Number

#### String

#### Boolean

#### Array

#### Tuple

#### Enum

#### Any

#### Void

#### Null and Undefined

#### Never

### Advanced

#### Union

#### Intersection

#### Type Guards

#### Type Aliases

#### Discriminated Unions

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
