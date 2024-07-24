# Day 12: Error Handling in JavaScript

Welcome to Day 12 of JavaScript Basics! Today, we'll explore error handling in JavaScript. We'll cover basic error handling with try-catch, using the finally block, creating custom error objects, handling errors in promises, and gracefully handling errors when using the `fetch` API. By the end of these activities, you'll have a strong understanding of how to handle errors in your JavaScript code effectively.

## Table of Contents

1. [Activity 1: Basic Error Handling with Try-Catch](#activity-1-basic-error-handling-with-try-catch)
2. [Activity 2: Finally Block](#activity-2-finally-block)
3. [Activity 3: Custom Error Objects](#activity-3-custom-error-objects)
4. [Activity 4: Error Handling in Promises](#activity-4-error-handling-in-promises)
5. [Activity 5: Graceful Error Handling in `fetch`](#activity-5-graceful-error-handling-in-fetch)
6. [Feature Request](#feature-request)
7. [Achievements](#achievements)

## Activity 1: Basic Error Handling with Try-Catch

**Task 1:** Write a function that intentionally throws an error and use a try-catch block to handle the error and log an appropriate message to the console.

```js
function throwError() {
  throw new Error("This is an intentional error.");
}

try {
  throwError();
} catch (error) {
  console.log("Caught an error:", error.message);
}

/*
OUTPUT:
Caught an error: This is an intentional error.
*/
```

**Task 2:** Create a function that divides two numbers and throws an error if the denominator is zero. Use a try-catch block to handle this error.

```js
function divide(a, b) {
  if (b === 0) {
    throw new Error("Division by zero is not allowed.");
  }
  return a / b;
}

try {
  console.log(divide(4, 2)); // Expected output: 2
  console.log(divide(4, 0)); // This will throw an error
} catch (error) {
  console.log("Caught an error:", error.message);
}

/*
OUTPUT:
2
Caught an error: Division by zero is not allowed.
*/
```

## Activity 2: Finally Block

**Task 3:** Write a script that includes a try-catch block and a finally block. Log messages in the try, catch, and finally blocks to observe the execution flow.

```js
function testFinallyBlock() {
  try {
    console.log("In try block");
    throw new Error("Error in try block");
  } catch (error) {
    console.log("In catch block:", error.message);
  } finally {
    console.log("In finally block");
  }
}

testFinallyBlock();

/*
OUTPUT:
In try block
In catch block: Error in try block
In finally block
*/
```

## Activity 3: Custom Error Objects

**Task 4:** Create a custom error class that extends the built-in Error class. Throw an instance of this custom error in a function and handle it using a try-catch block.

```js
class CustomError extends Error {
  constructor(message) {
    super(message);
    this.name = "CustomError";
  }
}

function throwError() {
  throw new CustomError("This is a custom error.");
}

try {
  throwError();
} catch (error) {
  console.log(`${error.name}: ${error.message}`);
}

/*
OUTPUT:
CustomError: This is a custom error.
*/
```

**Task 5:** Write a function that validates user input (e.g., checking if a string is not empty) and throws a custom error if the validation fails. Handle the custom error using a try-catch block.

```js
class ValidationError extends Error {
  constructor(message) {
    super(message);
    this.name = "ValidationError";
  }
}

function validateInput(input) {
  if (!input) {
    throw new ValidationError("Input cannot be empty.");
  }
  return true;
}

try {
  validateInput(""); // This will throw an error
} catch (error) {
  console.log(`${error.name}: ${error.message}`);
}

/*
OUTPUT:
ValidationError: Input cannot be empty.
*/
```

## Activity 4: Error Handling in Promises

**Task 6:** Create a promise that randomly resolves or rejects. Use `.catch()` to handle the rejection and log an appropriate message to the console.

```js
function randomPromise() {
  return new Promise((resolve, reject) => {
    const random = Math.random();
    if (random > 0.5) {
      resolve("Promise resolved!");
    } else {
      reject(new Error("Promise rejected."));
    }
  });
}

randomPromise()
  .then((message) => console.log(message))
  .catch((error) => console.log("Caught an error:", error.message));

/*
OUTPUT:
Promise resolved!
*/
```

**Task 7:** Use try-catch within an async function to handle errors from a promise that randomly resolves or rejects, and log the error message.

```js
function randomPromise() {
  return new Promise((resolve, reject) => {
    const random = Math.random();
    if (random > 0.5) {
      resolve("Promise resolved!");
    } else {
      reject(new Error("Promise rejected."));
    }
  });
}

async function handlePromise() {
  try {
    const message = await randomPromise();
    console.log(message);
  } catch (error) {
    console.log("Caught an error:", error.message);
  }
}

handlePromise();

/*
OUTPUT:
Caught an error: Promise rejected.
*/
```

## Activity 5: Graceful Error Handling in `fetch`

**Task 8:** Use the `fetch` API to request data from an invalid URL and handle the error using `.catch()`. Log an appropriate error message to the console.

```js
fetch("https://jsonplaceholder.typicode.com/postsssssssssssss")
  .then((response) => response.json())
  .catch((error) => console.log("Fetch error:", error.message));

/*
OUTPUT:
Fetch error: Failed to fetch
*/
```

**Task 9:** Use the `fetch` API to request data from an invalid URL within an async function and handle the error using try-catch. Log an appropriate error message.

```js
async function fetchData() {
  try {
    const response = await fetch(
      "https://jsonplaceholder.typicode.com/postsssssssssssss"
    );
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.log("Fetch error:", error.message);
  }
}

fetchData();

/*
OUTPUT:
Fetch error: Failed to fetch
*/
```

## Feature Request

1. **Basic Error Handling Script:** Write a script that demonstrates basic error handling using try-catch and finally blocks.
2. **Custom Error Script:** Create a script that defines and throws custom errors, handling them with try-catch blocks.
3. **Promise Error Handling Script:** Write a script that handles errors in promises using `.catch()` and try-catch within async functions.
4. **Fetch Error Handling Script:** Create a script that handles errors when using the `fetch` API to request data from invalid URLs.

## Achievements

By the end of these activities, students will:

- Understand and implement basic error handling using try-catch blocks.
- Use finally blocks to execute code regardless of the try-catch outcome.
- Create and use custom error classes.
- Handle errors in promises using `.catch()` and within async functions using try-catch.
- Implement graceful error handling when making network requests with the `fetch` API.
