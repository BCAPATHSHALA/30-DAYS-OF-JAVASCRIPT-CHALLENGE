# Day 4: Loops in JavaScript

Welcome to Day 4 of JavaScript Basics! Today, we'll be focusing on loops. This includes **for** loops, **while** loops, **do...while** loops, **nested loops**, and **loop control** statements.

## Table of Contents

1. [Activity 1: For Loop](#activity-1-for-loop)
   - Task 1: Print Numbers 1 to 10
   - Task 2: Multiplication Table of 5
2. [Activity 2: While Loop](#activity-2-while-loop)
   - Task 3: Sum of Numbers 1 to 10
   - Task 4: Print Numbers 10 to 1
3. [Activity 3: Do...While Loop](#activity-3-do-while-loop)
   - Task 5: Print Numbers 1 to 5
   - Task 6: Factorial Calculation
4. [Activity 4: Nested Loops](#activity-4-nested-loops)
   - Task 7: Print Pattern
5. [Activity 5: Loop Control Statements](#activity-5-loop-control-statements)
   - Task 8: Skip Number 5
   - Task 9: Break at Number 7
6. [Feature Request](#feature-request)
7. [Achievements](#achievements)

## Activity 1: For Loop

**Task 1:** Write a program to print numbers from 1 to 10 using a for loop.

```javascript
for (let i = 1; i <= 10; i++) {
  console.log(i);
}

/*
Expected Output:
1
2
3
4
5
6
7
8
9
10
*/
```

**Task 2:** Write a program to print the multiplication table of 5 using a for loop.

```javascript
const number = 5;
for (let i = 1; i <= 10; i++) {
  console.log(`${number} * ${i} = ${number * i}`);
}

/*
Expected Output:
5 * 1 = 5
5 * 2 = 10
5 * 3 = 15
5 * 4 = 20
5 * 5 = 25
5 * 6 = 30
5 * 7 = 35
5 * 8 = 40
5 * 9 = 45
5 * 10 = 50
*/
```

## Activity 2: While Loop

**Task 3:** Write a program to calculate the sum of numbers from 1 to 10 using a while loop.

```javascript
let sum = 0;
let i = 1;
while (i <= 10) {
  sum += i;
  i++;
}
console.log("Sum:", sum);

/*
Expected Output:
Sum: 55
*/
```

**Task 4:** Write a program to print numbers from 10 to 1 using a while loop.

```javascript
let i = 10;
while (i >= 1) {
  console.log(i);
  i--;
}

/*
Expected Output:
10
9
8
7
6
5
4
3
2
1
*/
```

## Activity 3: Do...While Loop

**Task 5:** Write a program to print numbers from 1 to 5 using a do...while loop.

```javascript
let i = 1;
do {
  console.log(i);
  i++;
} while (i <= 5);

/*
Expected Output:
1
2
3
4
5
*/
```

**Task 6:** Write a program to calculate the factorial of a number using a do...while loop.

```javascript
const number = 5;
let factorial = 1;
let i = number;

do {
  factorial *= i;
  i--;
} while (i > 0);

console.log(`Factorial of ${number} is ${factorial}`);

/*
Expected Output:
Factorial of 5 is 120
*/
```

## Activity 4: Nested Loops

**Task 7:** Write a program to print a pattern using nested for loops:

<div style="text-align: center;">
    <img src="https://res.cloudinary.com/dq3pru6ji/image/upload/v1721097477/pattern_logic_nmiobr.png" alt="JavaScrit">
</div>

```javascript
for (let row = 0; row < 5; row++) {
  let pattern = "";
  for (let col = 0; col < row + 1; col++) {
    pattern += "* ";
  }
  console.log(pattern.trim());
}

/*
Expected Output:
*
* *
* * *
* * * *
* * * * *
*/
```

## Activity 5: Loop Control Statements

**Task 8:** Write a program to print numbers from 1 to 10, but skip the number 5 using the `continue` statement.

```javascript
for (let i = 1; i <= 10; i++) {
  if (i === 5) continue;
  console.log(i);
}

/*
Expected Output:
1
2
3
4
6
7
8
9
10
*/
```

**Task 9:** Write a program to print numbers from 1 to 10, but stop the loop when the number is 7 using the `break` statement.

```javascript
for (let i = 1; i <= 10; i++) {
  if (i === 7) break;
  console.log(i);
}

/*
1
2
3
4
5
6
*/
```

## Feature Request:

1. Number Printing Script: Write a script that prints numbers from 1 to 10 using a `for` loop and a while loop.

2. Multiplication Table Script: Create a script that prints the multiplication table of 5 using a `for` loop.

3. Pattern Printing Script: Write a script that prints a pattern of stars using nested loops.

4. Sum Calculation Script: Write a script that calculates the sum of numbers from 1 to 10 using a `while` loop.

5. Factorial Calculation Script: Create a script that calculates the factorial of a number using a `do...while` loop.

## Achievements:

By the end of these activities, students will:

- Understand and use `for` loops to iterate over a sequence of numbers.

- Utilize `while` loops for iteration based on a condition.

- Apply `do...while` loops to ensure the loop body is executed at least once.

- Implement nested loops to solve more complex problems.

- Use loop control statements (`break` and `continue`) to control the flow of loops.
