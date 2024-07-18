# Day 6: Arrays in JavaScript

Welcome to Day 6 of JavaScript Basics! Today, we'll be focusing on arrays in JavaScript. This includes array creation, basic and intermediate array methods, array iteration, and working with multi-dimensional arrays.

## Table of Contents

1. [Activity 1: Array Creation and Access](#activity-1-array-creation-and-access)
   - Task 1: Create an array of numbers from 1 to 5 and log the array to the console.
   - Task 2: Access the first and last elements of the array and log them to the console.
2. [Activity 2: Array Methods (Basic)](#activity-2-array-methods-basic)
   - Task 3: Use the `push` method to add a new number to the end of the array and log the updated array.
   - Task 4: Use the `pop` method to remove the last element from the array and log the updated array.
   - Task 5: Use the `shift` method to remove the first element from the array and log the updated array.
   - Task 6: Use the `unshift` method to add a new number to the beginning of the array and log the updated array.
3. [Activity 3: Array Methods (Intermediate)](#activity-3-array-methods-intermediate)
   - Task 7: Use the `map` method to create a new array where each number is doubled and log the new array.
   - Task 8: Use the `filter` method to create a new array with only even numbers and log the new array.
   - Task 9: Use the `reduce` method to calculate the sum of all numbers in the array and log the result.
4. [Activity 4: Array Iteration](#activity-4-array-iteration)
   - Task 10: Use a `for` loop to iterate over the array and log each element to the console.
   - Task 11: Use the `forEach` method to iterate over the array and log each element to the console.
5. [Activity 5: Multi-dimensional Arrays](#activity-5-multi-dimensional-arrays)
   - Task 12: Create a two-dimensional array (matrix) and log the entire array to the console.
   - Task 13: Access and log a specific element from the two-dimensional array.
6. [Feature Request](#feature-request)
7. [Achievements](#achievements)

## Activity 1: Array Creation and Access

**Task 1:** Create an array of numbers from 1 to 5 and log the array to the console.

```javascript
let array = [1, 2, 3, 4, 5];
console.log(array);
// Output: [1, 2, 3, 4, 5]
```

**Task 2:** Access the first and last elements of the array and log them to the console.

```javascript
let array = [1, 2, 3, 4, 5];
console.log(array[0]); // Output: 1
console.log(array[array.length - 1]); // Output: 5
```

## Activity 2: Array Methods (Basic)

**Task 3:** Use the push method to add a new number to the end of the array and log the updated array.

```javascript
let array = [1, 2, 3, 4, 5];
array.push(6);
console.log(array);
// Output: [1, 2, 3, 4, 5, 6]
```

**Task 4:** Use the pop method to remove the last element from the array and log the updated array.

```javascript
let array = [1, 2, 3, 4, 5, 6];
array.pop();
console.log(array);
// Output: [1, 2, 3, 4, 5]
```

**Task 5:** Use the shift method to remove the first element from the array and log the updated array.

```javascript
let array = [1, 2, 3, 4, 5];
array.shift();
console.log(array);
// Output: [2, 3, 4, 5]
```

**Task 6:** Use the unshift method to add a new number to the beginning of the array and log the updated array.

```javascript
let array = [2, 3, 4, 5];
array.unshift(1);
console.log(array);
// Output: [1, 2, 3, 4, 5]
```

## Activity 3: Array Methods (Intermediate)

**Task 7:** Use the map method to create a new array where each number is doubled and log the new array.

```javascript
let array = [2, 3, 4, 5];
let doubledArray = array.map((num) => num * 2);
console.log(doubledArray);
// Output: [2, 4, 6, 8, 10]
```

**Task 8:** Use the filter method to create a new array with only even numbers and log the new array.

```javascript
let array = [1, 2, 3, 4, 5];
let evenArray = array.filter((num) => num % 2 === 0);
console.log(evenArray);
// Output: [2, 4]
```

**Task 9:** Use the reduce method to calculate the sum of all numbers in the array and log the result.

```javascript
let array = [1, 2, 3, 4, 5];
let sum = array.reduce(
  (accumulator, currentValue) => accumulator + currentValue,
  0
);
console.log(sum);
// Output: 15
```

## Activity 4: Array Iteration

**Task 10:** Use a for loop to iterate over the array and log each element to the console.

```javascript
let array = [1, 2, 3, 4, 5];
for (let i = 0; i < array.length; i++) {
  console.log(array[i]);
}
/*
Output:
1
2
3
4
5
*/
```

**Task 11:** Use the forEach method to iterate over the array and log each element to the console.

```javascript
let array = [1, 2, 3, 4, 5];
array.forEach((element) => console.log(element));
/*
Output:
1
2
3
4
5
*/
```

## Activity 5: Multi-dimensional Arrays

**Task 12:** Create a two-dimensional array (matrix) and log the entire array to the console.

```javascript
let matrix = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9],
];
console.log(matrix);
// Output: [ [1, 2, 3], [4, 5, 6], [7, 8, 9] ]
```

**Task 13:** Access and log a specific element from the two-dimensional array.

```javascript
let matrix = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9],
];

// Accessing the element at the second row and second column
console.log(matrix[1][1]);
// Output: 5
```

## Feature Request

1. Array Manipulation Script: Write a script that demonstrates the creation of an array, adding and removing elements using push, pop, shift, and unshift methods.

```javascript
// Create an array
let arr = [10, 20, 30];
console.log("Initial array:", arr); // [10, 20, 30]

// Add 40 to the end of the array
arr.push(40);
console.log("After push(40):", arr); // [10, 20, 30, 40]

// Remove the last element from the array
arr.pop();
console.log("After pop():", arr); // [10, 20, 30]

// Remove the first element from the array
arr.shift();
console.log("After shift():", arr); // [20, 30]

// Add 5 to the beginning of the array
arr.unshift(5);
console.log("After unshift(5):", arr); // [5, 20, 30]
```

2. Array Transformation Script: Create a script that uses map, filter, and reduce methods to transform and aggregate array data.

```javascript
// Create an array
let originalArray = [1, 2, 3, 4, 5];
console.log("Original array:", originalArray); // [1, 2, 3, 4, 5]

// Double each element using map
let doubledArray = originalArray.map((num) => num * 2);
console.log("Doubled array:", doubledArray); // [2, 4, 6, 8, 10]

// Filter out only even numbers
let evenArray = doubledArray.filter((num) => num % 2 === 0);
console.log("Even array:", evenArray); // [ 2, 4, 6, 8, 10 ]

// Calculate the sum of the filtered array using reduce
let sum = evenArray.reduce(
  (accumulator, currentValue) => accumulator + currentValue,
  0
);
console.log("Sum of even array:", sum); // 30
```

3. Array Iteration Script: Write a script that iterates over an array using both for loop and forEach method and logs each element.

```javascript
// Create an array
let iterationArray = [1, 2, 3];
console.log("Array for iteration:", iterationArray); // [1, 2, 3]

// Iterate using forEach
console.log("Iteration using forEach:");
iterationArray.forEach((element) => console.log(element)); // 1, 2, 3

// Iterate using for loop
console.log("Iteration using for loop:");
for (let i = 0; i < iterationArray.length; i++) {
  console.log(iterationArray[i]); // 1, 2, 3
}
```

4. Two-dimensional Array Script: Create a script that demonstrates the creation and manipulation of a two-dimensional array.

```javascript
// Create a two-dimensional array (matrix)
let twoDimArray = [
  [1, 2],
  [3, 4],
  [5, 6],
];
console.log("Two-dimensional array:");
console.log(twoDimArray); // [ [ 1, 2 ], [ 3, 4 ], [ 5, 6 ] ]

// Access and log each row
console.log("Accessing each row:");
twoDimArray.forEach((row) => console.log(row));
/*
[ 1, 2 ]
[ 3, 4 ]
[ 5, 6 ]
*/

// Access and log a specific element
console.log("Accessing a specific element (row 2, col 2):", twoDimArray[1][1]); // Output: 4
```

## Achievements:

By the end of these activities, students will:

- Create and manipulate arrays using various methods.
- Transform and aggregate array data using map, filter, and reduce.
- Iterate over arrays using loops and iteration methods.
- Understand and work with multi-dimensional arrays.
