## ECMAScript

> What is ECMAScript?

- Standard
  - is standard and language like javascript and ActionScript are designed according to this
- Language
  - Is a scripting language specification used as the foundation for languages like JavaScript
- Core
  - It defines the core features and behavior of languages like Javascript and ActionScript
- Consistency
  - Serves as the engine for various scripting languages, ensuring consistency in their fundamental functionalities.

### ES6

> What features were introduced to JavaScript by ES6 (ECMAScript 2015)?

- **Arrow Functions**
- **Classes**
- **Template Strings (Template Literals)**
- **Enhanced Object Literals**
- **Object Destructuring**
- **Promises**
- **Generators**
- **Modules**
- **Symbol**
- **Proxies**
- **Sets**
- **Default Function Parameters**
- **Rest and Spread Operators**
- **Block-Scoped Variables (`let` and `const`)**

## Strict

> What does `use strict` in javascript ?

- Security
  - Implies a higher lever of security
- Pros

  - It makes us write safer codes with fewer bugs

- Place
  - It use in front of the 'file ' or 'function'

```js
"use strict"; // use in first of file
var x = 3.14;

function myFunction() {
  "use strict"; // use in first of function
  y = 3.14;
}
```

- Error
  - when you assignment withou declaration

```js
"use strict";
x = 3.14; // Error: ReferenceError: assignment to undeclared variable x
myFunction();

function myFunction() {
  y = 3.14; // Error: ReferenceError: assignment to undeclared variable y
}
```

## Scope

> What is the concept of Scope , and what are its types?

- **Definition:**

  - Place
    - Refers to the places where variables are accessible and usable in a program.
  - Access
    - Scope in programming delineates where variables can be accessed and utilized.
  - Variable
    - It defines the visibility and reach of variables within a program, ensuring they are confined to specific parts of the code.

- **Types:**
  - **Global Scope:**
    - Variables declared in the global scope are accessible from **anywhere** in the program, both inside functions and outside them.
  - **Local Scope:**
    - Variables declared inside a **function** have local scope.
    - They are accessible only within that function.
  - **Block Scope:**
    - Introduced in ES6
    - Variables declared with `let` and `const` within a block have **block** scope.
    - They are accessible only within that block.

```js
// Global

// Local
function person() {
  var name = "Michael";
}

// Block
if (true) {
  let name = "Michael";
}
```

## Dom

> What is DOM?

- Stand for
  - Document Object Model
- Object
  - It's an object that includes elements with their own properties and methods

## Hosting

> What is the Hoisting ?

- Move
  - Process where function and variable declarations are moved to the top of their containing scope during the compilation phase.
- Use
  - you can use functions or variables in your code even before they are declared.

```js
// you can use before declared
smile();

function smile() {
  return ":)";
}
```

- Declaration
  - only the declarations are hoisted, not the initializations or assignments.

```js
var name;

console.log(name);

name = "Serena";
```

### Function

### Variable

## Variable

### Definition

> can use of const without assignment to that ?

- NO , due to when you define a constant, you must assign a value to it

```js
const      // Error
```

### Sensitive

> What does "case sensitive" mean in the context of JavaScript programming?

- Letter
  - Refers to distinction between uppercase and lowercase letter in variable , function and other identifiers within the code
- Mindful
  - Developers need to be mindful of case sensitivity while writing JavaScript code to ensure proper variable and function references throughout the program.

## Operator

### Comparison

> What is the Different Between == Equality Operator and ==== Strict Equality Operator ?

- Convert
  - ==
    - It convert the operands to the same type before making the comparison
  - ===
    - Operator does not convert operands. It compares values without type coercion.

```js
console.log(1 == "1"); // true -> 1 converted to '1'
console.log(true == 1); // true -> true converted to 1
console.log(null == undefined); // true -> null is considered equall to undefined

console.log(1 === "1"); // false
console.log(true === 1); // false
console.log(null === undefined); // false
```

- Value + Type
  - ==
    - It only checks the value
  - ===
    - In addition to the value, it also checks the type

```js
console.log(1 == "1"); // ture

console.log(1 === "1"); // flase
```

### And

> How does the logical AND (`&&`) operator work in JavaScript?

- Return
  - False : If any of the expressions being evaluated is false
  - True : If all expressions are true

```js
true && true; // true
true && false; // false
null && true; // null

"Hans" && "Alex" && "Ali"; // "Ali"
true && true && "Ali"; // "Ali"
```

### Or

> How does the logical OR (`||`) operator work in JavaScript?

- Return
  - True : If any of the expressions being evaluated is true
  - False : Only if all expressions are false

```js
true || false; // true
false || false; // false
```

### Double Not

> What does the `!!` operator do?

- **Definition:**
  - The `Double NOT` operator, `!!`, when placed before a value, converts it to a Boolean value.

```javascript
console.log(!!null); // false
console.log(!!undefined); // false
console.log(!!""); // false
console.log(!!0); // false
console.log(!!NaN); // false
console.log(!!" "); // true
console.log(!!{}); // true
console.log(!![]); // true
console.log(!!1); // true
```

### Rest Vs Spread

> what is the different between Rest and Spread Operator ?

- function
  - Rest
    - collect remains element of array or object into a new array
  - Spread
    - spread the elements of an array or object into another array or object.

```js
function sum(...arg) {
  console.log(arg); // [1 , 2 , 3]
}
sum(1, 2, 3);

let a = [1, 2, 3];
let b = [...a]; // [1,2,3]
```

- use case
  - Rest
    - function
  - Spread
    - array , object

```js
funciton multiply(...nums){  // spread operator
   console.log(nums)
}
var arr = [5,6]
multiply(...arr)  // rest operator
```

## Types

### Primitive

### Reference

> When two similar objects are compared in JavaScript, what is the output?

- **Reference**

  - Since objects are primitive types, the comparison yields `false`.
  - This result indicates that the references are different.

- **Equality**
  - If two objects are equal to each other, meaning they have the same reference, so the comparison results in `true`.

```javascript
// both have different reference
let alex = { hairs: true };
let john = { hairs: true };

console.log(alex == john); // false

// when equall to each other , have same reference
let fruit1 = { name: "potato" };
let fruit2 = fruit1;
console.log(fruit2 === fruit1); // true
```

### Object

> How can you create objects in JavaScript?

- Type

  - `Object` Literal
  - `Constructor` Function
  - `Object.Create` Method
  - `ES6` Classes
  - `Object` Constructor

- **Object Literal:**
  - The simplest way to create an object is by using object literals

```javascript
var person = {
  name: "John",
  age: 30,
  gender: "Male",
};
```

- **Constructor Function:**
  - which are essentially regular functions that are used to construct objects.
  - You can define properties and methods inside the constructor function.

```javascript
function Person(name, age, gender) {
  this.name = name;
  this.age = age;
  this.gender = gender;
}
var person = new Person("John", 30, "Male");
```

- **Object.create Method:**
  - Can create a new object with the specified prototype object.
  - It provides a clean way to create objects based on existing prototypes.

```javascript
var personProto = {
  greet: function () {
    console.log("Hello!");
  },
};
var person = Object.create(personProto);
```

- **ES6 Classes:**
  - That provide a more familiar and cleaner syntax for defining object blueprints.

```javascript
class Person {
  constructor(name, age, gender) {
    this.name = name;
    this.age = age;
    this.gender = gender;
  }
}
var person = new Person("John", 30, "Male");
```

- **Object Constructor:**
  - That provides predefined methods for creating and manipulating objects.

```javascript
var person = new Object();
person.name = "John";
person.age = 30;
person.gender = "Male";
```

> what is the `Object Destructuring` ?

- **Definition:**

  - Introduce
    - Introduced in ES6,
  - Variable
    - object destructuring extracts object properties into variables for convenient use.

- **Syntax:**

  - Uses curly braces `{}` for assignment.

    ```javascript
    const { name, age } = person;
    ```

- **Multiple Assignments:**

  - Assigns multiple object properties at once.

    ```javascript
    const { prop1, prop2 } = obj;
    ```

- **Default Values:**

  - Supports default values for undefined properties.

    ```javascript
    const { prop = defaultValue } = obj;
    ```

- **Nested Destructuring:**

  - Destructures properties of nested objects.

    ```javascript
    const { nestedProp } = obj.prop1;
    ```

- **Function Parameters:**

  - Simplifies function parameter handling.

    ```javascript
    function exampleFunction({ prop1, prop2 }) {
      // Function logic using prop1 and prop2
    }
    ```

- **Usage:**
  - Common in extracting data from API responses and complex object manipulations.

> ow can you determine if a property exists in an object in JavaScript?

- determine
  - `in` operator
  - `hasOwnProperty` method
  - Optional chaining

```js
const person = {
  name: "Alice",
  age: 30,
  gender: "female",
};

// Operator -> In
console.log("name" in person); // true
console.log("job" in person); // false

// Method -> hasOwnProperty
console.log(person.hasOwnProperty("name")); // true
console.log(person.hasOwnProperty("job")); // false

// Optional Chaining
console.log(person?.info?.address?.city); // "New York"
console.log(person?.info?.job?.title); // undefined (no error)
```

> What is the difference between `in` operator and `hasOwnProperty` method?

- Check
  - In
    - operator checks for **both** own and inherited properties.
  - hasOwnProperty
    - method checks **only** for own properties, excluding inherited ones

```js
// Operator -> In
const obj = { key: "value" };
console.log("key" in obj); // true
console.log("toString" in obj); // true (inherited from Object prototype)

// Method -> hasOwnProperty
const obj = { key: "value" };
console.log(obj.hasOwnProperty("key")); // true
console.log(obj.hasOwnProperty("toString")); // false (inherited property)
```

> What is the difference between the `freeze` and `seal` methods ?

- **Object**
  - both method are for the global object immutability methods
- **Limitation**
  - Seal
    - allows edits to existing properties but doesn't permit addition or removal of properties.
  - Freeze
    - prevents any changes, making the object completely immutable.

| **Method** | **Add** | **Edit** | **Remove** |
| ---------- | ------- | -------- | ---------- |
| `freeze()` | ❌      | ❌       | ❌         |
| `seal()`   | ❌      | ✅       | ❌         |

```javascript
// Freeze Method
const obj = {
  name: "John",
  age: 30,
};
Object.freeze(obj);
obj.name = "Alice"; // This change will be ignored in a frozen object

// Seal Method
const obj = {
  name: "John",
  age: 30,
};
Object.seal(obj);
obj.name = "Alice"; // This change is allowed in a sealed object
obj.address = "123 Street"; // This addition will be ignored in a sealed object
```

### Array

> How can you determine if a value is an array in JavaScript?

- Determine
  - `Aarray.isArray()` Method
  - `instanceof` Operator
  - `Object.prototype.toString()` Method

```js
// method ->  Array.isArray
const arr = [1, 2, 3];
const nonArray = "Hello";
console.log(Array.isArray(arr)); // true (arr is an array
console.log(Array.isArray(nonArray)); // false (nonArray is not an array)

// Operator -> instanceof
const arr = [1, 2, 3];
const nonArray = "Hello";

console.log(arr instanceof Array); // true
console.log(nonArray instanceof Array); // false

// method -> Object.prototype.toString()
const arr = [1, 2, 3];
const nonArray = "Hello";

console.log(Object.prototype.toString.call(arr) === "[object Array]"); // true
console.log(Object.prototype.toString.call(nonArray) === "[object Array]"); // false
```

> What are the various methods for iterating over array elements using a `for` loop ?

- Type
  - Standard for Loop
  - For Of
  - For In
  - ForEach

```js
// Array
const numbers = [1, 2, 3, 4, 5];

// Standar For
for (let i = 0; i < numbers.length; i++) {
  console.log(numbers[i]);
}

// For Of
const numbers = [1, 2, 3, 4, 5];
for (const number of numbers) {
  console.log(number);
}

// For In
const numbers = [1, 2, 3, 4, 5];
for (let index in numbers) {
  console.log(numbers[index]);
}

// ForEach
const numbers = [1, 2, 3, 4, 5];
numbers.forEach(function (number) {
  console.log(number);
});
```

### Number

> How can a string be converted to a number in JavaScript?

- Unary Plus Operator (`+`)
  - Using the unary plus operator (`+`) can be used to convert a string to a number.

```javascript
console.log(+"29"); // 29 (typeof number);
```

### String

> What are Template Literals in JavaScript ?

**Template Literals:**

- **Definition:**

  - Introduced in ES6, template literals enhance string handling in JavaScript.
  - Allow embedding expressions inside backticks (\`), improving readability and flexibility.

- **Syntax:**

  - Defined using backticks (\`).
  - Example:
    ```javascript
    const name = "Alice";
    const greeting = `Hello, ${name}!`;
    ```

- **Expression Embedding:**

  - Expressions embedded using `${}` syntax.
  - Enables variables and expressions in strings.

- **Multi-line Strings:**

  - Supports multi-line strings without concatenation or escape characters.
  - Line breaks maintained within backticks.

- **Tagged Templates:**

  - Utilized with functions, creating "tagged templates."
  - Functions (tags) manipulate the template literal's output.

    ```javascript
    function myTag(strings, ...values) {
      // Custom logic applied here
    }
    const name = "Alice";
    const greeting = myTag`Hello, ${name}!`;
    ```

- **Usage:**
  - Widely used for dynamic string generation, HTML templates, and scenarios requiring dynamic string construction.

```javascript
const name = "Alice";
const age = 30;
const message = `Hello, my name is ${name} and I am ${age} years old.`;
// output -> Hello, my name is Alice and I am 30 years old.
```

### Undefined

> When does a variable in JavaScript become undefined?

- **Variable:**
  - Declared but not assigned: Becomes `undefined`.
- **Object:**
  - Accessing non-existent properties: Results in `undefined`.
- **Function:**
  - No explicit return: Defaults to `undefined`.
  - Fewer arguments provided: Extra parameters set to `undefined`.
  - Conditional/default values used to handle potential `undefined` cases.

```javascript
// variable -> Declared but not assigned
let exampleVariable; // undefined

// object -> Accessing non-existent properties
const obj = { key: "value" };
console.log(obj.nonExistentKey); // undefined

// function ->  No explicit return
function noReturnFunction() {}
console.log(noReturnFunction()); // undefined

// function ->  Fewer arguments provided:
function exampleFunction(param) {
  console.log(param); // undefined
}
exampleFunction();

// function -> Conditional/default values used
function exampleFunction(param) {
  const valueToUse = param || "Default Value";
  console.log(valueToUse);
}
```

### Nan

> what is the `Nan` type ?

- Stand for
  - Not a Number
- Occurrences
  - When a mathematical operation such as multiplication is applied to non-numeric values

```js
let result = 10 / "apple";
console.log(result); // NaN (division of a number by a non-numeric value)
```

- Unique
  - that is not equal any value , including itself when compared using the equality operations

```js
console.log(NaN == NaN); // false
console.log(NaN === NaN); // false
```

- Check
  - with `isNan()` can check for NaN values
  - handle them gracefully in their applications , ensuring that unexpected NaN do not disrupt

```js
console.log(isNaN(NaN)); // true
console.log(isNaN("Hello")); // true (non-numeric string coerced to NaN)
console.log(isNaN(42)); // false (valid number)
```

### Null

> Why is `typeof null` an 'object' ?

- **Historical Bug**
  - The result of `typeof null` being `'object'` is considered a historical bug in JavaScript.

```js
typeof null === "object"; // true
```

- **Cause:**
  - Limit
    - When JavaScript was created, its original version had a 32-bit memory limit.
  - Low bits
    - The low bits of the binary representation for real objects are different from other types.
    - Objects have `000` in the low bits, whereas the low bits for `null` are `0001`.
    - The presence of `0001` in the low bits caused `typeof null` return `'object'`.
    - This behavior was carried forward for backward compatibility reasons. Changing it would have introduced breaking changes to existing code.
- **Caution:**
  - It's important to note that `null` is a primitive value in JavaScript, not an object.
  - This can lead to unexpected behaviors if not handled carefully.
- **Check:**
  - For more accurate comparisons , it's better use the equality operator ( === ) rather than `typeof`

```js
console.log(typeof null); // object

var value = null;
console.log(value === null); // true
```

### Null vs Undefined

> what is the different between undefined and null ?

- Type
  - Undefined
    - types is a Undefined
  - Null
    - type that is Object
- Variable , Assignment
  - Undefined
    - when don't assignment a variable, by default value that is undefined
  - Null
    - when you want a value null have , you explicitly use of null

```js
let a; // type -> undefined
let b = null; // type -> null
```

### False

> What are falsy values in JavaScript ?

- Value

  - Falsy values refer to values in JavaScript that, when converted to a Boolean

  ```javascript
  const falsyValues = ["", 0, null, undefined, NaN, false];
  ```

> How can we check if an expression is falsy ?

- Determine
  - Boolean Function
  - Double Not Operator

```javascript
// Boolean Function
var sch = null;
console.log(Boolean(sch)); // false

// Double Not Operator
var sch = null;
console.log(!!sch); // false
```

### False vs True

> what is the truthy and falsy ?

- Falsy
  - `NaN` (Not a Number) : Represents a value that is not a valid number
  - `null` : Represents an intentional absence of any object value
  - `undefined` : variable that has been declared but hasn't been assigned a value yet
  - `false` : The boolean false
  - `0` : The number zero
  - `""` Empty String : string with no characters in it.
- Truthy
  - This includes any value that is not falsy

### Coercion

> what is the `Coercion` ?

**Coercion**

> What is `Coercion` in JavaScript?

- Conversion
  - that automatic or implicit conversion of values from one data type to another during operations or comparisons.
- Use
  - This process happens behind the scenes and is intended to make different types of values work together seamlessly in expressions
- Type
  - Implicit
    - automatically converts values of one type to another without the programmer explicitly requesting it.
  - Explicit
    - Programmers intentionally convert values from one type to another using functions or operators like `parseInt()`, `Number()`, `String()`

```js
// Implicit
let num = 42;
let str = "The answer is: " + num; // Implicit coercion of num to a string

// Explicit
let strNumber = "42";
let num = Number(strNumber); // Explicit coercion of strNumber to a number
```

## Variable

#### Var

#### Let

#### Const

#### Difference

> What is Difference Between Var And Let ?

- Scope
  - var
    - global scope
  - let
    - block scope
- Version
  - var
    - it's exist before
  - let
    - introduce in after ec7 or 2013
- Hoisting
  - var
    - that hoisted
  - let
    - not hoisted

> what is different between 'var vs let vs const' ?

- **Scope**
  - `var`
    - Has function scope, meaning it is accessible within the function it is declared in.
  - `let`
    - Has block scope, meaning it is accessible only within the block it is declared in.
  - `const`
    - Also has block scope and behaves similar to `let`, but cannot be reassigned after declaration.
- **Version**
  - `var`
    - Existed before ES6 (ECMAScript 6).
  - `let` and `const`:
    - Introduced in ES6 (2015) as more predictable alternatives to `var`.
- **Hoisting**
  - `var`
    - Variables are hoisted and can be accessed before their declaration.
  - `let` and `const`
    - Variables are hoisted but not initialized; accessing them before declaration results in a ReferenceError
- **Redeclaration**
  - `var`:
    - Can be redeclared within the same scope.
  - `let` and `const`:
    - Cannot be redeclared within the same scope.
- **Reassignment**
  - `var`:
    - Can be reassigned.
  - `let`:
    - Can be reassigned.
  - `const`:
    - Cannot be reassigned after initialization.

| Feature           | `var`    | `let`       | `const`     |
| ----------------- | -------- | ----------- | ----------- |
| **Scope**         | Function | Block       | Block       |
| **Version**       | Pre-ES6  | ES6         | ES6         |
| **Hoisting**      | Yes      | Yes         | Yes         |
| **Redeclaration** | Allowed  | Not Allowed | Not Allowed |
| **Reassignment**  | Allowed  | Allowed     | Not Allowed |

### This

> What the mean 'This' keyword ?

- Execute
  - Refers to the part of the code that is being executed at this moment.
- Value
  - The value of this is an _object_.
  - It doesn't matter where and how we wrote the function.
  - What affects the value of this is the place and the way the function is \*called

```js
var name = "Sarah";

function person() {
  console.log(this.name);
}

person(); // Sarah
```

#### Apply

> What does the `apply` method do in JavaScript?

- Value
  - enables us to set the value of `this` in a function to a specific object of our choice.

```js
const person = {
  firstname: "Alice",
  lastname: "Smith",
  introduce() {
    alert(`${this.firstname} ${this.lastname}`);
  },
};

const person1 = {
  firstname: "Bob",
  lastname: "Johnson",
};

const person2 = {
  firstname: "Eva",
  lastname: "Davis",
};

person.introduce.apply(person1); // Alerts: Bob Johnson
person.introduce.apply(person2); // Alerts: Eva Davis
```

- Passing Argument
  - If the method requires arguments, we can pass them as an array

```js
const person = {
  introduce(age, country) {
    alert(`${this.firstname} ${this.lastname}, ${age}, ${country}`);
  },
};

const person1 = {
  firstname: "Alice",
  lastname: "Smith",
};

person.introduce.apply(person1, [25, "USA"]); // Alerts: Alice Smith, 25, USA
```

#### Call

> What does the `call` method do in JavaScript?

- **Value:**

  - The `call` method in JavaScript allows us to set the value of `this` in a function to a specific object of our choice, similar to `apply`.

  ```javascript
  const person = {
    firstname: "Alice",
    lastname: "Smith",
    introduce() {
      alert(`${this.firstname} ${this.lastname}`);
    },
  };

  const person1 = {
    firstname: "Bob",
    lastname: "Johnson",
  };

  const person2 = {
    firstname: "Eva",
    lastname: "Davis",
  };

  person.introduce.call(person1); // Alerts: Bob Johnson
  person.introduce.call(person2); // Alerts: Eva Davis
  ```

- **Passing Arguments:**

  - Similarly, if the method requires arguments, we can pass them individually.

  ```javascript
  const person = {
    introduce(age, country) {
      alert(`${this.firstname} ${this.lastname}, ${age}, ${country}`);
    },
  };

  const person1 = {
    firstname: "Alice",
    lastname: "Smith",
  };

  person.introduce.call(person1, 25, "USA"); // Alerts: Alice Smith, 25, USA
  ```

The `call` method works similarly to `apply`, but instead of passing arguments as an array, we pass them individually after the context object.

> what is difference between 'call' and 'apply' method ?

- Argument
  - call
    - Individually : arguments to be passed individually
  - apply
    - Array : Arguments are passed as an array or an array-like object.

```javascript
function greet(name, age) {
  console.log(`Hello, ${name}. You are ${age} years old.`);
}

// Call Method
greet.call(null, "Alice", 30); // Output: Hello, Alice. You are 30 years old.

// Apply Method
const args = ["Bob", 25];
greet.apply(null, args); // Output: Hello, Bob. You are 25 years old.
```

#### Bind

> What does the 'bind' method do in JavaScript ?

- Syntax:
  - `function.bind(thisArg[, arg1[, arg2[, ...]]])`
  - The `thisArg` parameter represents the context object that the function will have when invoked.
  - Additional optional arguments can also be passed and will be prepended to the arguments provided to the bound function.
- Function
  - Bind method is for create a new function with a specified `this` value.
- Custom This
  - It allows developers to explicitly define the context (`this` value) of the function, regardless of where and how the function is called.

```js
function hit() {
  this.count++;
}

const jumps = { count: 0 };
const hitJumps = hit.bind(jumps);

hitJumps();

alert(jumps.count); // Output: 1
```

- Persistent Context:
  - The bound function retains the specified `this` context, making it useful in scenarios where the function needs to be passed as a callback or used in event listeners while maintaining a consistent context.
- Creating Partial Functions:
  - `bind` can also be used to create partially applied functions, allowing developers to fix certain arguments and leave others open for future invocation.

## Function

### List

#### Arrow

> what is the arrow function ?

- Introduce
  - arrow function introduce in ES6 in javascript
- Syntax
  - it's has a bit more clean syntax
- Return
  - if function returning several line , you have to use of return otherwise not use
  - if have curly braces , you need use of return

```js
// returning several line
const sum = (number , number2) => {
  const result = number + number 2
  return result * 2 ;
}
console.log(sum(5,3))


// returning one line
const sum (number , number2) => result = number * number2
```

- **Limitations**
  - This
    - do not bind their own `this` value.
    - They inherit `this` from the parent scope.
  - Arguments
    - do not have their own `arguments` object.
    - They inherit `arguments` from the containing scope.

```js
// this
function RegularFunction() {
  this.value = 1;
  setTimeout(() => {
    this.value++;
    console.log(this.value); // 2
  }, 1000);
}
const instance = new RegularFunction();

// argumetns
function RegularFunction() {
  setTimeout(() => {
    console.log(arguments[0]); // ReferenceError: arguments is not defined
  }, 1000);
}
RegularFunction("hello");
```

> what is the difference between arrow function and declaration function ?

- Syntax
  - Declaration
    - don't use of arrow
  - Arrow
    - use of arrow

```js
// declaration function
function square(num) {
  return num * num;
}

// arrow function
const square = (num) => {
  return num * num;
};
```

- Return
  - Declaration
    - you have to use of return even if you have one line returning
  - Arrow
    - don't need use if you have one line returning

```js
// declaration function
function square(num) {
  return num * num;
}

// arrow function
const square = (num) => num * num;
```

- Argument
  - Declaration
    - is defined
  - Arrow
    - don't defined

```js
// declaration function
function fn() {
  console.log(arguments); //  { '0': 1, '1': 2, '2': 3 }
}
fn(1, 2, 3);

// arrow functions
let fnArr = () => {
  console.log(arguments); // arguments is not defined
};

fnArr(1, 2, 3);
```

- This keyword
  - Declaration
    - support this
  - Arrow
    - don't support

```js
let user = {
  username: "ali",
  rc1() {
    console.log(this.username);
  },
  rc2: () => {
    console.log(this.username);
  },
};

user.rc1(); // ali
user.rc2(); // undefined
```

#### Declaration

> what is the difference Declaration and Expression function ?

- Syntax
  - Declaration
    - function name () {}
  - Expression
    - let a = function () {}

```js
function name() {}

let a = function () {};
```

- Hoist
  - Declaration
    - this function hoisted
  - Expression
    - not hoisted

```js
name(); // true
function name() {}

a(); // flase
let a = function () {};
```

#### Expression

> What is the Expression Function ?

- Name
  - other name if `Normal Function`
- Variable
  - when a anonymous function assign to a variable

```js
let a = functin () {}
```

#### Anonymous

> what is the Anonymous Function ?

- Name
  - Function that no name

```js
function (){}   // not have any name
```

- Use Case
  - Assign to a Variable
  - Passed as Call back function

```js
let a = function () {}

function(() {}){
 retun a
}
```

#### First Class

> What are the First Class Functions ?

- Treat
  - They treated like variable , means they can be :
    - passed as arguments to other functions,
    - returned from other functions,
    - manipulate function,
    - and assigned to variables.

```js
function square (num){
  return num * num
}

funciton displaySquare (fn) {
  console.log("square is " , fn(5))
}

displaySquare(square)
```

- high order function
  - This flexibility enables powerful programming paradigms like functional programming and enables higher-order functions.

#### Self Invoke

> what is the IIFE ?

- Stand For
  - Immediately Invoked Function Expression

```js
(function square(num) {
  console.log(num * num); // 25
})(5);
```

#### Closure

> what is the closure ?

- Remember
  - Function that remember the variables from the scope in which it was created , even after that scope has finished executing
- Function
  - When use function within another function , inner function is closure
- Runtime
  - Closure determined in Runtime
- Use case
  - implementing private methods, creating callbacks, and creating stateful functions.

> What is difference between closure and scope ?

- Variable
  - Scope
    - that defines the visibility and accessibility of variables in a specific context,
  - Closure
    - is a function that remembers the variables from the scope in which it was created, even after that scope has finished executing.
- Definition
  - Scope
    - the placement that variable defined
  - Closure
    - when use function within another function , inner function is closure
- Determine
  - Scope
    - scope determined in at Compile time
  - Closure
    - closure determined in at Runtime
- Use Case
  - Scope
    - ...
  - Closure
    - implementing private methods, creating callbacks, and creating stateful functions.

#### Call Back

> What is the call back function ?

- Passed
  - function that is passed as an argument to another function
- Invoke
  - which is then invoked inside the outer function to complete some kind of routine or action
- Specific Operation
  - when want execute a piece of code after specific operation
- Asynchronous
  - that use in asynchronous programming and event-driven systems
  - to handle actions that should occur in response to certain conditions.

```javascript
// Example Array
const numbers = [1, 2, 3, 4, 5];

// Using Add Event
document.addEventListener("click", function (params) {
  console.log(params);
});

// Using `map` to Double Each Element
const doubledNumbers = numbers.map(function (number) {
  return number * 2;
});
console.log("Doubled Numbers:", doubledNumbers); // Output: [2, 4, 6, 8, 10]

// Using `filter` to Get Even Numbers
const evenNumbers = numbers.filter(function (number) {
  return number % 2 === 0;
});
console.log("Even Numbers:", evenNumbers); // Output: [2, 4]

// Using `reduce` to Sum All Elements
const sum = numbers.reduce(function (accumulator, currentValue) {
  return accumulator + currentValue;
}, 0);
console.log("Sum of Numbers:", sum); // Output: 15
```

#### High Order

> What is the `High Order Function` ?

- **Function:**
  - Function that can accept another function as an **argument** or **return** a function as its result.

```js
// Higher Order Function
function multiplier(factor) {
  // accept as argument
  // Inner function
  return function (number) {
    // return as result
    return number * factor;
  };
}

const double = multiplier(2); // Returns a function that doubles the input
const triple = multiplier(3); // Returns a function that triples the input

let result1 = double(5); // Result: 10 (2 * 5)
let result2 = triple(5); // Result: 15 (3 * 5)
```

#### First-Class

> What are first-class entities ?

- Other name
  - first-class entities , first-class citizens
- **Entities:**

  - Are entities in a programming language that support all operations, such as :
    - being passed as arguments,
    - returned from functions,
    - and assigned to variables.

- **Function**

  - Functions in JavaScript are first-class entities, meaning they can:
    - Be passed as arguments to other functions.
    - Be returned from other functions.
    - Be assigned to variables.

- **Example:**

```javascript
var func = function passAsArg(value, callback) {
  return callback(value);
};

func("value", alert);
```

#### Currying

> what is the currying function ?

- Transform
  - that allows you to transform a function with multiple arguments into a sequence of nesting functions
- Argument
  - that takes multiple arguments into a sequence of functions that take one argument each.
- Return
  - This is done by returning a new function from the original function that takes the first argument of the original function and returns a new function that takes the second argument of the original function, and so on.

```js
// Curry a function that takes three arguments.
const curryThreeArgs = curry((a, b, c) => a + b + c);

// Partially apply the first argument to the curried function.
const addTen = curryThreeArgs(10);

// Add 5 and 10 together.
const sum = addTen(5);

console.log(sum); // 15
```

### Inputs

#### Argument

> What is the `arguments` object in JavaScript functions?

- **Object:**
  - an array-like object available in all functions, containing the arguments passed to the function.

```javascript
function commit() {
  console.log(arguments); // { '0': 1, '1': 2, '2': 4 }
  console.log(arguments[0]); // 1
}

commit(1, 2, 4);
```

- **Cons**
  - Arrow Function do not have access to argument
  - instead can use of rest operator

```js
const sampleFunction = () => {
  console.log(arguments); // Error: 'arguments' is not defined
};
sampleFunction(1, 2, 3);

// solution -> use speared operator
const sampleFunction = (...args) => {
  console.log(args); // [ 1, 2, 3 ]
};
sampleFunction(1, 2, 3);
```

> What is difference between argument and spread operator ?

- `arguments` behaves like an array but lacks array methods like `forEach` and `map`. However, Arrow Functions do not have access to `arguments`. Instead, the rest parameter (`...args`) can be used:

```javascript
commit = (...args) => {
  console.log(args);
};

commit(1, 2, 4); // [ 1, 2, 4 ]
```

#### Parameter

> what is `default parameter` in javascript function ?

- **Introduce:**
  - Introduced after ES6 to allow functions to have optional parameters with preset values.
- **Use:**
  - That used when parameter is not provided during the function or `undefined` is passed
- **Syntax:**
  - Default parameters are specified in the function's parameter list using the assignment operator (=).
- **Before**
  - Before default parameters, developers used the OR (`||`) operator to achieve similar functionality.

```js
// Before -> use of OR operaotr
function add(a, b) {
  var a = a || 0;
  var b = b || 0;

  return a + b;
}

// Now  -> assignment operator
function add(a = 0, b = 0) {
  return a + b;
}
```

- **Destructuring**
  - Can use that default parameter with object destructuring

```js
function getFirst([first, ...rest] = [0, 1]) {
  return first;
}
```

#### Diff

> what is different between argument and parameter ?

- Placement
  - Argument
    - there are variables that we **define** as input when creating functions and methods
  - Parameter
    - there are variables that we pass when **using** functions and methods

```js
function square(num) {
  // parameter
  console.log(num * num);
}

square(5); // argument
```

## Method

### Map

> what does the `Map` method ?

- Transform:

  - Is a higher-order function used to transform elements in a new array.

- Input:
  - Takes a callback function with three parameters:
    - the current element,
    - the index of the element,
    - and the original array.
- Output:

  - Results of the callback function are stored in a new array, which is returned as the output.

- **Example:**

```javascript
let numbers = [1, 2, 3, 4];

let output = numbers.map(function (num) {
  return num * 2;
});

console.log(output); // Output: [2, 4, 6, 8]
```

### Filter

> what does the `Fitler` method ?

- Condition
  - The `filter` method in JavaScript arrays is used to selectively extract elements from an array based on a specified condition.
- Argument
  - It take a callback function as argument is applied to each element of the array
- Return
  - elements for which that callback return true , are included in the resulting filtered array

```js
let numbers = [111, 99, 51, 101, 102];

let output = numbers.filter(function (item) {
  return item > 100;
});

console.log(output); // [111, 101, 102]
```

### Reduce

> What does the the `Reduce` method ?

- **Transform:**
  - Simplifies an array by transforming its elements into a single value.
- **Accumulation:**
  - It executes a provided function on each array element and add them to the accumulated value from the previous element
- **Use Cases:**
  - is useful for operations where elements are interdependent,
  - like summing or finding averages of numeric array elements.

### Pop

> What does the `pop()` method ?

- Remove
  - Remove last element from an array and return that element

```js
const colors = ["red", "green", "blue"];
const removedColor = colors.pop();
console.log(colors); // Output: ['red', 'green']
console.log(removedColor); // Output: 'blue'
```

## Event

### Target

> what is the event.target ?

- **Element:**
  - Refers to the specific element that directly triggered the event.
- **Functionality:**
  - `event.target`provides the element that was interacted with, offering dynamic event source information.
- **Use Case:**
  - **Dynamic Interaction Handling:**
    - Used when the event handler needs to respond to the specific element that was interacted with.
    - Ideal for scenarios where you want to modify or manipulate the triggering element dynamically based on user actions.
    - _Example:_ Changing the text of a clicked button or validating the content of an input field upon user interaction.

```html
<div onclick="getElement(event)">
  <p>
    <button></button>
  </p>
</div>
```

```js
function getElement(event) {
  alert(event.target.tagName);
}

// if clicked on ->
//	   button -> output => button
//	   p      -> output => p
//	   div    -> output => div
```

### CurrentTarget

> what is the CurrentTarget ?

- **Element**
  - Refers to the element where the event handler is placed or the event is attributed
- **Functionality**
  - is particularly useful during event propagation phases. When an event bubbles or captures through the DOM hierarchy, `currentTarget` remains constant, providing a reliable reference to the element hosting the event listener
- **Use Case**
  - Ensuring Consistent Behavior:
    - Ensures uniform responses across nested elements, such as validating form submissions consistently regardless of the triggering input element.
    - _Example:_ Validating form submissions uniformly regardless of which input triggered the event.
  - Event Delegation:
    - Utilized in a single handler on a parent element to efficiently manage interactions with multiple child elements like lists or tables, significantly improving performance.
    - _Example:_ Managing click events on multiple list items using a single event handler attached to the parent `<ul>` element.
  - Dynamic UI Modifications:
    - Enables modifications to container elements based on interactions with child elements in dynamic interfaces, ensuring a consistent user experience across diverse interactions.
    - _Example:_ Updating the content of a container dynamically based on the specific button clicked within it.

```html
<div onclick="getElement(event)">
  <p>
    <button></button>
  </p>
</div>
```

```js
function getElement(event) {
  alert(event.currentTarget.tagName);
}

// If Clicked ON :
// Button -> output => div
// P      -> output => div
// div    -> output => div
```

> what is difference between e.target vs e.currentTarget ?

- Element
  - e.target
    - Refers to the element that directly triggered the event
  - e.currentTarget
    - Refers to the element where the event handler is placed or the event is attributed
- Change
  - e.target
    - the changing element based on user action, providing dynamic event source information.
  - e.currentTarget
    - Remains constant within the event propagation, offering a consistent reference to the element hosting the event listener
- Usage
  - e.target
    - Responds to specific element interactions, ideal for dynamic modifications based on user actions
    - e.g., changing button text, validating input
  - e.currentTarget
    - Utilized when you want consistent behavior regardless of which nested element triggered the event.
    - e.g., validating a form, stable behavior across different form fields

### Default

> How can you determine if event.preventDefault() has been applied to an element?

- defaultPrevented property
  - this property indicating that the default behavior has been prevented
  - if this valuse was true , it meant that preventDefault method has been applied

```html
<a id="anchor" href="#">The Slight Edge</a>

<script>
  var a = document.getElementById("anchor");
  a.addEventListener("click", function (event) {
    event.preventDefault();

    alert(event.defaultPrevented); // alerts true
  });
</script>
```

### Propagation

#### Bubbling

> What is Event Bubbling ?

- Propagation
  - There is a way to Propagation an event in a DOM
- Work
  - Event bubbling occurs when an event is triggered on the innermost element and then bubbles up to the outer elements in the DOM hierarchy.
- Enable
  - By default, event bubbling is the standard behavior in JavaScript.
  - You don't need to set any additional parameters to enable it.

```js
document.querySelector("div").addEventListener("click", function () {
  alert("I'm a div");
});

document.querySelector("p").addEventListener("click", function () {
  alert("I'm a p!");
});
```

#### Capturing

> What is Event Capturing ?

- Opposite
  - Event Capturing is the opposite of event bubbling
- Work
  - the event starts from the outermost element and travels through nested elements, reaching the target element last.
- Enable
  - To enable event capturing, the third argument of the `addEventListener` method should be set to `true`.

```js
document.querySelector("div").addEventListener(
  "click",
  function () {
    alert("I'm a div");
  },
  true,
);

document.querySelector("p").addEventListener(
  "click",
  function () {
    alert("I'm a p!");
  },
  true,
);
```

#### Diff

> What is the difference between the `e.preventDefault()` and `e.stopPropagation()` methods in JavaScript events?

- preventDefault()
  - Behavior
    - When applied to an element, it prevents the element's default behavior.
  - Example:
    - Preventing a form from submitting when the user clicks the submit button.
    - When applied to an a tag, it will cause that link to not work
- stopPropagation()
  - Propagation
    - Stop the event propagation, preventing it from reaching parent elements or other event listeners attached to the same element and ensuring the event does not continue along the DOM hierarchy.
  - Example:
    - Stopping an event from reaching parent elements.

```javascript
// preventDefault
document.querySelector("form").addEventListener("submit", function (e) {
  e.preventDefault();
  // Custom form submission logic
});

// stopPropagation
document.querySelector(".child-element").addEventListener("click", function (e) {
  e.stopPropagation();
  // This click event will not propagate to parent elements
});
```

## Prototype

> What is a "Prototype" in JavaScript?

- Inherit
  - when objects are created, they inherit a set of properties and methods from an object called the "prototype."

> How can we create an object without a prototype in JavaScript?

- Create Method
  - use the `Object.create()` method with `null` as its argument

```js
const obj = Object.create(null);

console.log(obj.toString()); // Error: obj.toString is not a function
```

## Class

> What are the differences in writing classes between ES5 and ES6?

- Create
  - `ES5`
    - Classes were defined using constructor functions
  - `ES6`
    - In ES6, classes can be defined using a syntax called "class syntax".
    - This approach is more readable and aligns with what we commonly know from other programming languages:

```js
// ES5 -> Constructor Function
function Person(name, age) {
  this.name = name;
  this.age = age;
}

Person.prototype.greet = function () {
  console.log("Hello, my name is " + this.name + " and I am " + this.age + " years old.");
};

var person = new Person("Alice", 30);
person.greet();

// ES6 -> Better Syntax is Called Class
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
  }
}

let person = new Person("Alice", 30);
person.greet();
```

### New

> What does the `new` keyword ?

- **Usage**
  - **Function:**
    - Constructor functions, when used with `new`, set properties on the newly created object.
    - Initializes a new object and binds the function call to it.
  - **Class:**
    - When `new` is applied to a class, it generates a new object based on the class blueprint.

```javascript
// Constructor Function -> + New -> New Object
function Car(make, model) {
  this.make = make;
}

const myCar = new Car("Toyota", "Camry");
console.log(myCar.make); // Output: 'Toyota'

// Class -> + New -> New Object
class Vehicle {
  constructor(type) {
    this.type = type;
  }
}

const myVehicle = new Vehicle("Car");
```

- **Case Name:**
  - Capitalization
    - Constructors and classes start with capital letters (e.g., `Car`, `Vehicle`) to indicate their usage with `new` when creating objects.

## Storage

### Local Storage

> What is Local Storage in JavaScript?

- Definition

  - Browser
    - Local Storage is a storage area available in the user's **browser**
  - Javascript
    - that allows JavaScript to store and retrieve data persistently.

- Use Cases:
  - **User Preferences:**
    - Store user preferences and settings locally for a personalized experience across sessions.
  - **Caching:**
    - Cache API responses or frequently accessed data to reduce server requests and enhance performance.
  - **Form Data Persistence:**
    - Save form data temporarily to prevent loss when a page is refreshed or accidentally closed.
- Limitations:
  - **Storage Capacity:**
    - Local Storage typically has a storage limit of around 5-10 MB per domain.
  - **Data Format:**
    - Data stored in Local Storage must be in string format, requiring serialization and deserialization for complex data structures.

```javascript
// Storing data in Local Storage
localStorage.setItem("username", "john_doe");

// Retrieving data from Local Storage
const username = localStorage.getItem("username");

// Removing data from Local Storage
localStorage.removeItem("username");
```

## Modules

> what is the Modules in Js ?

- **Definition:**

  - Modules in ES6 allow developers to divide code into smaller pieces, maintain each part in a separate file, and use them as independent units in the program.

- **Importing and Exporting:**

  - Modules can be imported and exported between files using `import` and `export` statements, enabling communication between different files.

- **Types of Exports:**

  - Modules can export variables, functions, or classes.
  - Exports can be either `default` or named.

- **Usage:**
  - Modules are extensively used in modern web development and JavaScript programming to manage and organize code by keeping related functionality together in separate files.
  - This approach reduces code complexity and enhances maintainability and debugging capabilities.

## Object

### Set

> what is the `set` object ?

- Unique Value

  - The Set object in JavaScript is a new way to store unique values.
  - That is, there are no duplicate items in the set

- Syntax:

  ```javascript
  const alpha = new Set(["a", "b", "b", "b", "c"]);
  ```

- Method
  - add
    - for add a value to a Set
  - remove
    - for remove an item from Set
  - has
    - To check if an item exists in a Set
  - clear
    - To clear all items from a Set
  - size
    - To get the number of items in a Set

```javascript
// Create a new Set
const alpha = new Set(["a", "b", "b", "b", "c"]);

// Add a new item to the Set
alpha.add("d");

// Remove an item from the Set
alpha.delete("b");

// Check if an item exists in the Set
alpha.has("h"); // Returns: false

// Clear all items from the Set
alpha.clear();

// Get the number of items in the Set
alpha.size; // Returns: 0
```

- **Usage:**
  - Sets are commonly used to remove duplicate values from an array, providing a quick and efficient way to filter unique items.

```javascript
const numbers = [1, 2, 3, 4, 5, 6, 6, 7, 8, 8, 5];
const uniqueNums = [...new Set(numbers)];
console.log(uniqueNums); // [1, 2, 3, 4, 5, 6, 7, 8]
```

### Wrapper

> What is an `Object Wrapper` in JavaScript?

- Convert
  - Refers to the automatic conversion of primitive data types (like strings, numbers, and booleans) into their corresponding object representations when a property or method is accessed on them.
- Discard
  - After the operation, the temporary object wrapper is discarded.

```js
let str = "Hello";
// str first primitive string ->  then convert to object ->  then discard after operation
console.log(str.length); // Output: 5
```

## Async

> what is async in javascript ?

- Execute
  - async are executed separately from main process of the program
  - the program does not wait for them to finish add continues its work
- Example
  - connecting to and external resource with ajax
- Handle
  - There are different ways to handle asynchronous operations in JavaScript.
  - Such as : callback , promise and async await

> What are the ways to manage asynchronous operations?

- Callbacks
  - **Def**
    - Simple but prone to callback hell. A function passed as an argument to another function
  - **Pros**
    - Simple, widely supported, and easy to understand
  - **Cons**
    - where nested callbacks can make code difficult to read and maintain
- Promises
  - **Def**
    - Better than callbacks, with improved error handling and chaining.
  - **Pros**
    - Avoids callback hell, improved error handling with `.catch()`, and easier chaining.
  - **Cons**
    - Requires understanding of Promise concepts.
- Async/Await:
  - **Def**
    - Modern , readable, and synchronous-looking asynchronous code.
  - **Pros**
    - Improved readability, code appears synchronous,
    - and easy error handling with `try` and `catch
  - **Cons**
    - Requires understanding of Promises and modern JavaScript
- Observables:

  - **Def**
    - A pattern widely used in reactive programming for handling asynchronous data streams.
    - Advanced, and suitable for complex applications, especially in reactive programming paradigms.
  - **Pros**
    - Powerful, provides operators for advanced operations on data streams,
    - suitable for complex applications.
  - **Cons**
    - Steeper learning curve, overkill for simpler applications.

- **Callbacks**

```javascript
function fetchData(callback) {
  // Asynchronous operation
  setTimeout(() => {
    callback(data);
  }, 1000);
}

fetchData((data) => {
  console.log(data);
});
```

- **Promises:**

```javascript
function fetchData() {
  return new Promise((resolve, reject) => {
    // Asynchronous operation
    setTimeout(() => {
      if (success) {
        resolve(data);
      } else {
        reject(error);
      }
    }, 1000);
  });
}

fetchData()
  .then((data) => {
    console.log(data);
  })
  .catch((error) => {
    console.error(error);
  });
```

- **Async/Await:**

```javascript
async function fetchData() {
  try {
    const data = await fetchDataFromAPI();
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

fetchData();
```

- **Observables (RxJS):**

```javascript
import { Observable } from "rxjs";

const observable = new Observable((observer) => {
  observer.next("Data 1");
  observer.next("Data 2");
  observer.error("Error occurred");
});

const subscription = observable.subscribe({
  next: (data) => console.log(data),
  error: (error) => console.error(error),
});
```

### Ajax

> What is `AJAX` in JavaScript?

- **Stand For**
  - Asynchronous Javascript and XML
- **Asynchronous**
  - A technology used in web development to create dynamic and interactive user interfaces
  - AJAX enables asynchronous communication between the client (browser) and the server
- **Refresh**
  - A web page can request and retrieve data from the server without refreshing the entire page.
  - The execution process of our program does not wait
- **XML**
  - While XML is part of the name, AJAX can work with other data formats like JSON
  - JSON has become more popular due to its simplicity and ease of use.
- **XMLHttpRequest**
  - Ajax requests are typically made using the `XMLHttpRequest` object,
  - a built-in JavaScript object that provides methods and properties for interacting with servers
- **Advantage**
  - Improved User Experience
  - Efficient Data Retrieval
  - Interactive Web Application
- **Example:**
  - Here's a simple example of an AJAX request using the `XMLHttpRequest` object to fetch data from a server:

```javascript
var xhr = new XMLHttpRequest();
xhr.open("GET", "https://api.example.com/data", true);
xhr.onreadystatechange = function () {
  if (xhr.readyState == 4 && xhr.status == 200) {
    var data = JSON.parse(xhr.responseText);
    console.log(data);
  }
};
xhr.send();
```

### Promise

> What are Promises in JavaScript ?

- **Object**
  - Promises in JavaScript are objects used for managing asynchronous operations
- **Asynchronous**
  - providing a more structured and sequential approach to handling asynchronous tasks
- **Pros**
  - Clean
    - Promises simplify and enhance code readability.
  - Manage:
    - Efficiently manage successful asynchronous results.
  - Error Handling:
    - Streamline error management for asynchronous tasks.

### Async/Await

> what is `async/await` ?

- Manage
  - a way for handle asynchronous operations in javascript
- Promise
  - is built on top of promises and use of promises behind the scene
- Functionality
  - that is much easier , more readable and better than other methods
- Keyword
  - async
    - Used before a function declaration
    - for indicate that the function returns a promise implicitly
  - await
    - Used inside an async function
    - for pause the execution until the promise is resolved,
    - that providing a non-blocking approach to asynchronous tasks

```js
async function callApi() {
  try {
    const resp = await fetch("url/to/api/endpoint");
    const data = await resp.json();
    //do something
  } catch (e) {
    //
  }
}
```

### Diff

> what is deference between `async/await` and `promise`

- **Control Flow:**
  - _Async/Await:_
    - Synchronous appearance for asynchronous code, enhancing readability.
  - _Promise:_
    - Chaining promises can lead to complex, less readable code.
- **Error Handling:**
  - _Async/Await:_
    - Uses `try` and `catch` blocks, making error handling intuitive.
  - _Promise:_
    - Requires separate `.catch()` blocks, which can be less clear in complex scenarios.
- **Readability:**
  - _Async/Await:_
    - Resembles synchronous code, enhancing readability.
  - _Promise:_
    - Nested promises can lead to less readable, verbose code.
- **Debugging:**
  - _Async/Await:_
    - Easier debugging with a synchronous-like appearance.
  - _Promise:_
    - Debugging can be challenging, especially in deeply nested chains.
- **Error Stacks:**
  - _Async/Await:_
    - Provides accurate error stacks, aiding error tracing.
  - _Promise:_
    - Error stacks might lack clarity, especially in complex chains.
