# Day 15: Closures in JavaScript

Welcome to JavaScript Closures Activities! In these activities, we will explore the concept of closures in JavaScript through various tasks and practical examples. By the end of these activities, you'll have a solid understanding of how to use closures effectively in JavaScript.

## Table of Contents

1. [Activity 1: Understanding Closures](#activity-1-understanding-closures)
2. [Activity 2: Practical Closures](#activity-2-practical-closures)
3. [Activity 3: Closures in Loops](#activity-3-closures-in-loops)
4. [Activity 4: Module Pattern](#activity-4-module-pattern)
5. [Activity 5: Event Listeners](#activity-5-event-listeners)
6. [Activity 6: Memoization](#activity-6-memoization)
7. [Activity 7: Function Currying](#activity-7-function-currying)
8. [Feature Request](#feature-request)
9. [Achievements](#achievements)

## Activity 1: Understanding Closures

**Task 1:** Write a function that returns another function, where the inner function accesses a variable from the outer function’s scope. Call the inner function and log the result.

```js
function outerFunction() {
  let outerVar = "I am from outer function";

  return function innerFunction() {
    console.log(outerVar);
  };
}

const inner = outerFunction();
console.log(inner); // inner: [Function: innerFunction]
inner(); // I am from outer function
```

**Task 2:** Create a closure that maintains a private counter. Implement functions to increment and get the current value of the counter.

```js
function createCounter() {
  let count = 0;

  return {
    increment() {
      count++;
    },
    getCount() {
      return count;
    },
  };
}

const counter = createCounter();
console.log(counter); // counter: { increment: [Function: increment], getCount: [Function: getCount] }
counter.increment(); // count: 1
counter.increment(); // count: 2
console.log(counter.getCount()); // 2
```

## Activity 2: Practical Closures

**Task 3:** Write a function that generates unique IDs. Use a closure to keep track of the last generated ID and increment it with each call.

```js
function createUniqueIdGenerator() {
  let lastId = 0;

  return function () {
    lastId++;
    return lastId;
  };
}

const generateId = createUniqueIdGenerator();
console.log(generateId); // generateId: [Function (anonymous)]
console.log(generateId()); // 1
console.log(generateId()); // 2
```

**Task 4:** Create a closure that captures a user’s name and returns a function that greets the user by name.

```js
function greetUser(name) {
  return function () {
    console.log(`Hello, ${name}!`);
  };
}

const greetSANOJ = greetUser("SANOJ");
greetSANOJ(); // Hello, SANOJ!
```

## Activity 3: Closures in Loops

**Task 5:** Write a loop that creates an array of functions. Each function should log its index when called. Use a closure to ensure each function logs the correct index.

```js
let functions = [];

for (let i = 0; i < 5; i++) {
  functions.push(
    (function (index) {
      return function () {
        console.log(index);
      };
    })(i)
  );
}

functions.forEach((func) => func());
/*
0
1
2
3
4
*/
```

## Activity 4: Module Pattern

**Task 6:** Use closures to create a simple module for managing a collection of items. Implement methods to `add`, `remove`, and `list` items.

```js
const itemManager = (function () {
  let items = [];

  return {
    addItem(item) {
      items.push(item);
    },
    removeItem(item) {
      items = items.filter((i) => i !== item);
    },
    listItems() {
      return items;
    },
  };
})();

console.log(itemManager);
/*
{
  addItem: [Function: addItem],
  removeItem: [Function: removeItem],
  listItems: [Function: listItems]
}
*/
console.log(itemManager.listItems()); // []
itemManager.addItem("Apple");
itemManager.addItem("Banana");
itemManager.addItem("Mango");
console.log(itemManager.listItems()); // [ 'Apple', 'Banana', 'Mango' ]
itemManager.removeItem("Apple");
console.log(itemManager.listItems()); // [ 'Banana', 'Mango' ]
```

## Activity 5: Event Listeners

**Task 7:** Write a function that attaches a click event listener to a button. Use a closure to keep track of the number of clicks and log the count each time the button is clicked.

```js
document.body.innerHTML = '<button id="myButton">Click me</button>';

function attachClickListener() {
  let clickCount = 0;

  document.getElementById("myButton").addEventListener("click", function () {
    clickCount++;
    console.log(`Button clicked ${clickCount} times`);
  });
}

attachClickListener();
```

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <button id="myButton">Click me</button>

    <script>
      function attachClickListener() {
        let clickCount = 0;

        document
          .getElementById("myButton")
          .addEventListener("click", function () {
            clickCount++;
            console.log(`Button clicked ${clickCount} times`); // Button clicked 1 times
          });
      }

      attachClickListener();
    </script>
  </body>
</html>
```

## Activity 6: Memoization

**Task 8:** Implement a memoized version of a function that calculates the factorial of a number. Use a closure to store previously calculated results.

```js
function memoize(fn) {
  const cache = {};

  return function (...args) {
    const key = args.toString();
    if (cache[key]) {
      return cache[key];
    } else {
      const result = fn(...args);
      cache[key] = result;
      return result;
    }
  };
}

const factorial = memoize(function (n) {
  if (n <= 1) {
    return 1;
  } else {
    return n * factorial(n - 1);
  }
});

console.log(factorial(5)); // 120
console.log(factorial(6)); // 720
```

## Activity 7: Function Currying

**Task 9:** Write a curried function that takes three arguments one by one (e.g., `add(a)(b)(c)`) and returns their sum.

```js
function add(a) {
  return function (b) {
    return function (c) {
      return a + b + c;
    };
  };
}

console.log(add(1)(2)(3)); // 6
```

**Task 10:** Create a curried version of a function that multiplies two numbers.

```js
function multiply(a) {
  return function (b) {
    return a * b;
  };
}

console.log(multiply(2)(3)); // 6
```

## Feature Request

1. Basic Closure Script: Write a script that demonstrates a basic closure with a function returning another function that accesses the outer function's variable.
2. Counter Closure Script: Create a script that uses a closure to maintain a private counter with increment and get functions.
3. Unique ID Generator Script: Write a script that generates unique IDs using a closure to keep track of the last generated ID.
4. Loop Closure Script: Create a script that demonstrates closures in loops to ensure functions log the correct index.
5. Memoization Script: Write a script that memoizes the results of a function and demonstrates it with a factorial calculation.

## Achievements

By the end of these activities, students will:

- Understand and create closures in JavaScript.
- Use closures to maintain private state and create encapsulated modules.
- Apply closures in practical scenarios like generating unique IDs and memoization.
- Use closures in loops to capture and use variables correctly.
