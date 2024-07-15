# Day 3: Control Structures in JavaScript

Welcome to Day 3 of JavaScript Basics! Today, we'll be focusing on control structures. This includes if-else statements, nested if-else statements, switch case statements, and the ternary operator.

## Table of Contents

1. [Activity 1: If-Else Statements](#activity-1-if-else-statements)
   - Task 1: Number Check
   - Task 2: Voting Eligibility
2. [Activity 2: Nested If-Else Statements](#activity-2-nested-if-else-statements)
   - Task 3: Find the Largest Number
3. [Activity 3: Switch Case](#activity-3-switch-case)
   - Task 4: Day of the Week
   - Task 5: Grade Assignment
4. [Activity 4: Conditional (Ternary) Operator](#activity-4-conditional-ternary-operator)
   - Task 6: Even or Odd Check
5. [Activity 5: Combining Conditions](#activity-5-combining-conditions)
   - Task 7: Leap Year Check
6. [Feature Request](#feature-request)
   - 1. Number Check Script
   - 2. Voting Eligibility Script
   - 3. Day of the Week Script
   - 4. Grade Assignment Script
   - 5. Leap Year Check Script
7. [Achievements](#achievements)

## Activity 1: If-Else Statements

**Task 1:** Write a program to check if a number is positive, negative, or zero, and log the result to the console.

```javascript
function checkNumber(num) {
  if (num > 0) {
    console.log("The number is positive.");
  } else if (num < 0) {
    console.log("The number is negative.");
  } else {
    console.log("The number is zero.");
  }
}

checkNumber(5); // Output: The number is positive.
checkNumber(-3); // Output: The number is negative.
checkNumber(0); // Output: The number is zero.
```

**Task 2:** Write a program to check if a person is eligible to vote (age >= 18) and log the result to the console.

```javascript
function checkVotingEligibility(age) {
  if (age >= 18) {
    console.log("The person is eligible to vote.");
  } else {
    console.log("The person is not eligible to vote.");
  }
}

checkVotingEligibility(20); // Output: The person is eligible to vote.
checkVotingEligibility(16); // Output: The person is not eligible to vote.
```

## Activity 2: Nested If-Else Statements

**Task 3:** Write a program to find the largest of three numbers using nested if-else statements.

```javascript
function findLargest(a, b, c) {
  if (a >= b) {
    if (a >= c) {
      console.log(`The largest number is ${a}.`);
    } else {
      console.log(`The largest number is ${c}.`);
    }
  } else {
    if (b >= c) {
      console.log(`The largest number is ${b}.`);
    } else {
      console.log(`The largest number is ${c}.`);
    }
  }
}

findLargest(3, 7, 5); // Output: The largest number is 7.
findLargest(10, 2, 8); // Output: The largest number is 10.
```

## Activity 3: Switch Case

**Task 4:** Write a program that uses a switch case to determine the day of the week based on a number (1-7) and log the day name to the console.

```javascript
function getDayOfWeek(dayNumber) {
  switch (dayNumber) {
    case 1:
      console.log("Sunday");
      break;
    case 2:
      console.log("Monday");
      break;
    case 3:
      console.log("Tuesday");
      break;
    case 4:
      console.log("Wednesday");
      break;
    case 5:
      console.log("Thursday");
      break;
    case 6:
      console.log("Friday");
      break;
    case 7:
      console.log("Saturday");
      break;
    default:
      console.log("Invalid day number. Please enter a number between 1 and 7.");
  }
}

getDayOfWeek(1); // Output: Sunday
getDayOfWeek(5); // Output: Thursday
```

**Task 5:** Write a program that uses a switch case to assign a grade ('A', 'B', 'C', 'D', 'F') based on a score and log the grade to the console.

```javascript
function getGrade(score) {
  let grade;
  switch (true) {
    case score >= 90:
      grade = "A";
      break;
    case score >= 80:
      grade = "B";
      break;
    case score >= 70:
      grade = "C";
      break;
    case score >= 60:
      grade = "D";
      break;
    default:
      grade = "F";
  }
  console.log(`The grade is ${grade}.`);
}

getGrade(85); // Output: The grade is B.
getGrade(72); // Output: The grade is C.
```

## Activity 4: Conditional (Ternary) Operator

**Task 6:** Write a program that uses the ternary operator to check if a number is even or odd and log the result to the console.

```javascript
function checkEvenOdd(num) {
  const result = num % 2 === 0 ? "The number is even." : "The number is odd.";
  console.log(result);
}

checkEvenOdd(4); // Output: The number is even.
checkEvenOdd(7); // Output: The number is odd.
```

## Activity 5: Combining Conditions

**Task 7:** Write a program to check if a year is a leap year using multiple conditions (divisible by 4, but not 100 unless also divisible by 400) and log the result to the console.

```javascript
function isLeapYear(year) {
  if ((year % 4 === 0 && year % 100 !== 0) || year % 400 === 0) {
    console.log(`${year} is a leap year.`);
  } else {
    console.log(`${year} is not a leap year.`);
  }
}

isLeapYear(2020); // Output: 2020 is a leap year.
isLeapYear(1900); // Output: 1900 is not a leap year.
isLeapYear(2000); // Output: 2000 is a leap year.
```

## Feature Request:

1. **Number Check Script:** Write a script that checks if a number is positive, negative, or zero using if-else statements and logs the result.
2. **Voting Eligibility Script:** Create a script to check if a person is eligible to vote based on their age and log the result.
3. **Day of the Week Script:** Write a script that uses a switch case to determine the day of the week based on a number (1-7) and logs the day name.
4. **Grade Assignment Script:** Create a script that uses a switch case to assign a grade based on a score and logs the grade.
5. **Leap Year Check Script:** Write a script that checks if a year is a leap year using multiple conditions and logs the result.

## Achievements:

By the end of these activities, students will:

- Implement and understand basic if-else control flow.
- Use nested if-else statements to handle multiple conditions.
- Utilize switch cases for control flow based on specific values.
- Apply the ternary operator for concise condition checking.
- Combine multiple conditions to solve more complex problems.
