# Day 11: Promises and Async/Awaitin Javascript

Welcome to Day 11 of JavaScript Basics! Today, we'll explore Promises and Async/Await. We'll cover creating and handling promises, chaining promises, using async/await, fetching data from APIs, and handling multiple concurrent promises. This session will help you understand asynchronous programming in JavaScript.

## Table of Contents

1. [Activity 1: Understanding Promises](#activity-1-understanding-promises)
   - Task 1: Create a Promise that Resolves
   - Task 2: Create a Promise that Rejects
2. [Activity 2: Chaining Promises](#activity-2-chaining-promises)
   - Task 3: Sequence of Promises
3. [Activity 3: Using Async/Await](#activity-3-using-asyncawait)
   - Task 4: Async Function with Resolved Promise
   - Task 5: Async Function with Rejected Promise
4. [Activity 4: Fetching Data from an API](#activity-4-fetching-data-from-an-api)
   - Task 6: Fetch API with Promises
   - Task 7: Fetch API with Async/Await
5. [Activity 5: Concurrent Promises](#activity-5-concurrent-promises)
   - Task 8: Using `Promise.all`
   - Task 9: Using `Promise.race`
6. [Feature Request](#feature-request)
7. [Achievements](#achievements)

## Activity 1: Understanding Promises

**Task 1:** Create a promise that resolves with a message after a 2-second timeout and log the message to the console.

```js
const resolvePromise = new Promise((resolve) => {
  setTimeout(() => {
    resolve("Promise resolved after 2 seconds");
  }, 2000);
});

resolvePromise.then((message) => {
  console.log(message); // Promise resolved after 2 seconds
});
```

**Task 2:** Create a promise that rejects with an error message after a 2-second timeout and handle the error using `.catch()`.

```js
const rejectPromise = new Promise((_, reject) => {
  setTimeout(() => {
    reject("Promise rejected after 2 seconds");
  }, 2000);
});

rejectPromise.catch((error) => {
  console.error(error); // Promise rejected after 2 seconds
});
```

## Activity 2: Chaining Promises

**Task 3:** Create a sequence of promises that simulate fetching data from a server. Chain the promises to log messages in a specific order.

```js
const fetchData = (data, delay) => {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve(data);
    }, delay);
  });
};

fetchData("Fetching data from server 1", 1000)
  .then((message) => {
    console.log(message); // Fetching data from server 1
    return fetchData("Fetching data from server 2", 1000);
  })
  .then((message) => {
    console.log(message); // Fetching data from server 2
    return fetchData("Fetching data from server 3", 1000);
  })
  .then((message) => {
    console.log(message); // Fetching data from server 3
  });
```

## Activity 3: Using Async/Await

**Task 4:** Write an async function that waits for a promise to resolve and then logs the resolved value.

```js
const asyncResolve = async () => {
  const promise = new Promise((resolve) => {
    setTimeout(() => {
      resolve("Resolved value from async function");
    }, 2000);
  });

  const result = await promise;
  console.log(result); // Resolved value from async function
};

asyncResolve();
```

**Task 5:** Write an async function that handles a rejected promise using try-catch and logs the error message.

```js
const asyncReject = async () => {
  const promise = new Promise((_, reject) => {
    setTimeout(() => {
      reject("Rejected value from async function");
    }, 2000);
  });

  try {
    const result = await promise;
    console.log(result);
  } catch (error) {
    console.error(error); // Rejected value from async function
  }
};

asyncReject();
```

## Activity 4: Fetching Data from an API

**Task 6:** Use the fetch API to get data from a public API and log the response data to the console using promises.

```js
fetch("https://jsonplaceholder.typicode.com/posts")
  .then((response) => response.json())
  .then((data) => {
    console.log(data);
  })
  .catch((error) => {
    console.error("Error fetching data:", error);
  });

/*
[
  {
    "userId": 1,
    "id": 1,
    "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
    "body": "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto"
  },
  {
    "userId": 1,
    "id": 2,
    "title": "qui est esse",
    "body": "est rerum tempore vitae\nsequi sint nihil reprehenderit dolor beatae ea dolores neque\nfugiat blanditiis voluptate porro vel nihil molestiae ut reiciendis\nqui aperiam non debitis possimus qui neque nisi nulla"
  }
]
*/
```

**Task 7:** Use the fetch API to get data from a public API and log the response data to the console using async/await.

```js
const fetchDataAsync = async () => {
  try {
    const response = await fetch("https://jsonplaceholder.typicode.com/posts");
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error("Error fetching data:", error);
  }
};

fetchDataAsync();
/*
[
  {
    "userId": 1,
    "id": 1,
    "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
    "body": "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto"
  },
  {
    "userId": 1,
    "id": 2,
    "title": "qui est esse",
    "body": "est rerum tempore vitae\nsequi sint nihil reprehenderit dolor beatae ea dolores neque\nfugiat blanditiis voluptate porro vel nihil molestiae ut reiciendis\nqui aperiam non debitis possimus qui neque nisi nulla"
  }
]
*/
```

## Activity 5: Concurrent Promises

**Task 8:** Use `Promise.all` to wait for multiple promises to resolve and then log all their values.
**Task 9:** Use `Promise.race` to log the value of the first promise that resolves among multiple promises.

```js
// Task 8
const promise1 = new Promise((resolve) =>
  setTimeout(resolve, 1000, "First promise")
);
const promise2 = new Promise((resolve) =>
  setTimeout(resolve, 2000, "Second promise")
);
const promise3 = new Promise((resolve) =>
  setTimeout(resolve, 3000, "Third promise")
);

Promise.all([promise1, promise2, promise3]).then((values) => {
  console.log("All promises resolved:", values);
});

// Task 9
Promise.race([promise1, promise2, promise3]).then((value) => {
  console.log("First promise resolved:", value);
});

/*
First promise resolved: First promise
All promises resolved: [ 'First promise', 'Second promise', 'Third promise' ]
*/
```

## Feature Request

1. **Promise Creation Script:** Write a script that demonstrates creating and handling promises, including both resolved and rejected states.
2. **Promise Chaining Script:** Create a script that chains multiple promises and logs messages in a specific sequence.
3. **Async/Await Script:** Write a script that uses async/await to handle promises and includes error handling with try-catch.
4. **API Fetch Script:** Create a script that fetches data from a public API using both promises and async/await, and logs the response data.
5. **Concurrent Promises Script:** Write a script that uses `Promise.all` and `Promise.race` to handle multiple promises concurrently and logs the results.

## Achievements

By the end of these activities, students will:

- Understand and create promises, including handling resolved and rejected states.
- Chain multiple promises to perform sequential asynchronous operations.
- Use async/await to handle asynchronous code more readably.
- Fetch data from public APIs using both promises and async/await.
- Manage multiple concurrent promises using `Promise.all` and `Promise.race`.
