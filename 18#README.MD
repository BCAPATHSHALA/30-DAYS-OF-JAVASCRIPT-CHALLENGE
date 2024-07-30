# Day 18: Algorithms in JavaScript

Welcome to Algorithm Activities! In these activities, we will explore various fundamental algorithms through tasks and practical examples. By the end of these activities, you'll have a solid understanding of how to implement and use different algorithms effectively in programming.

## Table of Contents

1. [Activity 1: Sorting Algorithms](#activity-1-sorting-algorithms)
2. [Activity 2: Searching Algorithms](#activity-2-searching-algorithms)
3. [Activity 3: String Algorithms](#activity-3-string-algorithms)
4. [Activity 4: Array Algorithms](#activity-4-array-algorithms)
5. [Activity 5: Dynamic Programming (Optional)](#activity-5-dynamic-programming-optional)
6. [Feature Request](#feature-request)
7. [Achievements](#achievements)

## Activity 1: Sorting Algorithms

**Task 1:** Implement the bubble sort algorithm to sort an array of numbers in ascending order. Log the sorted array.

```js
function bubbleSort(arr) {
  let n = arr.length;
  for (let i = 0; i < n - 1; i++) {
    for (let j = 0; j < n - i - 1; j++) {
      if (arr[j] > arr[j + 1]) {
        let temp = arr[j];
        arr[j] = arr[j + 1];
        arr[j + 1] = temp;
      }
    }
  }
  return arr;
}

console.log(bubbleSort([64, 34, 25, 12, 22, 11, 90])); // Output: [11, 12, 22, 25, 34, 64, 90]
```

**Task 2:** Implement the selection sort algorithm to sort an array of numbers in ascending order. Log the sorted array.

```js
function selectionSort(arr) {
  let n = arr.length;
  for (let i = 0; i < n - 1; i++) {
    let minIndex = i;
    for (let j = i + 1; j < n; j++) {
      if (arr[j] < arr[minIndex]) {
        minIndex = j;
      }
    }
    let temp = arr[minIndex];
    arr[minIndex] = arr[i];
    arr[i] = temp;
  }
  return arr;
}

console.log(selectionSort([64, 34, 25, 12, 22, 11, 90])); // Output: [11, 12, 22, 25, 34, 64, 90]
```

**Task 3:** Implement the quicksort algorithm to sort an array of numbers in ascending order. Log the sorted array.

```js
function quickSort(arr) {
  if (arr.length <= 1) {
    return arr;
  }
  let pivot = arr[Math.floor(arr.length / 2)];
  let left = [];
  let right = [];
  for (let i = 0; i < arr.length; i++) {
    if (i !== Math.floor(arr.length / 2)) {
      arr[i] < pivot ? left.push(arr[i]) : right.push(arr[i]);
    }
  }
  return quickSort(left).concat(pivot, quickSort(right));
}

console.log(quickSort([64, 34, 25, 12, 22, 11, 90])); // Output: [11, 12, 22, 25, 34, 64, 90]
```

## Activity 2: Searching Algorithms

**Task 4:** Implement the linear search algorithm to find a target value in an array. Log the index of the target value.

```js
function linearSearch(arr, target) {
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] === target) {
      return i;
    }
  }
  return -1;
}

console.log(linearSearch([64, 34, 25, 12, 22, 11, 90], 22)); // Output: 4
```

**Task 5:** Implement the binary search algorithm to find a target value in a sorted array. Log the index of the target value.

```js
function binarySearch(arr, target) {
  let left = 0;
  let right = arr.length - 1;
  while (left <= right) {
    let mid = Math.floor(left + (right - left) / 2);
    if (arr[mid] === target) {
      return mid;
    } else if (arr[mid] < target) {
      left = mid + 1;
    } else {
      right = mid - 1;
    }
  }
  return -1;
}

console.log(binarySearch([11, 12, 22, 25, 34, 64, 90], 22)); // Output: 2
console.log(binarySearch([11, 12, 22, 25, 34, 64, 90], 202)); // Output: -1
```

## Activity 3: String Algorithms

**Task 6:** Write a function to count the occurrences of each character in a string. Log the character counts.

```js
function charCount(str) {
  let count = {};
  for (let char of str) {
    count[char] = count[char] + 1 || 1;
  }
  return count;
}

console.log(charCount("hello")); // Output: { h: 1, e: 1, l: 2, o: 1 }
```

**Task 7:** Write a function to find the longest substring without repeating characters in a string. Log the length of the substring.

```js
function longestSubstring(str) {
  let maxLength = 0;
  let start = 0;
  let seen = {};
  for (let end = 0; end < str.length; end++) {
    if (seen[str[end]] !== undefined) {
      start = Math.max(start, seen[str[end]] + 1);
    }
    seen[str[end]] = end;
    maxLength = Math.max(maxLength, end - start + 1);
  }
  return maxLength;
}

console.log(longestSubstring("abcabcbb")); // Output: 3 (abc)
```

## Activity 4: Array Algorithms

**Task 8:** Write a function to rotate an array by `k` positions. Log the rotated array.

```js
function rotateArray(arr, k) {
  k = k % arr.length;
  return arr.slice(-k).concat(arr.slice(0, -k));
}

console.log(rotateArray([1, 2, 3, 4, 5, 6, 7], 3)); // Output: [5, 6, 7, 1, 2, 3, 4]
```

**Task 9:** Write a function to merge two sorted arrays into one sorted array. Log the merged array.

```js
function mergeArrays(arr1, arr2) {
  let merged = [];
  let i = 0;
  let j = 0;
  while (i < arr1.length && j < arr2.length) {
    if (arr1[i] < arr2[j]) {
      merged.push(arr1[i]);
      i++;
    } else {
      merged.push(arr2[j]);
      j++;
    }
  }
  return merged.concat(arr1.slice(i)).concat(arr2.slice(j));
}

console.log(mergeArrays([1, 3, 5], [2, 4, 6])); // Output: [1, 2, 3, 4, 5, 6]
```

## Activity 5: Dynamic Programming (Optional)

**Task 10:** Write a function to solve the Fibonacci sequence using dynamic programming. Log the Fibonacci numbers.

```js
function fibonacci(n) {
  let fib = [0, 1];
  for (let i = 2; i <= n; i++) {
    fib[i] = fib[i - 1] + fib[i - 2];
  }
  return fib;
}

console.log(fibonacci(10)); // Output: [0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55]
```

**Task 11:** Write a function to solve the knapsack problem using dynamic programming. Log the maximum value that can be obtained.

```js
function knapsack(weights, values, capacity) {
  let n = weights.length;
  let dp = Array(n + 1)
    .fill()
    .map(() => Array(capacity + 1).fill(0));
  for (let i = 1; i <= n; i++) {
    for (let w = 0; w <= capacity; w++) {
      if (weights[i - 1] <= w) {
        dp[i][w] = Math.max(
          dp[i - 1][w],
          dp[i - 1][w - weights[i - 1]] + values[i - 1]
        );
      } else {
        dp[i][w] = dp[i - 1][w];
      }
    }
  }
  return dp[n][capacity];
}

console.log(knapsack([1, 2, 3], [10, 15, 40], 6)); // Output: 55
```

## Feature Request

1. **Sorting Algorithm Script:** Write a script that implements bubble sort, selection sort, and quicksort algorithms to sort arrays.
2. **Searching Algorithm Script:** Create a script that implements linear search and binary search algorithms to find values in arrays.
3. **String Algorithm Script:** Write a script that counts character occurrences and finds the longest substring without repeating characters.
4. **Array Algorithm Script:** Create a script that rotates arrays and merges sorted arrays.
5. **Dynamic Programming Script:** Write a script that solves the Fibonacci sequence and knapsack problem using dynamic programming (optional).

## Achievements:

By the end of these activities, students will:

- Implement and understand common sorting algorithms.
- Implement and understand common searching algorithms.
- Solve string manipulation problems using algorithms.
- Perform array operations using algorithms.
- Apply dynamic programming to solve complex problems (optional).
