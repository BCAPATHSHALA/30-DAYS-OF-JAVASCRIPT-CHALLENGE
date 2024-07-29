# Day 17: Data Structures in JavaScript

Welcome to Data Structures Activities! In these activities, we will explore various fundamental data structures through tasks and practical examples. By the end of these activities, you'll have a solid understanding of how to implement and use different data structures effectively in programming.

## Table of Contents

1. [Activity 1: Linked List](#activity-1-linked-list)
2. [Activity 2: Stack](#activity-2-stack)
3. [Activity 3: Queue](#activity-3-queue)
4. [Activity 4: Binary Tree](#activity-4-binary-tree)
5. [Activity 5: Graph (Optional)](#activity-5-graph-optional)
6. [Feature Request](#feature-request)
7. [Achievements](#achievements)

## Activity 1: Linked List

**Task 1:** Implement a _Node_ class to represent an element in a linked list with properties _value_ and _next_.

```js
class Node {
  constructor(value) {
    this.value = value;
    this.next = null;
  }
}
```

**Task 2:** Implement a _LinkedList_ class with methods to add a node to the end, remove a node from the end, and display all nodes.

```js
class LinkedList {
  constructor() {
    this.head = null;
  }

  // Method 1: to add a node to the end of the linked list
  add(value) {
    const newNode = new Node(value);
    if (!this.head) {
      // When head is null, then newNode join to the next of head
      this.head = newNode;
    } else {
      // When head is not null, then newNode join to the next of tail
      let current = this.head;
      while (current.next) {
        current = current.next;
      }
      current.next = newNode;
    }
  }

  // Method 2: to remove a node from the end of the linked list
  remove() {
    if (!this.head) return null;

    if (!this.head.next) {
      const value = this.head.value;
      this.head = null;
      return value;
    }

    let current = this.head;
    while (current.next.next) {
      current = current.next;
    }

    const value = current.next.value;
    current.next = null;
    return value;
  }

  // Method 3: to display all nodes of the linked list
  display() {
    let current = this.head;
    while (current) {
      console.log(current.value);
      current = current.next;
    }
  }
}

// Example usage
const list = new LinkedList();
list.add(1);
list.add(2);
list.add(3);
list.display(); // 1 2 3
console.log(list.remove()); // 3
list.display(); // 1 2
```

## Activity 2: Stack

**Task 3:** Implement a _Stack_ class with methods _push_ (add element), _pop_ (remove element), and _peek_ (view the top element).

```js
class Stack {
  constructor() {
    this.items = [];
  }

  push(value) {
    this.items.push(value);
  }

  pop() {
    if (this.items.length === 0) return null;
    return this.items.pop();
  }

  peek() {
    if (this.items.length === 0) return null;
    return this.items[this.items.length - 1];
  }
}

// Example usage
const stack = new Stack();
stack.push(1);
stack.push(2);
stack.push(3);
console.log(stack.peek()); // 3
console.log(stack.pop()); // 3
console.log(stack.pop()); // 2
console.log(stack.pop()); // 1
console.log(stack.pop()); // null
```

**Task 4:** Use the _Stack_ class to reverse a string by pushing all characters onto the stack and then popping them off.

```js
function reverseString(str) {
  // pushing all characters onto the stack
  const stack = new Stack();
  for (let char of str) {
    stack.push(char);
  }

  // popping all characters from the stack
  let reversed = "";
  while (stack.peek() !== null) {
    reversed += stack.pop();
  }
  return reversed;
}

// Example usage
console.log(reverseString("hello")); // "olleh"
console.log(reverseString("world")); // "dlrow"
```

## Activity 3: Queue

**Task 5:** Implement a _Queue_ class with methods _enqueue_ (add element), _dequeue_ (remove element), and _front_ (view the first element).

```js
class Queue {
  constructor() {
    this.items = [];
  }

  enqueue(value) {
    this.items.push(value);
  }

  dequeue() {
    if (this.items.length === 0) return null;
    return this.items.shift();
  }

  front() {
    if (this.items.length === 0) return null;
    return this.items[0];
  }
}

// Example usage
const queue = new Queue();
queue.enqueue(1);
queue.enqueue(2);
queue.enqueue(3);
console.log(queue.front()); // 1
console.log(queue.dequeue()); // 1
console.log(queue.dequeue()); // 2
console.log(queue.dequeue()); // 3
console.log(queue.dequeue()); // null
```

**Task 6:** Use the _Queue_ class to simulate a simple printer queue where print jobs are added to the queue and processed in order.

```js
class PrinterQueue {
  constructor() {
    this.queue = new Queue();
  }

  addPrintJob(job) {
    this.queue.enqueue(job);
    console.log(`Print job added: ${job}`);
  }

  processPrintJobs() {
    while (this.queue.front() !== null) {
      const job = this.queue.dequeue();
      console.log(`Processing print job: ${job}`);
    }
  }
}

// Example usage
const printer = new PrinterQueue();
printer.addPrintJob("Document1");
printer.addPrintJob("Document2");
printer.addPrintJob("Document3");
printer.processPrintJobs();
// Output:
// Print job added: Document1
// Print job added: Document2
// Print job added: Document3
// Processing print job: Document1
// Processing print job: Document2
// Processing print job: Document3
```

## Activity 4: Binary Tree

**Task 7:** Implement a _TreeNode_ class to represent a node in a binary tree with properties _value_, _left_, and _right_.

```js
class TreeNode {
  constructor(value) {
    this.value = value;
    this.left = null;
    this.right = null;
  }
}
```

**Task 8:** Implement a _BinaryTree_ class with methods for inserting values and performing in-order traversal to display nodes.

```js
class BinaryTree {
  constructor() {
    this.root = null;
  }

  // Method 1: to insert values
  insert(value) {
    const newNode = new TreeNode(value);
    if (!this.root) {
      // When root is null, then newNode join to the root node of BT
      this.root = newNode;
      return;
    }

    let current = this.root;
    while (true) {
      if (value < current.value) {
        if (!current.left) {
          // Join the newNode to left of the current root node
          current.left = newNode;
          return;
        }
        // Update the current root node via left node
        current = current.left;
      } else {
        if (!current.right) {
          // Join the newNode to right of the current root node
          current.right = newNode;
          return;
        }
        // Update the current root node via right node
        current = current.right;
      }
    }
  }

  // Method 2: to perform in-order traversal to display nodes (LNR)
  inOrderTraversal(node = this.root) {
    if (node !== null) {
      // L
      this.inOrderTraversal(node.left);
      // N
      console.log(node.value);
      // R
      this.inOrderTraversal(node.right);
    }
  }
}

// Example usage
const tree = new BinaryTree();
tree.insert(5);
tree.insert(3);
tree.insert(7);
tree.insert(2);
tree.insert(4);
tree.insert(6);
tree.insert(8);
tree.inOrderTraversal();
// Output: 2 3 4 5 6 7 8
```

## Activity 5: Graph (Optional)

**Task 9:** Implement a _Graph_ class with methods to add vertices, add edges, and perform a breadth-first search (BFS).

```js
class Graph {
  constructor() {
    this.adjList = new Map();
  }

  // Method 1: to add vertices
  addVertex(vertex) {
    if (!this.adjList.has(vertex)) {
      this.adjList.set(vertex, []);
    }
  }

  // Method 2: to add the edges
  addEdge(vertex1, vertex2) {
    if (this.adjList.has(vertex1)) {
      this.adjList.get(vertex1).push(vertex2);
    }
    if (this.adjList.has(vertex2)) {
      this.adjList.get(vertex2).push(vertex1);
    }
  }

  // Method 3: to perform a breadth-first search (BFS)
  bfs(start) {
    const visited = new Set();
    const queue = [start];
    while (queue.length > 0) {
      const vertex = queue.shift();
      if (!visited.has(vertex)) {
        console.log(vertex);
        visited.add(vertex);
        const neighbors = this.adjList.get(vertex);
        for (const neighbor of neighbors) {
          if (!visited.has(neighbor)) {
            queue.push(neighbor);
          }
        }
      }
    }
  }
}

// Example usage
const graph = new Graph();
graph.addVertex("A");
graph.addVertex("B");
graph.addVertex("C");
graph.addVertex("D");
graph.addEdge("A", "B");
graph.addEdge("A", "C");
graph.addEdge("B", "D");
graph.addEdge("C", "D");
graph.bfs("A");
// Output: A B C D
```

**Task 10:** Use the _Graph_ class to represent a simple network and perform BFS to find the shortest path between two nodes.

```js
class SimpleNetwork {
  constructor() {
    this.graph = new Graph();
  }

  addNode(node) {
    this.graph.addVertex(node);
  }

  addConnection(node1, node2) {
    this.graph.addEdge(node1, node2);
  }

  findShortestPath(start, end) {
    const visited = new Set();
    const queue = [[start, [start]]];
    while (queue.length > 0) {
      const [vertex, path] = queue.shift();
      if (vertex === end) return path;
      if (!visited.has(vertex)) {
        visited.add(vertex);
        const neighbors = this.graph.adjList.get(vertex);
        for (const neighbor of neighbors) {
          queue.push([neighbor, [...path, neighbor]]);
        }
      }
    }
    return null;
  }
}

// Example usage
const network = new SimpleNetwork();
network.addNode("A");
network.addNode("B");
network.addNode("C");
network.addNode("D");
network.addConnection("A", "B");
network.addConnection("A", "C");
network.addConnection("B", "D");
network.addConnection("C", "D");
console.log(network.findShortestPath("A", "D")); // Output: ['A', 'B', 'D']
```

## Feature Request

1. **Linked List Script:** Write a script that implements a linked list with methods to add, remove, and display nodes.
2. **Stack Script:** Create a script that implements a stack and uses it to reverse a string.
3. **Queue Script:** Write a script that implements a queue and simulates a printer queue.
4. **Binary Tree Script:** Create a script that implements a binary tree with insertion and in-order traversal methods.
5. **Graph Script:** Write a script that implements a graph and performs breadth-first search (optional).

## Achievements

By the end of these activities, students will:

- Implement and use linked lists for dynamic data storage.
- Use stacks for `LIFO (Last-In-First-Out)` operations and reverse data.
- Use queues for `FIFO (First-In-First-Out)` operations and simulate real-world scenarios.
- Implement binary trees for hierarchical data storage and traversal.
- Understand and use graphs for network representations and pathfinding (optional).
