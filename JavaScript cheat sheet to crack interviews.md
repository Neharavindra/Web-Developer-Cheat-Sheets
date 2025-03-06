# JavaScript and TypeScript Interview Questions Cheat Sheet

## **JavaScript Interview Questions**

**JavaScript Interview Questions & Answers**

### **What is JavaScript?**

- JavaScript (JS) is a **synchronous, single-threaded** language, meaning it executes one task at a time in a specific order.
- It is **interpreted and dynamically typed**, making it flexible for development but requiring careful debugging.
- JavaScript is a **scripting language** used to create **interactive and dynamic** web pages.
- It runs in the **browser's execution environment**, but can also be used on the **server-side** via Node.js.

### **Explain execution context in JS.**

- Everything in JavaScript runs within an **execution context**, which determines the scope and behavior of variables and functions.
- The execution context consists of two main phases:
  1. **Memory Creation Phase**: Variables and function declarations are stored in memory.
  2. **Code Execution Phase**: JavaScript executes the code line by line.
- **Global Execution Context (GEC)** is created first and contains the `window` object.
- **Function Execution Context (FEC)** is created when a function is invoked and is destroyed when execution completes.
- The **Call Stack** maintains the order of function execution and ensures that the last function called is the first to be executed.

### **What is Just-In-Time (JIT) compilation?**

- JIT compilation is a technique used in JavaScript engines like **V8 (Chrome, Node.js)** to **improve performance** by converting high-level JavaScript code into optimized machine code **at runtime**.
- Unlike traditional **interpreted languages**, JIT compilation **compiles and executes** code simultaneously.
- This enhances execution speed compared to **ahead-of-time (AOT) compilation**, which compiles code before execution.
- Modern JavaScript engines use **JIT optimizations** such as inline caching and hidden classes to improve performance.

### **What are first-class functions?**

- JavaScript functions are **first-class citizens**, meaning they can be:
  - Assigned to variables.
  - Passed as arguments to other functions.
  - Returned from other functions.
- This property allows for powerful programming techniques like **higher-order functions**, **callbacks**, and **functional composition**.

### **What are higher-order functions?**

- A **higher-order function** is a function that:
  - **Takes another function as an argument**.
  - **Returns another function** as a result.
- They allow for **reusability, abstraction, and functional programming patterns**.
- Example:
```javascript
function multiplier(factor) {
  return function (number) {
    return number * factor;
  };
}
const double = multiplier(2);
console.log(double(5)); // Output: 10
```

### **What is a variable and what are the different types of variable declarations in JS?**

- A **variable** is a named reference to a value in memory.
- **Types of variable declarations:**
  - **`var`**:
    - Function-scoped (accessible throughout a function but not outside it).
    - Can be **redeclared and updated**.
    - Hoisted and initialized with `undefined`.
  - **`let`**:
    - Block-scoped (only accessible within the enclosing `{}` block).
    - Cannot be **redeclared in the same scope**, but can be updated.
    - Hoisted but **not initialized**.
  - **`const`**:
    - Block-scoped and **cannot be reassigned**.
    - **Read-only**, but for objects, properties can be modified.
    - Prevents unintended reassignments and enforces immutability.

### **What is hoisting in JS?**

- **Hoisting** is JavaScript’s behavior of moving **variable and function declarations** to the **top of their scope** before execution.
- Only **declarations** are hoisted, not value assignments.
- **Function declarations** are fully hoisted, but **function expressions** are not.
- Example:
```javascript
console.log(x); // Output: undefined (due to hoisting)
var x = 10;
```

### **What is the Temporal Dead Zone (TDZ)?**

- The **Temporal Dead Zone (TDZ)** is the time between the **declaration** of a variable (with `let` or `const`) and its **initialization**.
- Accessing a variable in TDZ results in a **ReferenceError**.
- Example:
```javascript
console.log(a); // ReferenceError: Cannot access 'a' before initialization
let a = 10;
```

### **What are global variables?**

- **Global variables** are variables declared outside any function and accessible **throughout the entire program**.
- In browsers, global variables are properties of the **`window` object**.
- Example:
```javascript
var globalVar = "I'm global";
console.log(window.globalVar); // Output: "I'm global"
```

### **What are the data types in JavaScript?**

- **Primitive Data Types (Immutable):**
  - `string`, `number`, `boolean`, `bigint`, `null`, `undefined`, `symbol`
- **Non-Primitive Data Type (Mutable):**
  - `object` (arrays, functions, sets, maps, etc.)

### **What is type coercion in JavaScript?**

- Type coercion is JavaScript’s **automatic conversion** of one data type into another.
- Example:
```javascript
console.log('5' + 3); // Output: "53" (string concatenation)
console.log('5' - 3); // Output: 2 (automatic number conversion)
```
- Use `parseInt()`, `parseFloat()`, or `Number()` for explicit conversions.

### **What is 'use strict' mode?**

- `"use strict"` enables **strict mode** in JavaScript to enforce better coding practices.
- Helps prevent **silent errors**, restricts **global variable declarations**, and disables **duplicate parameter names**.
- Declared at the beginning of a script or function:
```javascript
'use strict';
function test() {
  x = 10; // ReferenceError (undeclared variable)
}
test();
```

### **Difference between `==` and `===` operators.**

- `==` (Abstract Equality) **checks values** but performs **type conversion** if necessary.
- `===` (Strict Equality) checks **both value and type**.
- Example:
```javascript
console.log(5 == '5'); // Output: true (type conversion happens)
console.log(5 === '5'); // Output: false (different types)
```

- **What is the purpose of re-exporting modules in JavaScript?**

  - Allows combining multiple module exports into a single module.
  - Improves module organization and reduces import redundancy.

---

## **TypeScript Interview Questions**

- **What is TypeScript?**

  - A superset of JavaScript that adds static typing to the language. It is developed by Microsoft.
  - Adds features like type safety, interfaces, async/await, and compiles to JavaScript.
  - Angular is entirely written in TypeScript for better scalability and maintainability.

- **What is an abstract class in TypeScript and when would you use it?**

  - A class that cannot be instantiated directly but provides a blueprint for subclasses.
  - Defines common properties and methods for derived classes.

- **How do namespaces work in TypeScript?**

  - Used to organize code and prevent global scope pollution.
  - Groups related interfaces, functions, and classes together.

---
