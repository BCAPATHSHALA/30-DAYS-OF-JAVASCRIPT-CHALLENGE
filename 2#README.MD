# DAY 2: JavaScript Operators

Welcome to Day 2 of JavaScript Basics! Today, we'll be focusing on JavaScript operators. This includes arithmetic, assignment, comparison, logical, and ternary operators.

## Table of Contents

1. [Activity 1: Arithmetic Operations](#activity-1-arithmetic-operations)
   - Task 1: Addition
   - Task 2: Subtraction
   - Task 3: Multiplication
   - Task 4: Division
   - Task 5: Remainder
2. [Activity 2: Assignment Operators](#activity-2-assignment-operators)
   - Task 6: `+=` Operator
   - Task 7: `-=` Operator
3. [Activity 3: Comparison Operators](#activity-3-comparison-operators)
   - Task 8: `>` and `<` Operators
   - Task 9: `>=` and `<=` Operators
   - Task 10: `==` and `===` Operators
4. [Activity 4: Logical Operators](#activity-4-logical-operators)
   - Task 11: `&&` Operator
   - Task 12: `||` Operator
   - Task 13: `!` Operator
5. [Activity 5: Ternary Operator](#activity-5-ternary-operator)
   - Task 14: Ternary Operator
6. [Feature Request](#feature-request)
   - 1. Arithmetic Operations Script
   - 2. Comparison and Logical Operators Script
   - 3. Ternary Operator Script
7. [Achievements](#achievements)

## Activity 1: Arithmetic Operations

**Task 1:** Write a program to add two numbers and log the result to the console.

```javascript
let a = 5;
let b = 3;
let sum = a + b;
console.log("Sum:", sum); // Sum: 8
```

**Task 2:** Write a program to subtract two numbers and log the result to the console.

```javascript
let a = 10;
let b = 4;
let difference = a - b;
console.log("Difference:", difference); // Difference: 6
```

**Task 3:** Write a program to multiply two numbers and log the result to the console.

```javascript
let a = 7;
let b = 6;
let product = a * b;
console.log("Product:", product); // Product: 42
```

**Task 4:** Write a program to divide two numbers and log the result to the console.

```javascript
let a = 20;
let b = 5;
let quotient = a / b;
console.log("Quotient:", quotient); // Quotient: 4
```

**Task 5:** Write a program to find the remainder when one number is divided by another and log the result to the console.

```javascript
let a = 15;
let b = 4;
let remainder = a % b;
console.log("Remainder:", remainder); // Remainder: 3
```

## Activity 2: Assignment Operators

**Task 6:** Use the `+=` operator to add a number to a variable and log the result to the console.

```javascript
let a = 10;
a += 5;
console.log("After += operation:", a); // After += operation: 15
```

**Task 7:** Use the `-= `operator to subtract a number from a variable and log the result to the console.

```javascript
let a = 10;
a -= 3;
console.log("After -= operation:", a); // After -= operation: 7
```

## Activity 3: Comparison Operators

**Task 8:** Write a program to compare two numbers using `>` and `<` and log the result to the console.

```javascript
let a = 8;
let b = 5;
console.log("a > b:", a > b); // a > b: true
console.log("a < b:", a < b); // a < b: false
```

**Task 9:** Write a program to compare two numbers using `>=` and `<=` and log the result to the console.

```javascript
let a = 8;
let b = 8;
console.log("a >= b:", a >= b); // a >= b: true
console.log("a <= b:", a <= b); // a <= b: true
```

**Task 10:** Write a program to compare two numbers using `==` and `===` and log the result to the console.

```javascript
let a = 10;
let b = "10";
console.log("a == b:", a == b); // a == b: true -> because == does type coercion
console.log("a === b:", a === b); // a === b: false -> because === checks for strict equality
```

## Activity 4: Logical Operators

**Task 11:** Write a program that uses the `&&` operator to combine two conditions and log the result to the console.

```javascript
let a = true;
let b = false;
console.log("a && b:", a && b); // a && b: false -> because both conditions are not true
```

**Task 12:** Write a program that uses the `||` operator to combine two conditions and log the result to the console.

```javascript
let a = true;
let b = false;
console.log("a || b:", a || b); // a || b: true -> because at least one condition is true
```

**Task 13:** Write a program that uses the `!` operator to negate a condition and log the result to the console.

```javascript
let a = true;
console.log("!a:", !a); // !a: false -> because the negation of true is false
```

## Activity 5: Ternary Operator

**Task 14:** Write a program that uses the ternary operator to check if a number is positive or negative and log the result to the console.

```javascript
let num = -5;
let result = num > 0 ? "Positive" : "Negative";
console.log("The number is:", result); // The number is: Negative
```

```javascript
let num = 5;
let result = num > 0 ? "Positive" : "Negative";
console.log("The number is:", result); // The number is: Positive
```

## Feature Request:

### 1. Arithmetic Operations Script:

Write a script that performs basic arithmetic operations **(addition, subtraction, multiplication, division, remainder)** on two numbers and logs the results.

```javascript
let num1 = 12;
let num2 = 8;

// Addition
let addition = num1 + num2;
console.log("Addition:", addition); // Addition: 20

// Subtraction
let subtraction = num1 - num2;
console.log("Subtraction:", subtraction); // Subtraction: 4

// Multiplication
let multiplication = num1 * num2;
console.log("Multiplication:", multiplication); // Multiplication: 96

// Division
let division = num1 / num2;
console.log("Division:", division); // Division: 1

// Remainder
let remainder = num1 % num2;
console.log("Remainder:", remainder); // Remainder: 4
```

### 2. Comparison and Logical Operators Script:

Create a script that compares two numbers using different comparison operators and combines conditions using logical operators, logging the results.

```javascript
let a = 15;
let b = 10;

// Comparison Operators
console.log("a > b:", a > b); // Output: true
console.log("a < b:", a < b); // Output: false
console.log("a >= b:", a >= b); // Output: true
console.log("a <= b:", a <= b); // Output: false
console.log("a == b:", a == b); // Output: false
console.log("a === b:", a === b); //  Output: false

// Logical Operators
let condition1 = a > b; // Output: true
let condition2 = a == 15; // Output: true

console.log("condition1 && condition2:", condition1 && condition2); // Output: true
console.log("condition1 || condition2:", condition1 || condition2); // Output: true
console.log("!condition1:", !condition1); // Output: false
```

### 3. Ternary Operator Script:

Write a script that uses the ternary operator to determine if a number is positive or negative and logs the result.

```javascript
let number = -7;
let result = number >= 0 ? "Positive" : "Negative";
console.log("The number is:", result); // The number is: Negative
```

## Achievements:

By the end of these activities, students will:

- Understand and use arithmetic operators to perform basic calculations.
- Use assignment operators to modify variable values.
- Compare values using comparison operators.
- Combine conditions using logical operators.
- Use the ternary operator for concise conditional expressions.
