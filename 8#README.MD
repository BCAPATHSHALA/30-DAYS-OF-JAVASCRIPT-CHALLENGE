# Day 8: Modern JavaScript Features

Welcome to Day 8 of JavaScript Basics! Today, we'll be focusing on modern JavaScript features including template literals, destructuring, spread and rest operators, default parameters, and enhanced object literals.

## Table of Contents

1. [Activity 1: Template Literals](#activity-1-template-literals)
   - Task 1: Use template literals to create a string that includes variables for a person's name and age, and log the string to the console.
   - Task 2: Create a multi-line string using template literals and log it to the console.
2. [Activity 2: Destructuring](#activity-2-destructuring)
   - Task 3: Use array destructuring to extract the first and second elements from an array of numbers and log them to the console.
   - Task 4: Use object destructuring to extract the title and author from a book object and log them to the console.
3. [Activity 3: Spread and Rest Operators](#activity-3-spread-and-rest-operators)
   - Task 5: Use the spread operator to create a new array that includes all elements of an existing array plus additional elements, and log the new array to the console.
   - Task 6: Use the rest operator in a function to accept an arbitrary number of arguments, sum them, and return the result.
4. [Activity 4: Default Parameters](#activity-4-default-parameters)
   - Task 7: Write a function that takes two parameters and returns their product, with the second parameter having a default value of 1. Log the result of calling this function with and without the second parameter.
5. [Activity 5: Enhanced Object Literals](#activity-5-enhanced-object-literals)
   - Task 8: Use enhanced object literals to create an object with methods and properties, and log the object to the console.
   - Task 9: Create an object with computed property names based on variables and log the object to the console.
6. [Feature Request](#feature-request)
   - Template Literals Script
   - Destructuring Script
   - Spread and Rest Operators Script
   - Default Parameters Script
   - Enhanced Object Literals Script
7. [Achievements](#achievements)

## Activity 1: Template Literals

**Task 1:** Use template literals to create a string that includes variables for a person's name and age, and log the string to the console.

```javascript
const name = "AMIT";
const age = 25;
const message = `My name is ${name} and I am ${age} years old.`;
console.log(message);
// Output: My name is AMIT and I am 25 years old.
```

**Task 2:** Create a multi-line string using template literals and log it to the console.

```javascript
const multiLineString = `My name is amit.
I am BCA passout student.
Now i am learning AI.`;
console.log(multiLineString);
/*
Output:
My name is amit.
         I am BCA passout student.
         Now i am learning AI.
*/
```

## Activity 2: Destructuring

**Task 3:** Use array destructuring to extract the first and second elements from an array of numbers and log them to the console.

```javascript
const numbers = [1, 2, 3, 4, 5];
const [first, second] = numbers;
console.log(`First: ${first}, Second: ${second}`);
// Output: First: 1, Second: 2
```

**Task 4:** Use object destructuring to extract the title and author from a book object and log them to the console.

```javascript
const book = {
  title: "Chai Aur Code",
  author: "HC",
  year: 2024,
};
const { title, author } = book;
console.log(`Title: ${title}, Author: ${author}`);
// Output: Title: Chai Aur Code, Author: HC
```

## Activity 3: Spread and Rest Operators

**Task 5:** Use the spread operator to create a new array that includes all elements of an existing array plus additional elements, and log the new array to the console.

```javascript
const oldArray = [1, 2, 3];
const newArray = [...oldArray, 4, 5, 6];
console.log(newArray);
// Output: [1, 2, 3, 4, 5, 6]
```

**Task 6:** Use the rest operator in a function to accept an arbitrary number of arguments, sum them, and return the result.

```javascript
function sum(...numbers) {
  return numbers.reduce((total, num) => total + num, 0);
}
console.log(sum(1, 2, 3, 4, 5)); // Output: 15
```

## Activity 4: Default Parameters

**Task 7:** Write a function that takes two parameters and returns their product, with the second parameter having a default value of 1. Log the result of calling this function with and without the second parameter.

```javascript
function multiply(a, b = 1) {
  return a * b;
}
console.log(multiply(5)); // Output: 5
console.log(multiply(5, 2)); // Output: 10
```

## Activity 5: Enhanced Object Literals

**Task 8:** Use enhanced object literals to create an object with methods and properties, and log the object to the console.

```javascript
const name = "MANOJ NISHAD";
const age = 25;

const person = {
  name,
  age,
  greet() {
    console.log(
      `Hello, my name is ${this.name} and I am ${this.age} years old.`
    );
  },
};

console.log(person);
// Output: { name: 'MANOJ NISHAD', age: 25, greet: [Function: greet] }
person.greet();
// Output: Hello, my name is MANOJ NISHAD and I am 25 years old.
```

**Task 9:** Create an object with computed property names based on variables and log the object to the console.

```javascript
const key = "favoriteColor";
const value = "blue";

const obj = {
  [key]: value,
};

console.log(obj);
// Output: { favoriteColor: 'blue' }
```

## Feature Request

1. **Template Literals Script:** Create a string that includes variables for a person's name and age, and log the string to the console.

```javascript
const personName = "MANOJ";
const personAge = 28;
const greeting = `Hello, my name is ${personName} and I am ${personAge} years old.
Nice to meet you!`;
console.log(greeting);
// Output: Hello, my name is MANOJ and I am 28 years old.
//         Nice to meet you!
```

2. **Destructuring Script:** Use object destructuring to extract properties from an object and log them to the console.

```javascript
const user = {
  username: "MANOJ",
  email: "manoj@example.com",
  password: "12345",
};

const { username, email } = user;
console.log(`Username: ${username}, Email: ${email}`);
// Output: Username: MANOJ, Email: manoj@example.com
```

3. **Spread and Rest Operators Script:** Use the spread operator to create a new array and the rest operator to sum an arbitrary number of arguments.

```javascript
const array1 = [1, 2, 3];
const array2 = [4, 5, 6];
const combinedArray = [...array1, ...array2];
console.log(combinedArray);
// Output: [1, 2, 3, 4, 5, 6]

function multiplyNumbers(multiplier, ...numbers) {
  console.log(multiplier); // 2
  return numbers.map((num) => num * multiplier);
}

console.log(multiplyNumbers(2, 1, 2, 3, 4)); // Output: [2, 4, 6, 8]
```

4. **Default Parameters Script:** Write a function with default parameters and log the results.

```javascript
function greet(name = "MANOJ") {
  console.log(`Hello, ${name}!`);
}

greet(); // Output: Hello, MANOJ!
greet("AMIT"); // Output: Hello, AMIT!
```

5. **Enhanced Object Literals Script:** Create an object with methods and properties using enhanced object literals and log the object and method results.

```javascript
const x = 10;
const y = 20;

const mathOperations = {
  x,
  y,
  add() {
    return this.x + this.y;
  },
  multiply() {
    return this.x * this.y;
  },
};

console.log(mathOperations);
// Output: { x: 10, y: 20, add: [Function: add], multiply: [Function: multiply] }
console.log(mathOperations.add()); // Output: 30
console.log(mathOperations.multiply()); // Output: 200
```

## Achievements

By the end of these activities, students will:

- Understand and use template literals for string interpolation and multi-line strings.
- Utilize array and object destructuring to extract values from arrays and objects.
- Apply the spread and rest operators for various use cases including function arguments and array manipulation.
- Implement default parameters in functions.
- Create and manage objects with enhanced object literals for cleaner and more concise code.
