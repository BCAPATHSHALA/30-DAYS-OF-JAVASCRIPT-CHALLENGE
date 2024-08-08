# Day 22: LeetCode Medium

## Table of Contents

1.  [Activity 1: Add Two Numbers](#activity-1-add-two-numbers)
2.  [Activity 2: Longest Substring Without Repeating Characters](#activity-2-longest-substring-without-repeating-characters)
3.  [Activity 3: Container With Most Water](#activity-3-container-with-most-water)
4.  [Activity 4: 3Sum](#activity-4-3sum)
5.  [Activity 5: Group Anagrams](#activity-5-group-anagrams)
6.  [Feature Request](#feature-request)
7.  [Achievements](#achievements)

## Activity 1: Add Two Numbers

- Task 1: Solve the **"Add Two Numbers"** problem on LeetCode.
- Write a function that takes two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order, and each node contains a single digit. Add the two numbers and return the sum as a linked
  list.
- Create a few test cases with linked lists and log the sum as a linked list.

```js
/**
 * @param {ListNode} l1
 * @param {ListNode} l2
 * @return {ListNode}
 */
var addTwoNumbers = function (l1, l2) {
  let dummyHead = new ListNode(0);
  let current = dummyHead;
  let carry = 0;

  while (l1 !== null || l2 !== null || carry !== 0) {
    let sum = (l1 !== null ? l1.val : 0) + (l2 !== null ? l2.val : 0) + carry;
    carry = Math.floor(sum / 10);
    let val = sum % 10;

    current.next = new ListNode(val);
    current = current.next;

    l1 = l1 !== null ? l1.next : null;
    l2 = l2 !== null ? l2.next : null;
  }

  return dummyHead.next;
};
```

## Activity 2: Longest Substring Without Repeating Characters 🙋🏻‍♂️

- Task 2: Solve the **"Longest Substring Without Repeating Characters"** problem on LeetCode.
- Write a function that takes a string and returns the length of the longest substring without repeating characters.
- Log the length for a few test cases, including edge cases.

```js
/**
 * @param {string} s
 * @return {number}
 */
var lengthOfLongestSubstring = function (s) {
  let chars = new Set(); // to store characters in the current window
  let maxSize = 0;
  let left = 0,
    right = 0; // pointers for the sliding window

  while (right < s.length) {
    // if the current character at s[right] is already in the set
    while (chars.has(s[right])) {
      // remove characters from the set and move the left pointer to the right
      chars.delete(s[left]);
      left++;
    }

    // update the maximum length found so far
    maxSize = Math.max(maxSize, right - left + 1);

    // add the current character to the set and move the right pointer to the right
    chars.add(s[right]);
    right++;
  }

  return maxSize;
};
```

## Activity 3: Container With Most Water 🙋🏻‍♂️

- Task 3: Solve the **"Container With Most Water"** problem on LeetCode.
- Write a function that takes an array of non-negative integers where each integer represents the height of a line drawn at each point. Find two lines that together with the x-axis form a container, such that the container holds the most water.
- Log the maximum amount of water for a few test cases.

```js
/**
 * @param {number[]} height
 * @return {number}
 */
var maxArea = function (height) {
  let i = 0;
  let j = height.length - 1;
  let maxi = 0;

  while (i < j) {
    let h = Math.min(height[i], height[j]);
    let w = j - i;
    let area = h * w;
    maxi = Math.max(area, maxi);

    if (height[i] < height[j]) {
      i++;
    } else {
      j--;
    }
  }

  return maxi;
};
```

## Activity 4: 3Sum

- Task 4: Solve the **"3Sum"** problem on LeetCode.
- Write a function that takes an array of integers and finds all unique triplets in the array which give the sum of zero.
- Log the triplets for a few test cases, including edge cases.

```js
/**
 * @param {number[]} nums
 * @return {number[][]}
 */
var threeSum = function (nums) {
  let result = [];

  nums.sort((a, b) => a - b);

  for (let i = 0; i < nums.length; i++) {
    if (i > 0 && nums[i] === nums[i - 1]) {
      continue;
    }
    let n1 = nums[i];
    let target = -n1;
    let startIndex = i + 1;
    let endIndex = nums.length - 1;
    twoSum(nums, target, startIndex, endIndex);
  }

  function twoSum(nums, target, i, j) {
    while (i < j) {
      if (nums[i] + nums[j] > target) {
        j--;
      } else if (nums[i] + nums[j] < target) {
        i++;
      } else {
        while (i < j && nums[i] === nums[i + 1]) i++;
        while (i < j && nums[j] === nums[j - 1]) j--;
        result.push([-target, nums[i], nums[j]]);
        i++;
        j--;
      }
    }
  }

  return result;
};
```

## Activity 5: Group Anagrams

- Task 5: Solve the **"Group Anagrams"** problem on LeetCode.
- Write a function that takes an array of strings and groups anagrams together.
- Log the grouped anagrams for a few test cases.

```js
/**
 * @param {string[]} strs
 * @return {string[][]}
 */
var groupAnagrams = function (strs) {
  function hash(s) {
    let hash = new Array(256).fill(0);
    for (let i = 0; i < s.length; i++) {
      hash[s.charCodeAt(i)]++;
    }
    return hash;
  }

  let mp = new Map();

  for (let str of strs) {
    let hashArray = hash(str);
    let hashString = hashArray.join(",");
    if (mp.has(hashString)) {
      mp.get(hashString).push(str);
    } else {
      mp.set(hashString, [str]);
    }
  }

  let result = [];
  for (let value of mp.values()) {
    result.push(value);
  }

  return result;
};
```

## Feature Request

1. **Add Two Numbers Script:** Write a script that includes a function to solve the "Add Two Numbers" problem and logs the sum as a linked list.
2. **Longest Substring Script:** Create a script that includes a function to find the longest substring without repeating characters and logs the length.
3. **Container With Most Water Script:** Write a script that includes a function to find the container with the most water and logs the maximum amount of water.
4. **3Sum Script:** Create a script that includes a function to find all unique triplets in an array that sum to zero and logs the triplets.
5. **Group Anagrams Script:** Write a script that includes a function to group anagrams and logs the grouped anagrams.

## Achievements

- Solve common medium-level LeetCode problems.
- Apply advanced problem-solving skills to implement algorithms.
- Understand and handle edge cases in more complex algorithmic solutions.
- Gain confidence in solving medium-level coding challenges on LeetCode.
