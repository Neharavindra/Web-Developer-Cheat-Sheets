# 🚀 JavaScript and TypeScript Interview Cheat Sheet 🚀

### **1. What is JavaScript?**
- JavaScript (JS) is a synchronous, single-threaded language.
- It can execute only one command at a time in a specific order. 
- JavaScript is a scripting language used to make web pages interactive.
- It runs in the browser's execution environment but can also be used on the server-side via Node.js.

### **2. Explain execution context in JS.**
- The Execution Context is an environment where JavaScript code is executed.
- It contains the global object (`window` in browsers, `global` in Node.js).
- The Call Stack maintains the order of execution.
- Memory is allocated to all variables and functions before code execution starts.
- After execution, the global execution context is destroyed.
- Phases of execution context: 
1. **Creation Phase**
   - **Memory allocation** for variables and functions.
   - Variables get `undefined` (hoisting).
   - Functions are stored in memory.

2. **Execution Phase**
   - Code is executed line by line.
   - Variables are assigned values.
   - Functions are invoked.

### **3. What is Just-In-Time (JIT) compilation?**
- JIT compilation translates high-level language code into machine code at runtime.
- Commonly used in web browsers to improve performance.
- Unlike interpreted languages, JIT compiles and executes code simultaneously.

### **4. What are the data types in JavaScript?**
- **Primitive Data Types**: Boolean, number, string, BigInt, null, undefined, symbol.
- **Non-Primitive Data Types**: Object (arrays, functions, sets, maps, etc.).

### **5. What is type coercion in JavaScript?**
- JavaScript automatically converts data types during operations.
```javascript
console.log('5' + 3); // "53" (string concatenation)
console.log('5' - 3); // 2 (numeric conversion)
```

### **6. What are the different types of variable declarations in JS?**
- **`var`**: Function-scoped, can be redeclared and updated, hoisted.
- **`let`**: Block-scoped, cannot be redeclared in the same scope, hoisted but not initialized.
- **`const`**: Block-scoped, read-only, cannot be reassigned.

### **7. What are global variables?**
- Global variables are properties of the global object (`window` in browsers).

### **8. What is function scope?**
- Variables defined inside a function cannot be accessed outside the function.
- Functions have access to variables in their parent scope but not the other way around.

### **9. What are first-class functions?**
- Functions are treated like any other variable.
- Functions can be:
  - Assigned to a variable.
  - Passed as an argument to another function.
  - Returned from another function.

### **10. What are higher-order functions?**
- A higher-order function is a function that accepts another function as an argument or returns a function as a result.
- Allows reusability and abstraction.

### **11. What is function definition in JS?**
- A function definition (or function declaration) consists of the `function` keyword, a name, parameters, and function statements enclosed in curly braces.

### **12. What is the difference between a parameter and an argument?**
- A parameter is the variable in a function definition.
- An argument is the value passed to the function when invoked.

### **13. What are different kinds of function expressions in JS?**
- **Anonymous function expression**: A function without a name.
```javascript
const square = function(n) { return n * n; };
```
- **Named function expression**: A function with a name.
```javascript
const square = function squ(n) { return n * n; };
```

### **14. What is function hoisting?**
- JavaScript moves function declarations to the top of their scope.
- Only works with function declarations, not function expressions.

### **15. What are Immediately Invoked Function Expressions (IIFE)?**
- A function that executes immediately after it is defined.
```javascript
(function () { console.log("IIFE executed"); })();
```

### **16. What are arrow functions?**
- A shorter syntax for function expressions without their own `this`.
```javascript
const add = (a, b) => a + b;
```

### **17. What is the Temporal Dead Zone (TDZ)?**
- A variable declared with `let`, `const`, or `class` is in a Temporal Dead Zone (TDZ) from the start of the block until it is initialized.

### **18. What is hoisting in JS?**
- Hoisting moves variable and function declarations to the top of their scope before execution.
- Only declarations are hoisted, not value assignments.

### **19. What is 'use strict' mode?**
- Strict Mode allows you to write a code or a function in a "strict" operational environment.
-	Useful to write secure JS by notifying bad syntax.
- `"use strict"` Declared at the beginning of a script or function.

### **20. What is the difference between `==` and `===` operators?**
- `==` compares values and performs type conversion.
- `===` strictly compares both value and type.

### **21. What is a try-catch statement?**
- `try` contains code that may throw an error.
- `catch` handles errors if they occur.

### **22. What is the finally block?**
- The `finally` block always executes after `try` and `catch`, regardless of an error.

### **23. What is pass by value and pass by reference in JS?**
- Primitive types are passed by value (copied to a new memory location).
- Objects and arrays are passed by reference (point to the same memory location).

### **24. What are different kinds of statements for loops in JS?**
- **For**: Iterates over indexes as long as the condition is met.
- **Do-while**: Executes the statement before checking the condition.
- **While**: Executes the statement as long as the condition is true.
- **Label**: Names a loop to refer back to it later.
- **Break**: Stops execution of the nearest enclosing loop.
- **Continue**: Skips the current iteration and continues the next.
- **For-in**: Iterates over enumerable properties of an object.
- **For-of**: Iterates over iterable objects (arrays, strings, maps, sets, etc.).

### **25. What are closures?**
- A closure is a function that remembers variables from its parent scope even after the parent function has executed.
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

### **26. What is a rest parameter?**
- The rest parameter syntax allows a function to accept an indefinite number of arguments as an array.
```javascript
function sum(...numbers) {
  return numbers.reduce((acc, num) => acc + num, 0);
}
console.log(sum(1, 2, 3)); // Output: 6
```

### **27. What are template literals?**
- A way to define strings that allows embedding expressions and multi-line formatting.
```javascript
const name = "John";
console.log(`Hello, ${name}!`);
```

### **28. What is lexical scope?**
- The scope of a variable is determined by where it is declared, not where it is called.

### **29. What are the types of popup boxes available in JavaScript?**
- **Alert**: Displays a message.
- **Confirm**: Asks for user confirmation (OK/Cancel).
- **Prompt**: Asks for user input.

### **30. What is Event Loop & Microtask Queue?**
- Event Loop is a mechanism that allows JavaScript to execute asynchronous operations.
- It continuously checks the call stack to see if there are any functions to execute and if the call stack is empty, it checks the callback queue for events that need to be processed.
- Microtasks (Promises, `process.nextTick`) have higher priority and execute before callbacks (`setTimeout`, `setInterval`) from the queue.

### **31. What is the Fetch API?**
- The Fetch API is used for making HTTP requests.
```javascript
fetch('https://api.example.com/data')
  .then(response => response.json())
  .then(data => console.log(data));
```

### **32. What is Garbage Collection in JavaScript?**
- JavaScript automatically removes unused objects to free memory.
- Uses Mark-and-Sweep algorithm.

### **33. What is async/await in JavaScript?**
- `async` makes a function return a Promise.
- `await` pauses execution until the Promise resolves.
```javascript
async function fetchData() {
  let response = await fetch('https://api.example.com/data');
  let data = await response.json();
  console.log(data);
}
fetchData();
```

### **34. What is memory heap in JavaScript?**
- The heap is where JavaScript allocates objects and functions in memory.
- JavaScript manages memory using garbage collection.

### **35. What is currying in JavaScript?**
- Currying transforms a function with multiple arguments into a sequence of functions with single arguments.
```javascript
const add = a => b => c => a + b + c;
console.log(add(1)(2)(3)); // 6
```

### **36. What is a Promise in JavaScript?**
- A Promise represents a future value.
- Can be in pending, fulfilled, or rejected states.
- Used to handle asynchronous operations.

### **37. What is the difference between synchronous and asynchronous code in JavaScript?**
- **Synchronous code** runs line by line.
- **Asynchronous code** runs independently, allowing execution of other tasks.

### **38. What is a shallow copy vs. deep copy?**
- **Shallow Copy**: Copies only the first-level properties, keeping references to nested objects.
- **Deep Copy**: Copies all nested objects recursively, creating independent clones.

### **39. What is the difference between call, apply, and bind methods?**
- `call()` invokes a function with individual arguments.
- `apply()` invokes a function with an array of arguments.
- `bind()` returns a new function with a specific `this` value.

### **40. What is memoization in JavaScript?**
- Memoization caches function results to improve performance.
```javascript
const memoizedAdd = () => {
  let cache = {};
  return (num) => cache[num] || (cache[num] = num + 10);
};
```

### **41. What is the purpose of re-exporting modules in JavaScript?**
  - Allows combining multiple module exports into a single module.
  - Improves module organization and reduces import redundancy.

### **42. What is debouncing in JavaScript?**
  - Debouncing is a technique used to delay function execution until a certain time has passed since the last event.
  - Instead of calling a function every time an event (like keypress or scroll) occurs, debouncing waits for a pause before executing the function.

### **43. What are Callback Functions in JavaScript?**
- A callback function is a function that is passed as an argument to another function and executed later.
- It allows handling asynchronous operations, ensuring that code runs after a task completes.
- Used in event listeners, timers (`setTimeout`, `setInterval`), and API calls (`fetch`, `XMLHttpRequest`).
```javascript
function fetchData(callback) {
  setTimeout(() => {
    console.log("Data fetched");
    callback();
  }, 2000);
}
function processData() {
  console.log("Processing data");
}
fetchData(processData);
```

### **44. What is Callback Queue in JavaScript?**
- **Callback Queue** stores asynchronous callbacks that are waiting to be executed.
- Callbacks from `setTimeout`, `setInterval`, and I/O tasks go into the Callback Queue.
- **How it works:**
  - The Call Stack must be empty before a callback from the queue is executed.
  - The Event Loop continuously checks for pending tasks in the queue.
```javascript
console.log("Start");
setTimeout(() => console.log("Callback executed"), 0);
console.log("End");
```
**Output:**
```
Start
End
Callback executed
```
- Even though `setTimeout` has a `0ms` delay, it moves to the Callback Queue and executes after the main thread is free.

### **45. What is the difference between `let` and `var` in JavaScript?**
1. **Scope**  
   - `var` is function-scoped, meaning it is accessible throughout the function in which it is declared.  
   - `let` is block-scoped, meaning it is only accessible within the block `{}` in which it is declared.  
2. **Hoisting**  
   - Variables declared with `var` are hoisted to the top of their scope and initialized with `undefined`.  
   - Variables declared with `let` are hoisted but not initialized, leading to a Temporal Dead Zone (TDZ) until they are assigned a value.  
3. **Redeclaration**  
   - `var` allows redeclaration within the same scope without errors.  
   - `let` does not allow redeclaration in the same scope and will throw an error.  
4. **Global Object Property**  
   - `var` declarations at the global level create a property on the `window` object (in browsers).  
   - `let` does not create a property on the global object.  
```javascript
function example() {
    console.log(a); // undefined
    console.log(b); // ReferenceError: Cannot access 'b' before initialization

    var a = 10;
    let b = 20;
}
```

### **46. Explain map, reduce and filter in JavaScript?**
- **map**: 
- Used to transform each element in an array and return a new array.
- Does not modify the original array.
```javascript
  const numbers = [1, 2, 3, 4];
  const doubled = numbers.map(num => num * 2);
  console.log(doubled); // [2, 4, 6, 8]
```
- **filter**:
- Used to filter elements based on a condition.
- Returns a new array with elements that satisfy the condition.
```javascript
  const numbers = [1, 2, 3, 4, 5, 6];
  const evens = numbers.filter(num => num % 2 === 0);
  console.log(evens); // [2, 4, 6]
```
- **reduce**: 
- Used to reduce an array to a single value (sum, product, average, etc.).
- Takes a callback function with an accumulator and the current value.
```javascript
  const numbers = [1, 2, 3, 4];
  const sum = numbers.reduce((acc, num) => acc + num, 0);
  console.log(sum); // 10
```
- Using all three together
```javascript
  const numbers = [1, 2, 3, 4, 5, 6];
  const result = numbers
    .filter(num => num % 2 === 0)  // [2, 4, 6]
    .map(num => num * num)         // [4, 16, 36]
    .reduce((sum, num) => sum + num, 0); // 4 + 16 + 36 = 56
  console.log(result); // 56
```

### **47. What is ECMAScript?**
- ECMAScript (ES) is the standardized specification for JavaScript, maintained by ECMA International.
- It defines the core features of JavaScript, ensuring consistency across different implementations such as browsers and Node.js.

### **48. What is the difference between ECMAScript and JavaScript?**
- ECMAScript is the standard that defines how JavaScript should work. JavaScript is the implementation of ECMAScript in browsers and other environments.

### **49. What is the purpose of the `spread` (`...`) and `rest` (`...`) operators?**
- **Spread Operator (`...`)** – Expands arrays or objects into individual elements.  
  ```javascript
  const arr = [1, 2, 3];
  const newArr = [...arr, 4, 5]; // [1, 2, 3, 4, 5]
  ```
- **Rest Operator (`...`)** – Gathers multiple arguments into an array. 
  ```javascript
  function sum(...numbers) {
    return numbers.reduce((acc, num) => acc + num, 0);
  }
  console.log(sum(1, 2, 3, 4)); // 10
  ```

### **50: What is optional chaining (?.) in ECMAScript?**
- Optional chaining allows safe access to deeply nested object properties without checking if intermediate properties exist.
```javascript
  const user = { profile: { name: "John" } };
  console.log(user.profile?.name); // "John"
  console.log(user.address?.city); // undefined (instead of an error)
```

### **51. What is the difference between null and undefined?**
- **null** – Explicitly set value, representing the absence of an object.
- **undefined** – A variable that has been declared but not assigned a value.

### **52. What is the Promise.all() method?**
- Promise.all() takes multiple promises and resolves when all promises are fulfilled or rejects if one fails.
```javascript
  const p1 = Promise.resolve(10);
  const p2 = new Promise((resolve) => setTimeout(() => resolve(20), 1000));
  const p3 = Promise.resolve(30);
  Promise.all([p1, p2, p3]).then(console.log); // [10, 20, 30] after 1 second
```

### **53. What is `this` in JavaScript?** 
- `this` refers to the object that is currently executing the function.
- Its value depends on how and where the function is called.
  
| **Context**                             | **`this` Refers To**                          |
| -------------------------------------- | -------------------------------------------- |
| **Global Scope**                        | `window` (in browser) / `global` (in Node.js) |
| **Function (Non-strict mode)**          | `window` (in browsers)                        |
| **Function (Strict mode)**              | `undefined`                                   |
| **Object Method**                       | The calling object                            |
| **Arrow Function**                      | Inherited `this` from parent scope            |
| **Constructor Function**                | The new instance object                       |
| **Event Listener**                      | The DOM element that triggered the event      |
| **Using `call()`, `apply()`, `bind()`** | Explicitly set object                         |

### **54. What is scope chaining in JavaScript?**
- Scope chaining is the process where nested functions can access variables from their parent functions.
- If a variable is not found in the current scope, JavaScript looks up the scope chain until it reaches the global scope.
- Used in closures to maintain access to outer variables.
```javascript
function outer() {
  let a = 10;
  function inner() {
    console.log(a); // Accesses 'a' from outer function
  }
  inner();
}
outer(); // Output: 10
```

### **55. Difference between scope chaining and closure?**

|Feature |	Scope Chaining	| Closure |
| ------ | --------------- | -------- |
| Definition |	The mechanism where nested functions can access variables from their outer scopes.  Variables flow downward (from parent to child). |	A function retaining access to its lexical scope even after the outer function has returned. Inner function "remembers" outer variables even after execution.|
| Access Scope	| Inner functions can access variables of parent functions and the global scope. |	Even after the parent function executes and is removed from the stack, the inner function still remembers and can use its parent's variables. |
| When It Occurs |	Happens whenever functions are nested inside another function. |	Happens when an inner function is returned from an outer function. |
| Use Case	| Used for organizing code and variable access in a structured way. |	Used for data privacy, function factories, and maintaining state across function calls. |
| Key Benefit	| Allows functions to access variables from parent scopes for modularity. |	Helps in data encapsulation and preserving state. |


### **56. What is shadowing in JavaScript?**
- Shadowing occurs when a variable in the inner scope has the same name as a variable in the outer scope.
- The inner variable overrides the outer variable within its scope.
```javascript
let x = "Global";
function test() {
  let x = "Local"; // Shadows global 'x'
  console.log(x);
}
test(); // Output: Local
console.log(x); // Output: Global
```

### **57. What is TypeScript?**
- A superset of JavaScript that adds static typing to the language. It is developed by Microsoft.
- Adds features like type safety, interfaces, async/await, and compiles to JavaScript.
- Angular is entirely written in TypeScript for better scalability and maintainability.

### **58. What is an abstract class in TypeScript and when would you use it?**
- A class that cannot be instantiated directly but provides a blueprint for subclasses.
- Defines common properties and methods for derived classes.

### **59. How do namespaces work in TypeScript?**
- Used to organize code and prevent global scope pollution.
- Groups related interfaces, functions, and classes together.

### **60. What are the data types in TypeScript?**
- TypeScript supports static typing with the following data types:
1. **Primitive Types:** number, string, boolean, bigint, null, undefined, symbol.
2. **Object Types:** Array, Tuple, Object.
3. **Special Types:** any, void, never, unknown.

### **61. What is type casting?**
- Type casting allows converting one type to another using:
- **Angle-bracket syntax**: `<Type>variable`
- **as keyword**: `variable as Type`

### **62. How do functions work in typescript?**
- Functions in TypeScript support parameter types, return types, optional parameters, and default values.

### **63. What is class visibility in TypeScript?**
- TypeScript uses access modifiers to control visibility:
1. **public**: Accessible everywhere (default).
2. **private**: Accessible only inside the class.
3. **protected**: Accessible inside the class and subclasses.

### **64. What are ES6 features?**
1. **let & const** (Block-Scoped Variables)
- let → Block-scoped, re-assignable.
- const → Block-scoped, cannot be reassigned.
2. **Arrow Functions (=>)**
- Shorter function syntax.
- Does not have its own this context.
3. **Template Literals (````)**
- Supports multi-line strings.
- Allows embedded expressions using ${}.
4. **Default Parameters**
- Assigns default values to function parameters.
5. **Destructuring Assignment**
- Extracts values from arrays/objects easily.
```javascript
const { name, age } = { name: "Alice", age: 25 };
```
6. **Spread & Rest Operators (...)**
- Spread (...) → Expands elements of an array/object.
- Rest (...) → Collects remaining elements into an array.
7. **Classes & Inheritance**
- Supports Object-Oriented Programming (OOP).
- `class` and `extends` for modular code.
8. **Modules (import/export)**
- Enables code modularity & reusability.
```javascript
export function square(x) { return x * x; }
import { square } from './math.js';
```
9. **Promises (async/await)**
- Handles asynchronous operations efficiently.
- Avoids callback hell.
10. **Map & Set**
- Map → Stores key-value pairs with unique keys.
- Set → Stores unique values only.

---
