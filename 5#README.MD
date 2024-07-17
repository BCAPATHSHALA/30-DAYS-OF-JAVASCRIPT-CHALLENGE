# Day 5: Functions in JavaScript

Welcome to Day 5 of JavaScript Basics! Today, we'll be focusing on functions in JavaScript. This includes function declarations, function expressions, arrow functions, function parameters with default values, and higher-order functions.

## Table of Contents

1. [Activity 1: Function Declaration](#activity-1-function-declaration)
   - Task 1: Write a function to check if a number is even or odd and log the result to the console.
   - Task 2: Write a function to calculate the square of a number and return the result.
2. [Activity 2: Function Expression](#activity-2-function-expression)
   - Task 3: Write a function expression to find the maximum of two numbers and log the result to the console.
   - Task 4: Write a function expression to concatenate two strings and return the result.
3. [Activity 3: Arrow Functions](#activity-3-arrow-functions)
   - Task 5: Write an arrow function to calculate the sum of two numbers and return the result.
   - Task 6: Write an arrow function to check if a string contains a specific character and return a boolean value.
4. [Activity 4: Function Parameters and Default Values](#activity-4-function-parameters-and-default-values)
   - Task 7: Write a function that takes two parameters and returns their product. Provide a default value for the second parameter.
   - Task 8: Write a function that takes a person’s name and age and returns a greeting message. Provide a default value for the age.
5. [Activity 5: Higher-Order Functions](#activity-5-higher-order-functions)
   - Task 9: Write a higher-order function that takes a function and a number, and calls the function that many times.
   - Task 10: Write a higher-order function that takes two functions and a value, applies the first function to the value, and then applies the second function to the result.
6. [Feature Request](#feature-request)
7. [Achievements](#achievements)

## Activity 1: Function Declaration

**Task 1:** Write a function to check if a number is even or odd and log the result to the console.

```javascript
function isEvenOrOdd(number) {
  if (number % 2 === 0) {
    console.log(`${number} is even.`);
  } else {
    console.log(`${number} is odd.`);
  }
}

isEvenOrOdd(7); // Output: 7 is odd.
isEvenOrOdd(12); // Output: 12 is even.
```

**Task 2:** Write a function to calculate the square of a number and return the result.

```javascript
function square(number) {
  return number * number;
}

console.log(square(5)); // Output: 25
console.log(square(9)); // Output: 81
```

## Activity 2: Function Expression

**Task 3:** Write a function expression to find the maximum of two numbers and log the result to the console.

```javascript
const findMax = function (num1, num2) {
  let max = num1 > num2 ? num1 : num2;
  console.log(`The maximum of ${num1} and ${num2} is ${max}.`);
};

findMax(10, 20); // Output: The maximum of 10 and 20 is 20.
findMax(42, 39); // Output: The maximum of 42 and 39 is 42.
```

**Task 4:** Write a function expression to concatenate two strings and return the result.

```javascript
const concatenateStrings = function (str1, str2) {
  return str1 + str2;
};

console.log(concatenateStrings("Hello, ", "World!")); // Output: Hello, World!
console.log(concatenateStrings("JavaScript ", "is awesome!")); // Output: JavaScript is awesome!
```

## Activity 3: Arrow Functions

**Task 5:** Write an arrow function to calculate the sum of two numbers and return the result.

```javascript
const sum = (num1, num2) => num1 + num2;

console.log(sum(8, 12)); // Output: 20
console.log(sum(25, 17)); // Output: 42
```

**Task 6:** Write an arrow function to check if a string contains a specific character and return a boolean value.

```javascript
const containsChar = (str, char) => str.includes(char);

console.log(containsChar("Hello, World!", "o")); // Output: true
console.log(containsChar("JavaScript", "z")); // Output: false
```

## Activity 4: Function Parameters and Default Values

**Task 7:** Write a function that takes two parameters and returns their product. Provide a default value for the second parameter.

```javascript
function multiply(num1, num2 = 1) {
  return num1 * num2;
}

console.log(multiply(5, 4)); // Output: 20
console.log(multiply(7)); // Output: 7
```

**Task 8:** Write a function that takes a person’s name and age and returns a greeting message. Provide a default value for the age.

```javascript
function greet(name, age = 30) {
  return `Hello, ${name}! You are ${age} years old.`;
}

console.log(greet("Manoj")); // Output: Hello, Manoj! You are 30 years old.
console.log(greet("Alice", 25)); // Output: Hello, Alice! You are 25 years old.
```

## Activity 5: Higher-Order Functions

**Task 9:** Write a higher-order function that takes a function and a number, and calls the function that many times.

```javascript
function repeatFunction(fn, times) {
  for (let i = 0; i < times; i++) {
    fn();
  }
}

repeatFunction(() => console.log("Hello!"), 3);
// Output:
// Hello!
// Hello!
// Hello!
```

**Task 10:** Write a higher-order function that takes two functions and a value, applies the first function to the value, and then applies the second function to the result.

```javascript
function applyFunctions(fn1, fn2, value) {
  return fn2(fn1(value));
}

const addFive = (x) => x + 5;
const square = (x) => x * x;

console.log(applyFunctions(addFive, square, 3)); // Output: 64
// Explanation: addFive(3) => 8, then square(8) => 64
```

## Feature Request:

1. Even or Odd Function Script: Write a script that includes a function to check if a number is even or odd and logs the result.

```javascript
function evenOrOddScript(number) {
  const isEven = (num) => num % 2 === 0;
  const result = isEven(number) ? "even" : "odd";
  console.log(`${number} is ${result}.`);
}

evenOrOddScript(10); // Output: 10 is even.
evenOrOddScript(7); // Output: 7 is odd.
```

2. Square Calculation Function Script: Create a script that includes a function to calculate the square of a number and returns the result.

```javascript
function squareFunctionScript(number) {
  const square = (num) => num * num;
  return square(number);
}

console.log(squareFunctionScript(6)); // Output: 36
console.log(squareFunctionScript(3)); // Output: 9
```

3. Concatenation Function Script: Write a script that includes a function expression to concatenate two strings and returns the result.

```javascript
const concatenate = (str1, str2) => str1 + str2;

console.log(concatenate("Good ", "Morning!")); // Output: Good Morning!
console.log(concatenate("Front ", "End")); // Output: Front End
```

4. Sum Calculation Arrow Function Script: Create a script that includes an arrow function to calculate the sum of two numbers and returns the result.

```javascript
const sumCalculation = (num1, num2) => num1 + num2;

console.log(sumCalculation(15, 25)); // Output: 40
console.log(sumCalculation(7, 14)); // Output: 21
```

5. Higher-Order Function Script: Write a script that includes a higher-order function to apply a given function multiple times.

```javascript
const higherOrderFunction = (fn, times, value) => {
  let result = value;
  for (let i = 0; i < times; i++) {
    result = fn(result);
  }
  return result;
};

const addTen = (num) => num + 10;

console.log(higherOrderFunction(addTen, 3, 5)); // Output: 35
// Explanation: 5 + 10 + 10 + 10 = 35
```

## Achievements:

By the end of these activities, students will:

- Understand and define functions using function declarations, expressions, and arrow functions.
- Use function parameters and default values effectively.
- Create and utilize higher-order functions.
- Apply functions to solve common problems and perform calculations.
- Enhance code reusability and organization using functions.
