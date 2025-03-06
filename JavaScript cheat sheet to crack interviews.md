# JavaScript and TypeScript Interview Questions Cheat Sheet

## **JavaScript Interview Questions**

### **1. What is JavaScript?**
- JavaScript (JS) is a **synchronous, single-threaded** language.
- It can execute only one command at a time in a specific order. 
- JavaScript is a **scripting language** used to make web pages interactive.
- It runs in the **browser's execution environment** but can also be used on the **server-side** via Node.js.

### **2. Explain execution context in JS.**
- Everything happens in an **execution context**. 
- JavaScript first creates a **memory environment (variable environment)** and then executes code (**thread of execution**).
- After execution, the **global execution context is destroyed**.
- The **Call Stack** maintains the order of execution.
- Memory is allocated to all variables and functions before code execution starts.

### **3. What is Just-In-Time (JIT) compilation?**
- JIT compilation translates high-level language code into machine code **at runtime**.
- Commonly used in web browsers to **improve performance**.
- Unlike interpreted languages, JIT compiles and executes code **simultaneously**.

### **4. What are first-class functions?**
- Functions are treated like **any other variable**.
- Functions can be:
  - **Assigned to a variable**.
  - **Passed as an argument** to another function.
  - **Returned from another function**.

### **5. What are higher-order functions?**
- A **higher-order function** is a function that **accepts another function as an argument** or **returns a function as a result**.
- Allows **reusability and abstraction**.

### **6. What are the different types of variable declarations in JS?**
- **`var`**: Function-scoped, can be **redeclared** and **updated**, hoisted.
- **`let`**: Block-scoped, cannot be redeclared in the same scope, hoisted but **not initialized**.
- **`const`**: Block-scoped, **read-only**, cannot be reassigned.

### **7. What is hoisting in JS?**
- Hoisting moves **variable and function declarations** to the **top of their scope** before execution.
- Only **declarations** are hoisted, not value assignments.

### **8. What is the Temporal Dead Zone (TDZ)?**
- A variable declared with `let`, `const`, or `class` is in a **Temporal Dead Zone (TDZ)** from the start of the block until it is initialized.

### **9. What are global variables?**
- Global variables are **properties of the global object** (`window` in browsers).

### **10. What are the data types in JavaScript?**
- **Primitive Data Types**: Boolean, number, string, BigInt, null, undefined, symbol.
- **Non-Primitive Data Types**: Object (arrays, functions, sets, maps, etc.).

### **11. What is type coercion in JavaScript?**
- JavaScript automatically converts data types **during operations**.
- Example:
```javascript
console.log('5' + 3); // "53" (string concatenation)
console.log('5' - 3); // 2 (numeric conversion)
```

### **12. What is 'use strict' mode?**
- `"use strict"` enforces better coding practices.
- Prevents accidental global variables.
- Declared at the beginning of a script or function.

### **13. What is the difference between `==` and `===` operators?**
- `==` **compares values** and performs **type conversion**.
- `===` **strictly compares** both **value and type**.

### **14. What is a try-catch statement?**
- `try` contains code that may throw an error.
- `catch` handles errors if they occur.

### **15. What is the finally block?**
- The `finally` block **always executes** after `try` and `catch`, regardless of an error.

### **16. What is pass by value and pass by reference in JS?**
- **Primitive types** are passed **by value** (copied to a new memory location).
- **Objects and arrays** are passed **by reference** (point to the same memory location).

### **14. What are different kinds of statements for loops in JS?**
- **For**: Iterates over indexes as long as the condition is met.
- **Do-while**: Executes the statement before checking the condition.
- **While**: Executes the statement as long as the condition is true.
- **Label**: Names a loop to refer back to it later.
- **Break**: Stops execution of the nearest enclosing loop.
- **Continue**: Skips the current iteration and continues the next.
- **For-in**: Iterates over enumerable properties of an object.
- **For-of**: Iterates over iterable objects (arrays, strings, maps, sets, etc.).

### **15. What is function definition in JS?**
- A function definition (or function declaration) consists of the `function` keyword, a name, parameters, and function statements enclosed in curly braces.

### **16. What is the difference between a parameter and an argument?**
- A **parameter** is the variable in a function definition.
- An **argument** is the value passed to the function when invoked.

### **17. What are different kinds of function expressions in JS?**
- **Anonymous function expression**: A function without a name.
```javascript
const square = function(n) { return n * n; };
```
- **Named function expression**: A function with a name.
```javascript
const square = function squ(n) { return n * n; };
```

### **18. What is function hoisting?**
- JavaScript moves function declarations to the top of their scope.
- Only works with **function declarations**, not function expressions.

### **19. What are Immediately Invoked Function Expressions (IIFE)?**
- A function that executes immediately after it is defined.
```javascript
(function () { console.log("IIFE executed"); })();
```

### **20. What is function scope?**
- Variables defined inside a function **cannot be accessed outside the function**.
- Functions have access to variables in their **parent scope** but not the other way around.

### **21. What are closures?**
- A closure is a function that remembers variables from its parent scope even after the parent function has executed.
- Example:
```javascript
function outer() {
  let count = 0;
  return function inner() {
    count++;
    console.log(count);
  };
}
const counter = outer();
counter(); // Output: 1
```

### **22. What is a rest parameter?**
- The rest parameter syntax allows a function to accept an **indefinite number of arguments** as an array.
```javascript
function sum(...numbers) {
  return numbers.reduce((acc, num) => acc + num, 0);
}
console.log(sum(1, 2, 3)); // Output: 6
```

### **23. What are arrow functions?**
- A shorter syntax for function expressions without their own `this`.
```javascript
const add = (a, b) => a + b;
```

### **24. What are template literals?**
- A way to define strings that allows embedding expressions and multi-line formatting.
```javascript
const name = "John";
console.log(`Hello, ${name}!`);
```

### **25. What is lexical scope?**
- The scope of a variable is determined by **where it is declared**, not where it is called.

### **26. What are the types of popup boxes available in JavaScript?**
- **Alert**: Displays a message.
- **Confirm**: Asks for user confirmation (OK/Cancel).
- **Prompt**: Asks for user input.

---

This document provides **comprehensive JavaScript interview questions and answers**, covering functions, loops, closures, and scope. Let me know if you'd like modifications! 🚀



### **27. What is the Event Loop & Microtask Queue?**
- The **Event Loop** handles **asynchronous operations**.
- **Microtasks (Promises, MutationObserver)** run **before Macrotasks** (`setTimeout`, `setInterval`).

### **28. What is the Fetch API?**
- The Fetch API is used for making **HTTP requests**.
- Example:
```javascript
fetch('https://api.example.com/data')
  .then(response => response.json())
  .then(data => console.log(data));
```

### **29. What is Garbage Collection in JavaScript?**
- JavaScript **automatically removes unused objects** to free memory.
- Uses **Mark-and-Sweep** algorithm.

### **30. What is async/await in JavaScript?**
- `async` makes a function return a **Promise**.
- `await` pauses execution **until the Promise resolves**.
- Example:
```javascript
async function fetchData() {
  let response = await fetch('https://api.example.com/data');
  let data = await response.json();
  console.log(data);
}
fetchData();
```

### **31. What is memory heap in JavaScript?**
- The **heap** is where JavaScript **allocates objects and functions** in memory.
- JavaScript manages memory using **garbage collection**.

### **32. What is currying in JavaScript?**
- Currying transforms a function with multiple arguments into a sequence of functions.
- Example:
```javascript
const add = a => b => c => a + b + c;
console.log(add(1)(2)(3)); // 6
```

### **33. What is a Promise in JavaScript?**
- A Promise represents a **future value**.
- Can be in **pending, fulfilled, or rejected** states.
- Used to **handle asynchronous operations**.

### **34. What is the difference between synchronous and asynchronous code in JavaScript?**
- **Synchronous code** runs line by line.
- **Asynchronous code** runs independently, allowing execution of other tasks.

### **35. What is a shallow copy vs. deep copy?**
- **Shallow Copy**: Copies only the first-level properties, keeping references to nested objects.
- **Deep Copy**: Copies all nested objects recursively, creating **independent clones**.

### **36. What is the difference between call, apply, and bind methods?**
- `call()` invokes a function with individual arguments.
- `apply()` invokes a function with an array of arguments.
- `bind()` returns a new function with a specific `this` value.

### **37. What is memoization in JavaScript?**
- Memoization **caches function results** to improve performance.
- Example:
```javascript
const memoizedAdd = () => {
  let cache = {};
  return (num) => cache[num] || (cache[num] = num + 10);
};
```

### **38. What is the purpose of re-exporting modules in JavaScript?**

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
