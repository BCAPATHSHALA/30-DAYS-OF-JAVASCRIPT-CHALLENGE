# Day 16: Recursion in JavaScript

Welcome to Recursion Activities! In these activities, we will explore the concept of recursion through various tasks and practical examples. By the end of these activities, you'll have a solid understanding of how to use recursion effectively in programming.

## Table of Contents

1. [Activity 1: Basic Recursion](#activity-1-basic-recursion)
2. [Activity 2: Recursion with Arrays](#activity-2-recursion-with-arrays)
3. [Activity 3: String Manipulation with Recursion](#activity-3-string-manipulation-with-recursion)
4. [Activity 4: Recursive Search](#activity-4-recursive-search)
5. [Activity 5: Tree Traversal (Optional)](#activity-5-tree-traversal-optional)
6. [Feature Request](#feature-request)
7. [Achievements](#achievements)

## Activity 1: Basic Recursion

**Task 1:** Write a recursive function to calculate the _factorial of a number_. Log the result for a few test cases.

```js
function factorial(n) {
  // Base Case
  if (n === 0) {
    return 1;
  }

  // Recursive Relation
  let recursionAns = n * factorial(n - 1); // 5: 5 * (5-1) * (5-2) * (5-3) * (5-4) * (5-5)
  return recursionAns;
}

console.log(factorial(5)); // 120
console.log(factorial(6)); // 720
```

**Task 2:** Write a recursive function to calculate the _nth Fibonacci number_. Log the result for a few test cases.

```js
function fibonacci(n) {
  // Base Case
  if (n <= 1) {
    return n;
  }

  // Recursive Relation
  let a = fibonacci(n - 1);
  let b = fibonacci(n - 2);
  let recursionAns = a + b;

  return recursionAns;
}

console.log(fibonacci(5)); // 5: 0, 1, 1, 2, 3
console.log(fibonacci(6)); // 8: 0, 1, 1, 2, 3, 5, 8, 13
```

## Activity 2: Recursion with Arrays

**Task 3:** Write a recursive function to find the _sum of all elements in an array_. Log the result for a few test cases.

```js
function sumArray(arr) {
  // Base Case
  if (arr.length === 0) {
    return 0;
  }

  // Recursive Relation
  let recursionAns = arr[0] + sumArray(arr.slice(1));
  return recursionAns;
}

console.log(sumArray([1, 2, 3, 4, 5])); // 15
console.log(sumArray([10, 20, 30])); // 60

/*
DRY RUN ON [1, 2, 3, 4, 5]
CALL STACK OF THE FUNCTION:
Call 1: [ 1, 2, 3, 4, 5 ]: Return recursionAns 6: 1 + 14 = 15
Call 2: [ 2, 3, 4, 5 ]: Return recursionAns 5: 2 + 12 = 14
Call 3: [ 3, 4, 5 ]: Return recursionAns 4: 3 + 9 = 12
Call 4: [ 4, 5 ]: Return recursionAns 3: 4 + 5 = 9
Call 5: [ 5 ] : Return recursionAns 2: 5 + 0 = 5
Call 6: [] : Return recursionAns 1: 0
*/
```

**Task 4:** Write a recursive function to find the _maximum element in an array_. Log the result for a few test cases.

```js
function maxArray(arr) {
  // Base Case
  if (arr.length === 1) {
    return arr[0];
  }

  // Recursive Relation
  let recursionAns = Math.max(arr[0], maxArray(arr.slice(1)));
  return recursionAns;
}

console.log(maxArray([1, 5, 3, 9, 2])); // 9
console.log(maxArray([10, 20, 30, 15])); // 30

/*
DRY RUN ON [1, 5, 3, 9, 2]
CALL STACK OF THE FUNCTION:
Call 1: [1, 5, 3, 9, 2]: Return recursionAns 5: max(1, 9) = 9
Call 2: [5, 3, 9, 2]: Return recursionAns 4: max(5, 9) = 9
Call 3: [3, 9, 2]: Return recursionAns 3: max(3, 9) = 9
Call 4: [9, 2]: Return recursionAns 2: max(9, 2) = 9
Call 5: [2] : Return recursionAns 1: max(2, 2) = 2
*/
```

## Activity 3: String Manipulation with Recursion

**Task 5:** Write a recursive function to _reverse a string_. Log the result for a few test cases.

```js
function reverseString(str) {
  // Base Case
  if (str === "") {
    return "";
  }

  // Recursive Relation
  let recursionAns = reverseString(str.slice(1)) + str[0];
  return recursionAns;
}

console.log(reverseString("hello")); // "olleh"
console.log(reverseString("world")); // "dlrow"

/*
DRY RUN ON "hello"
CALL STACK OF THE FUNCTION:
Call 1: "hello": Return recursionAns 6: "olle" + "h" = "olleh"
Call 2: "ello": Return recursionAns 5: "oll" + "e" = "olle"
Call 3: "llo": Return recursionAns 4: "ol" + "l" = "oll"
Call 4: "lo": Return recursionAns 3: "o" + "l" = "ol"
Call 5: "o" : Return recursionAns 2: "" + "o" = "o"
Call 6: "" : Return recursionAns 1: ""
*/
```

**Task 6:** Write a recursive function to _check if a string is a palindrome_. Log the result for a few test cases.

```js
function isPalindrome(str) {
  // Base Case 1
  if (str.length <= 1) {
    return true;
  }

  // Base Case 2
  if (str[0] !== str[str.length - 1]) {
    // If first and last char of string are not same, string is not palindrome
    return false;
  }

  // Recursive Relation
  let recursionAns = isPalindrome(str.slice(1, str.length - 1));
  return recursionAns;
}

console.log(isPalindrome("racecar")); // true
console.log(isPalindrome("hello")); // false

/*
DRY RUN ON "racecar"
CALL STACK OF THE FUNCTION:
Call 1: "racecar": Return recursionAns 4: 'r' === 'r' = true
Call 2: "aceca": Return recursionAns 3: 'a' === 'a' = true
Call 3: "cec": Return recursionAns 2: 'c' === 'c' = true
Call 4: "e": Return recursionAns 1: 'e' === 'e' = true
*/
```

## Activity 4: Recursive Search

**Task 7:** Write a recursive function to _perform a binary search on a sorted array_. Log the index of the target element for a few test cases.

```js
function binarySearch(arr, target, low = 0, high = arr.length - 1) {
  // Base Case
  if (low > high) {
    return -1;
  }

  // Processing + Recursive Relation
  let recursionAns;
  let mid = Math.floor(low + (high - low) / 2);

  // Target Found
  if (arr[mid] === target) {
    return mid;
  }

  // Go to left side from mid - 1 to low
  if (arr[mid] > target) {
    recursionAns = binarySearch(arr, target, low, mid - 1);
  }
  // Go to right side from mid + 1 to high
  if (arr[mid] < target) {
    recursionAns = binarySearch(arr, target, mid + 1, high);
  }

  return recursionAns;
}

console.log(binarySearch([1, 2, 3, 4, 5], 3)); // 2
console.log(binarySearch([10, 20, 30, 40, 50], 25)); // -1
```

**Task 8:** Write a recursive function to _count the occurrences of a target element in an array_. Log the result for a few test cases.

```js
function countOccurrences(arr, target) {
  // Base Case
  if (arr.length === 0) {
    return 0;
  }

  // Recursive Relation + Processing
  let recursionAns = countOccurrences(arr.slice(1), target);
  let isTargetFound = arr[0] === target ? 1 : 0;
  let count = isTargetFound + recursionAns;
  return count;
}

console.log(countOccurrences([1, 2, 3, 1, 4, 1], 1)); // 3
console.log(countOccurrences([10, 20, 30, 40, 50], 25)); // 0
```

## Activity 5: Tree Traversal (Optional)

**Task 9:** Write a recursive function to _perform an in-order traversal of a binary tree_. Log the nodes as they are visited.

```js
// Create the Binary Tree Node
class TreeNode {
  constructor(value) {
    this.value = value;
    this.left = null;
    this.right = null;
  }
}

// In-order Traversal Of A Binary Tree (Left-Node-Right)
function inOrderTraversal(root) {
  // Base Case
  if (root === null) {
    return;
  }

  // Recursive Relation + Processing
  // Left
  inOrderTraversal(root.left);
  // Node
  console.log(root.value);
  // Right
  inOrderTraversal(root.right);
}

const root = new TreeNode(1); // Create the root of BT: 1
root.left = new TreeNode(2); // Create the left child 2 of root of BT 1
root.right = new TreeNode(3); // Create the right child 3 of root of BT 1
root.left.left = new TreeNode(4); // Create the left child 4 of node of BT 2
root.left.right = new TreeNode(5); // Create the right child 4 of node of BT 2

inOrderTraversal(root); // 4 2 5 1 3
```

**Task 10:** Write a recursive function to _calculate the depth of a binary tree_. Log the result for a few test cases.

```js
function treeDepth(root) {
  // Base Case
  if (root === null) {
    return 0;
  }
  // Recursive Relation + Processing
  let leftSubTreeH = treeDepth(root.left);
  let rightSubTreeH = treeDepth(root.right);
  let heightOfBT = Math.max(leftSubTreeH + rightSubTreeH) + 1;
  return heightOfBT;
}

console.log(treeDepth(root)); // 3
```

## Feature Request

1. **Factorial and Fibonacci Script:** Write a script that includes recursive functions to calculate the factorial and Fibonacci numbers.
2. **Array Recursion Script:** Create a script that includes recursive functions to find the sum and maximum element of an array.
3. **String Recursion Script:** Write a script that includes recursive functions to reverse a string and check if a string is a palindrome.
4. **Recursive Search Script:** Create a script that includes recursive functions for binary search and counting occurrences in an array.
5. **Tree Traversal Script:** Write a script that includes recursive functions for in-order traversal and depth calculation of a binary tree (optional).

## Achievements

By the end of these activities, students will:

- Understand and implement basic recursion.
- Apply recursion to solve problems with arrays and strings.
- Use recursion for searching and counting elements in arrays.
- Perform tree traversal and calculate tree depth using recursion (optional).
