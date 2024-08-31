# JavaScript Concepts

Visit website for better experience - [Link](https://siddhu123m.github.io/JS-concepts/)

This repository contains a Markdown file that explains various JavaScript concepts with examples and detailed explanations. The concepts covered include object inheritance using `Object.create`, modules for organizing and reusing code, and the technique of currying functions## Introduction

The `jsConcepts.md` file in this repository provides detailed explanations and examples of several advanced JavaScript concepts. This is a great resource for developers looking to deepen their understanding of JavaScript and its capabilities.

---

### JavaScript Concepts

- [Setter & Getter](#setter--getter)
- [Destructuring](#destructuring)
- [Rest Operator](#rest-operator)
- [Spread Operator](#spread-operator)
- [setInterval](#setinterval)
- [Break, Continue, Return](#break-continue-return)
- [Object Methods](#object-methods)
- [Factory Function](#factory-function)
- [Object Destructuring](#object-destructuring)
- [Export & Export Default](#export--export-default)
- [Defer Attribute](#defer-attribute)
- [Async Attribute](#async-attribute)
- [Call Stack](#call-stack)
- [Hoisting](#hoisting)
- [Closures](#closures)
- [Promises](#promises)
- [Async/Await](#asyncawait)
- [Event Loop](#event-loop)
- [IIFE (Immediately Invoked Function Expression)](#iife-immediately-invoked-function-expression)
- [this Keyword](#this-keyword)
- [Prototypes](#prototypes)
- [Modules](#modules)
- [Event Delegation](#event-delegation)
- [Debouncing](#debouncing)
- [Throttling](#throttling)
- [Currying](#currying)
- [Higher-Order Functions](#higher-order-functions)
- [Polyfills](#polyfills)
- [Memoization](#memoization)
- [Promises vs. Callbacks](#promises-vs-callbacks)
- [ES6 Classes](#es6-classes)
- [Event Loop and Message Queue](#event-loop-and-message-queue)
- [Promises and Async/Await](#promises-and-asyncawait)
- [Prototypal Inheritance](#prototypal-inheritance)
- [Debouncing and Throttling](#debouncing-and-throttling)

#### Setter & Getter
Setters and getters are special methods that provide a way to access and update the properties of an object.

**Example:**

```javascript
const person = {
  firstName: 'Mosh',
  lastName: 'Hamedani',
  get fullName() {
    return `${this.firstName} ${this.lastName}`;
  },
  set fullName(value) {
    const parts = value.split(' ');
    this.firstName = parts[0];
    this.lastName = parts[1];
  }
};

person.fullName = 'John Smith';
console.log(person); // { firstName: 'John', lastName: 'Smith' }
```

**Explanation:**
- **Getter**: The `get` keyword defines a getter method to access the `fullName` property.
- **Setter**: The `set` keyword defines a setter method to update the `fullName` property.

#### Destructuring
Destructuring allows you to unpack values from arrays or properties from objects into distinct variables.

**Example:**

```javascript
const person = { firstName: 'John', lastName: 'Doe' };
const { firstName, lastName } = person;
console.log(firstName); // John
console.log(lastName); // Doe
```

**Explanation:**
- The `{ firstName, lastName }` syntax extracts `firstName` and `lastName` from the `person` object.

#### Rest Operator
The rest operator (`...`) allows you to represent an indefinite number of elements as an array.

**Example:**

```javascript
function sum(...numbers) {
  return numbers.reduce((acc, num) => acc + num, 0);
}

console.log(sum(1, 2, 3)); // 6
```

**Explanation:**
- The `...numbers` syntax collects all arguments into an array called `numbers`.

#### Spread Operator
The spread operator (`...`) allows an iterable such as an array to be expanded in places where zero or more arguments or elements are expected.

**Example:**

```javascript
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5, 6];
console.log(arr2); // [1, 2, 3, 4, 5, 6]
```

**Explanation:**
- The `...arr1` syntax spreads the elements of `arr1` into `arr2`.

#### setInterval
`setInterval` is a method that repeatedly calls a function or executes a code snippet, with a fixed time delay between each call.

**Example:**

```javascript
setInterval(() => {
  console.log('Hello, world!');
}, 1000);
```

**Explanation:**
- This code logs "Hello, world!" to the console every second.

#### Break, Continue, Return
- **Break**: Terminates the current loop, switch, or label statement.
- **Continue**: Skips the rest of the current loop iteration and proceeds to the next iteration.
- **Return**: Exits from the current function and returns a value.

**Example:**

```javascript
for (let i = 0; i < 5; i++) {
  if (i === 3) break;
  console.log(i); // 0, 1, 2
}

for (let i = 0; i < 5; i++) {
  if (i === 3) continue;
  console.log(i); // 0, 1, 2, 4
}

function greet() {
  return 'Hello!';
}
console.log(greet()); // Hello!
```

#### Object Methods
- **assign**: Copies all enumerable own properties from one or more source objects to a target object.
- **entries**: Returns an array of a given object's own enumerable string-keyed property [key, value] pairs.
- **keys**: Returns an array of a given object's own enumerable property names.

**Example:**

```javascript
const target = { a: 1 };
const source = { b: 2 };
const returnedTarget = Object.assign(target, source);
console.log(returnedTarget); // { a: 1, b: 2 }

const obj = { a: 1, b: 2 };
console.log(Object.entries(obj)); // [['a', 1], ['b', 2]]
console.log(Object.keys(obj)); // ['a', 'b']
```

#### Factory Function
A factory function is a function that returns a new object each time it is called.

**Example:**

```javascript
function createPerson(firstName, lastName) {
  return {
    firstName,
    lastName,
    fullName() {
      return `${firstName} ${lastName}`;
    }
  };
}

const person = createPerson('John', 'Doe');
console.log(person.fullName()); // John Doe
```

#### Object Destructuring
Object destructuring allows you to extract properties from an object and bind them to variables.

**Example:**

```javascript
const person = { firstName: 'John', lastName: 'Doe' };
const { firstName, lastName } = person;
console.log(firstName); // John
console.log(lastName); // Doe
```

#### Export & Export Default
- **Export**: Used to export functions, objects, or primitives from a given file or module.
- **Export Default**: Used to export a single value or to have a fallback value for your module.

**Example:**

```javascript
// module.js
export const name = 'John';
export default function greet() {
  return 'Hello!';
}

// main.js
import greet, { name } from './module';
console.log(greet()); // Hello!
console.log(name); // John
```

#### Defer Attribute
The `defer` attribute in HTML tells the browser to download the script file during HTML parsing and execute it after the HTML is completely parsed.

**Example:**

```html
<script src="script.js" defer></script>
```

**Explanation:**
- The script is downloaded during HTML parsing but executed after the HTML is fully parsed.

#### Async Attribute
The `async` attribute in HTML tells the browser to download the script file during HTML parsing and execute it as soon as it is downloaded.

**Example:**

```html
<script src="script.js" async></script>
```

**Explanation:**
- The script is downloaded during HTML parsing and executed as soon as it is available.

Sure! Here are some more important JavaScript topics with detailed explanations and simple syntax examples:

#### Call Stack
The call stack is a mechanism for an interpreter to keep track of its place in a script that calls multiple functions.

**Example:**

```javascript
function firstFunction() {
  secondFunction();
  console.log('First Function');
}

function secondFunction() {
  console.log('Second Function');
}

firstFunction();
// Output:
// Second Function
// First Function
```

**Explanation:**
- The call stack keeps track of function calls. When `firstFunction` calls `secondFunction`, `secondFunction` is added to the stack. After `secondFunction` completes, it is removed from the stack, and `firstFunction` continues.

#### Hoisting
Hoisting is JavaScript's default behavior of moving declarations to the top of the current scope.

**Example:**

```javascript
console.log(hoistedVar); // undefined
var hoistedVar = 'This is hoisted';
```

**Explanation:**
- Variable declarations (`var`) are hoisted to the top of their scope, but their assignments are not. Hence, `hoistedVar` is `undefined` when logged.

#### Closures
A closure is a function that retains access to its lexical scope, even when the function is executed outside that scope.

**Example:**

```javascript
function outerFunction() {
  const outerVar = 'I am outside!';
  
  function innerFunction() {
    console.log(outerVar);
  }
  
  return innerFunction;
}

const myFunction = outerFunction();
myFunction(); // I am outside!
```

**Explanation:**
- `innerFunction` retains access to `outerVar` even after `outerFunction` has finished executing.

#### Promises
Promises represent the eventual completion (or failure) of an asynchronous operation and its resulting value.

**Example:**

```javascript
const myPromise = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve('Promise resolved!');
  }, 1000);
});

myPromise.then((message) => {
  console.log(message); // Promise resolved!
});
```

**Explanation:**
- A `Promise` is created and resolved after 1 second. The `then` method is used to handle the resolved value.

#### Async/Await
`async` and `await` are syntactic sugar built on top of promises, making asynchronous code easier to write and read.

**Example:**

```javascript
async function fetchData() {
  const response = await fetch('https://api.example.com/data');
  const data = await response.json();
  console.log(data);
}

fetchData();
```

**Explanation:**
- The `await` keyword pauses the execution of the `fetchData` function until the `fetch` promise is resolved.

#### Event Loop
The event loop is a mechanism that allows JavaScript to perform non-blocking operations by offloading operations to the system kernel whenever possible.

**Example:**

```javascript
console.log('Start');

setTimeout(() => {
  console.log('Timeout');
}, 0);

console.log('End');
// Output:
// Start
// End
// Timeout
```

**Explanation:**
- The `setTimeout` callback is executed after the synchronous code, demonstrating the event loop's handling of asynchronous operations.

#### IIFE (Immediately Invoked Function Expression)
An IIFE is a function that runs as soon as it is defined.

**Example:**

```javascript
(function() {
  console.log('IIFE executed!');
})();
```

**Explanation:**
- The function is defined and immediately invoked, running the code inside it.

#### this Keyword
The `this` keyword refers to the object it belongs to.

**Example:**

```javascript
const person = {
  name: 'John',
  greet() {
    console.log(`Hello, my name is ${this.name}`);
  }
};

person.greet(); // Hello, my name is John
```

**Explanation:**
- In the `greet` method, `this` refers to the `person` object.

#### Prototypes
Prototypes are the mechanism by which JavaScript objects inherit features from one another.

**Example:**

```javascript
function Person(name) {
  this.name = name;
}

Person.prototype.greet = function() {
  console.log(`Hello, my name is ${this.name}`);
};

const john = new Person('John');
john.greet(); // Hello, my name is John
```

**Explanation:**
- The `greet` method is added to `Person`'s prototype, making it available to all instances of `Person`.

#### Modules
Modules are a way to organize and reuse code by exporting and importing functions, objects, or primitives.

**Example:**

```javascript
// module.js
export const name = 'John';
export function greet() {
  return 'Hello!';
}

// main.js
import { name, greet } from './module';
console.log(greet()); // Hello!
console.log(name); // John
```

**Explanation:**
- The `name` and `greet` are exported from `module.js` and imported into `main.js`.

Sure! Here are some more important JavaScript topics with detailed explanations and simple syntax examples:

#### Event Delegation
Event delegation is a technique involving adding a single event listener to a parent element to manage events for multiple child elements.

**Example:**

```javascript
document.getElementById('parent').addEventListener('click', function(event) {
  if (event.target && event.target.matches('button.class-name')) {
    console.log('Button clicked!');
  }
});
```

**Explanation:**
- The event listener is added to the parent element, and it checks if the event target matches the specified selector.

#### Debouncing
Debouncing is a technique to limit the rate at which a function is executed.

**Example:**

```javascript
function debounce(func, delay) {
  let debounceTimer;
  return function() {
    const context = this;
    const args = arguments;
    clearTimeout(debounceTimer);
    debounceTimer = setTimeout(() => func.apply(context, args), delay);
  };
}

const handleResize = debounce(() => {
  console.log('Resized!');
}, 500);

window.addEventListener('resize', handleResize);
```

**Explanation:**
- The `debounce` function ensures that the `handleResize` function is called only after 500 milliseconds have passed since the last resize event.

#### Throttling
Throttling is a technique to ensure a function is executed at most once in a specified time period.

**Example:**

```javascript
function throttle(func, limit) {
  let lastFunc;
  let lastRan;
  return function() {
    const context = this;
    const args = arguments;
    if (!lastRan) {
      func.apply(context, args);
      lastRan = Date.now();
    } else {
      clearTimeout(lastFunc);
      lastFunc = setTimeout(() => {
        if (Date.now() - lastRan >= limit) {
          func.apply(context, args);
          lastRan = Date.now();
        }
      }, limit - (Date.now() - lastRan));
    }
  };
}

const handleScroll = throttle(() => {
  console.log('Scrolled!');
}, 1000);

window.addEventListener('scroll', handleScroll);
```

**Explanation:**
- The `throttle` function ensures that the `handleScroll` function is called at most once every 1000 milliseconds during scrolling.

#### Currying
Currying is a technique of evaluating a function with multiple arguments, transforming it into a sequence of functions with a single argument.

**Example:**

```javascript
function curry(func) {
  return function curried(...args) {
    if (args.length >= func.length) {
      return func.apply(this, args);
    } else {
      return function(...args2) {
        return curried.apply(this, args.concat(args2));
      };
    }
  };
}

function add(a, b) {
  return a + b;
}

const curriedAdd = curry(add);
console.log(curriedAdd(1)(2)); // 3
```

**Explanation:**
- The `curry` function transforms the `add` function into a sequence of functions that can be called with a single argument.

#### Higher-Order Functions
Higher-order functions are functions that take other functions as arguments or return functions as their result.

**Example:**

```javascript
function higherOrderFunction(callback) {
  return function() {
    return callback();
  };
}

function sayHello() {
  return 'Hello!';
}

const greet = higherOrderFunction(sayHello);
console.log(greet()); // Hello!
```

**Explanation:**
- The `higherOrderFunction` takes `sayHello` as an argument and returns a new function that calls `sayHello`.

#### Polyfills
Polyfills are pieces of code (usually JavaScript on the web) used to provide modern functionality on older browsers that do not natively support it.

**Example:**

```javascript
if (!Array.prototype.includes) {
  Array.prototype.includes = function(element) {
    return this.indexOf(element) !== -1;
  };
}

const arr = [1, 2, 3];
console.log(arr.includes(2)); // true
```

**Explanation:**
- This polyfill adds the `includes` method to `Array.prototype` if it does not already exist.

#### Memoization
Memoization is an optimization technique to speed up function calls by caching the results of expensive function calls.

**Example:**

```javascript
function memoize(fn) {
  const cache = {};
  return function(...args) {
    const key = JSON.stringify(args);
    if (cache[key]) {
      return cache[key];
    } else {
      const result = fn.apply(this, args);
      cache[key] = result;
      return result;
    }
  };
}

function slowFunction(num) {
  for (let i = 0; i < 1e9; i++) {} // Simulate a slow computation
  return num * 2;
}

const memoizedSlowFunction = memoize(slowFunction);
console.log(memoizedSlowFunction(5)); // Slow computation
console.log(memoizedSlowFunction(5)); // Fast computation (cached)
```

**Explanation:**
- The `memoize` function caches the results of `slowFunction` to avoid redundant computations.

#### Promises vs. Callbacks
Promises and callbacks are both used to handle asynchronous operations, but promises provide a more powerful and flexible way to manage asynchronous code.

**Example:**

```javascript
// Callback
function fetchData(callback) {
  setTimeout(() => {
    callback('Data fetched');
  }, 1000);
}

fetchData((data) => {
  console.log(data); // Data fetched
});

// Promise
function fetchDataPromise() {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve('Data fetched');
    }, 1000);
  });
}

fetchDataPromise().then((data) => {
  console.log(data); // Data fetched
});
```

**Explanation:**
- Promises provide a cleaner and more manageable way to handle asynchronous operations compared to callbacks.

#### ES6 Classes
ES6 classes provide a more intuitive and syntactically cleaner way to create objects and handle inheritance in JavaScript.

**Example:**

```javascript
class Person {
  constructor(name) {
    this.name = name;
  }

  greet() {
    console.log(`Hello, my name is ${this.name}`);
  }
}

const john = new Person('John');
john.greet(); // Hello, my name is John
```

**Explanation:**
- The `class` syntax is used to define a `Person` class with a constructor and a `greet` method.


#### Event Loop and Message Queue
The event loop is a mechanism that allows JavaScript to perform non-blocking operations by offloading operations to the system kernel whenever possible.

**Example:**

```javascript
console.log('Start');

setTimeout(() => {
  console.log('Timeout');
}, 0);

console.log('End');
// Output:
// Start
// End
// Timeout
```

**Explanation:**
- The `setTimeout` callback is executed after the synchronous code, demonstrating the event loop's handling of asynchronous operations.

#### Promises and Async/Await
Promises represent the eventual completion (or failure) of an asynchronous operation and its resulting value. `async` and `await` are syntactic sugar built on top of promises, making asynchronous code easier to write and read.

**Example:**

```javascript
// Using Promises
function fetchData() {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve('Data fetched');
    }, 1000);
  });
}

fetchData().then((data) => {
  console.log(data); // Data fetched
});

// Using Async/Await
async function fetchDataAsync() {
  const data = await fetchData();
  console.log(data); // Data fetched
}

fetchDataAsync();
```

**Explanation:**
- Promises provide a cleaner and more manageable way to handle asynchronous operations compared to callbacks.
- `async` and `await` make asynchronous code look synchronous, improving readability.

#### Closures
A closure is a function that retains access to its lexical scope, even when the function is executed outside that scope.

**Example:**

```javascript
function outerFunction() {
  const outerVar = 'I am outside!';
  
  function innerFunction() {
    console.log(outerVar);
  }
  
  return innerFunction;
}

const myFunction = outerFunction();
myFunction(); // I am outside!
```

**Explanation:**
- `innerFunction` retains access to `outerVar` even after `outerFunction` has finished executing.

#### Prototypal Inheritance
Prototypal inheritance is a feature in JavaScript used to add methods and properties to objects. It is a method by which an object can inherit properties and methods from another object.

**Example:**

```javascript
const person = {
  greet() {
    console.log('Hello!');
  }
};

const john = Object.create(person);
john.greet(); // Hello!
```

**Explanation:**
- `john` inherits the `greet` method from `person` using `Object.create`.

#### Modules
Modules are a way to organize and reuse code by exporting and importing functions, objects, or primitives.

**Example:**

```javascript
// module.js
export const name = 'John';
export function greet() {
  return 'Hello!';
}

// main.js
import { name, greet } from './module';
console.log(greet()); // Hello!
console.log(name); // John
```

**Explanation:**
- The `name` and `greet` are exported from `module.js` and imported into `main.js`.

#### Currying
Currying is a technique of evaluating a function with multiple arguments, transforming it into a sequence of functions with a single argument.

**Example:**

```javascript
function curry(func) {
  return function curried(...args) {
    if (args.length >= func.length) {
      return func.apply(this, args);
    } else {
      return function(...args2) {
        return curried.apply(this, args.concat(args2));
      };
    }
  };
}

function add(a, b) {
  return a + b;
}

const curriedAdd = curry(add);
console.log(curriedAdd(1)(2)); // 3
```

**Explanation:**
- The `curry` function transforms the `add` function into a sequence of functions that can be called with a single argument.

#### Higher-Order Functions
Higher-order functions are functions that take other functions as arguments or return functions as their result.

**Example:**

```javascript
function higherOrderFunction(callback) {
  return function() {
    return callback();
  };
}

function sayHello() {
  return 'Hello!';
}

const greet = higherOrderFunction(sayHello);
console.log(greet()); // Hello!
```

**Explanation:**
- The `higherOrderFunction` takes `sayHello` as an argument and returns a new function that calls `sayHello`.

#### Memoization
Memoization is an optimization technique to speed up function calls by caching the results of expensive function calls.

**Example:**

```javascript
function memoize(fn) {
  const cache = {};
  return function(...args) {
    const key = JSON.stringify(args);
    if (cache[key]) {
      return cache[key];
    } else {
      const result = fn.apply(this, args);
      cache[key] = result;
      return result;
    }
  };
}

function slowFunction(num) {
  for (let i = 0; i < 1e9; i++) {} // Simulate a slow computation
  return num * 2;
}

const memoizedSlowFunction = memoize(slowFunction);
console.log(memoizedSlowFunction(5)); // Slow computation
console.log(memoizedSlowFunction(5)); // Fast computation (cached)
```

**Explanation:**
- The `memoize` function caches the results of `slowFunction` to avoid redundant computations.

#### Debouncing and Throttling
Debouncing and throttling are techniques to control the rate at which a function is executed.

**Debouncing Example:**

```javascript
function debounce(func, delay) {
  let debounceTimer;
  return function() {
    const context = this;
    const args = arguments;
    clearTimeout(debounceTimer);
    debounceTimer = setTimeout(() => func.apply(context, args), delay);
  };
}

const handleResize = debounce(() => {
  console.log('Resized!');
}, 500);

window.addEventListener('resize', handleResize);
```

**Throttling Example:**

```javascript
function throttle(func, limit) {
  let lastFunc;
  let lastRan;
  return function() {
    const context = this;
    const args = arguments;
    if (!lastRan) {
      func.apply(context, args);
      lastRan = Date.now();
    } else {
      clearTimeout(lastFunc);
      lastFunc = setTimeout(() => {
        if (Date.now() - lastRan >= limit) {
          func.apply(context, args);
          lastRan = Date.now();
        }
      }, limit - (Date.now() - lastRan));
    }
  };
}

const handleScroll = throttle(() => {
  console.log('Scrolled!');
}, 1000);

window.addEventListener('scroll', handleScroll);
```

**Explanation:**
- **Debouncing** ensures that the function is called only after a specified delay has passed since the last call.
- **Throttling** ensures that the function is called at most once in a specified time period.
---
