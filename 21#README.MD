# Day 21: LeetCode Easy

## Table of Contents

1.  [Activity 1: Two Sum](#activity-1-two-sum)
2.  [Activity 2: Reverse Integer](#activity-2-reverse-integer)
3.  [Activity 3: Palindrome Number](#activity-3-palindrome-number)
4.  [Activity 4: Merge Two Sorted Lists](#activity-4-merge-two-sorted-lists)
5.  [Activity 5: Valid Parentheses](#activity-5-valid-parentheses)
6.  [Feature Request](#feature-request)
7.  [Achievements](#achievements)

## Activity 1: Two Sum

- Task 1: Solve the "Two Sum" problem on LeetCode.
- Write a function that takes an array of numbers and a target number, and returns the indices of the two numbers that add up to the target.
- Log the indices for a few test cases.

```js
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function (nums, target) {
  let numMap = new Map();
  let n = nums.length;
  /*
        This is a logic
        a + b = sum;
        b = sum - a;
    */

  for (let i = 0; i < n; i++) {
    let complement = target - nums[i];
    if (numMap.has(complement)) {
      return [numMap.get(complement), i];
    }
    numMap.set(nums[i], i);
  }

  return []; // No solution found
};
```

## Activity 2: Reverse Integer

- Task 2: Solve the "Reverse Integer" problem on LeetCode.
- Write a function that takes an integer and returns it with its digits reversed.
- Handle edge cases like negative numbers and numbers ending in zero.
- Log the reversed integers for a few test cases.

```js
/**
 * @param {number} x
 * @return {number}
 */
var reverse = function (x) {
  let reversed = 0;
  let temp = Math.abs(x);

  while (temp > 0) {
    let digit = temp % 10;
    reversed = reversed * 10 + digit;
    temp = Math.floor(temp / 10);
  }

  // Check if the reversed integer fits within the range of a 32-bit signed integer
  if (reversed >= -Math.pow(2, 31) && reversed <= Math.pow(2, 31) - 1) {
    // Return reversed integer if overflow does not occur
    return x < 0 ? -reversed : reversed;
  } else {
    // Return 0 if overflow occurs
    return 0;
  }
};
```

## Activity 3: Palindrome Number

- Task 3: Solve the "Palindrome Number" problem on LeetCode.
- Write a function that takes an integer and returns true if it is a palindrome, and false otherwise.
- Log the result for a few test cases, including edge cases like negative numbers.

```js
/**
 * @param {number} x
 * @return {boolean}
 */
var isPalindrome = function (x) {
  // Corner Case: for negative number is always non-palindrome
  if (x < 0) {
    return false;
  }

  let reversed = 0;
  let temp = x;

  while (temp !== 0) {
    let digit = temp % 10;
    reversed = reversed * 10 + digit;
    temp = Math.floor(temp / 10);
  }

  return reversed === x;
};
```

## Activity 4: Merge Two Sorted Lists

- Task 4: Solve the "Merge Two Sorted Lists" problem on LeetCode.
- Write a function that takes two sorted linked lists and returns a new sorted list by merging them.
- Create a few test cases with linked lists and log the merged list.

```js
/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} l1
 * @param {ListNode} l2
 * @return {ListNode}
 */
var mergeTwoLists = function (l1, l2) {
  if (!l1) return l2;
  if (!l2) return l1;

  let ans = new ListNode(0);
  let current = ans;

  while (l1 && l2) {
    if (l1.val <= l2.val) {
      current.next = l1;
      current = l1;
      l1 = l1.next;
    } else {
      current.next = l2;
      current = l2;
      l2 = l2.next;
    }
  }

  if (l1 !== null) {
    current.next = l1;
  }

  if (l2 !== null) {
    current.next = l2;
  }

  return ans.next;
};
```

## Activity 5: Valid Parentheses

- Task 5: Solve the "Valid Parentheses" problem on LeetCode.
- Write a function that takes a string containing just the characters `'('`,`')'`, `''`, `'}'`, `'T'` and `']'`, and determines if the input string is valid.
- A string is valid if open brackets are closed in the correct order.
- Log the result for a few test cases.

```js
/**
 * @param {string} s
 * @return {boolean}
 */
var isValid = function (s) {
  let stack = [];

  for (let i = 0; i < s.length; i++) {
    let bracket = s[i];

    if (bracket === "(" || bracket === "{" || bracket === "[") {
      stack.push(bracket);
    } else {
      if (stack.length > 0) {
        if (
          (bracket === ")" && stack[stack.length - 1] === "(") ||
          (bracket === "}" && stack[stack.length - 1] === "{") ||
          (bracket === "]" && stack[stack.length - 1] === "[")
        ) {
          // Stack is not empty, and we a a matched bracket of stack top so pop the top from stack
          stack.pop();
        } else {
          // Stack is not empty, but we have a not matched bracket of stack top so invalid parentheses
          return false;
        }
      } else {
        // Stack is empty, but we have a bracket so invalid parentheses
        return false;
      }
    }
  }

  // if stack is empty it means string have valid parentheses
  return stack.length === 0;
};
```

## Feature Request:

---

1. **Two Sum Script:** Write a script that includes a function to solve the "Two Sum" problem and logs the indices of the two numbers.
2. **Reverse Integer Script:** Create a script that includes a function to reverse an integer and handles edge cases.
3. **Palindrome Number Script:** Write a script that includes a function to check if an integer is a palindrome and logs the result.
4. **Merge Two Sorted Lists Script:** Create a script that includes a function to merge two sorted linked lists and logs the merged list.
5. **Valid Parentheses Script:** Write a script that includes a function to check if a string of parentheses is valid and logs the result.

## Achievements:

By the end of these activities, students will:

- Solve common LeetCode problems.
- Apply problem-solving skills to implement algorithms.
- Understand and handle edge cases in algorithmic solutions.
- Gain confidence in solving easy-level coding challenges on LeetCode.
