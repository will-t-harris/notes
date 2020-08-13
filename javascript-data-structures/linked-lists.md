# Linked Lists

- Series of linked nodes where each node points to the next node in the list. The pointer is the link.
- Each node has a value and a pointer reference to the next node.
- Doubly linked lists have two pointers for each node, one to the next node and one to the previous node.
- Linked lists are LIFO "last in first out." Nodes are added to and deleted from the same end
- Searching for a node in a linked list requires iterating through the list until the node is found. Worst case, this is O(n)

## Downsides of Linked Lists

- To remove a node from a singly-linked list requires iterating through the list and keeping track of the previous node at each iteration until the desired node is found.

## Linked List Methods

- `push(item)`
	- Add an item to the list
- `pop()`
	- Remove an item from the list
- `get(index)`
	- Return an element at a given index, without removing it from the list
- `delete(index)`
	- Delete an element at a given index
- `isEmpty()`
	- Convenience method to check whether the list is empty

## Class-based Singly-Linked List

1. Create a class that represents a Node in the list. Nodes will each have a `value` and a pointer reference to the next node (`next`).
	- **We will assume that the `Node` class is in the same scope as the `LinkedList` class below at all times**

```js
class Node {
	constructor(value) {
		this.value = value;
		this.next = null;
	}
}
```

2. Create a class that represents our linked list. The class keeps track of three values:
	 - `head`: reference to the first item in the linked list
	 - `tail`: reference to the last item in the linked list
	 - `length`: the number of nodes in the list

```js
class LinkedList {
	constructor() {
		this.head = null;
		this.tail = null;
		this.length = 0;
	}
}
```

3. Create the `isEmpty()` convenience method on the `LinkedList` class which returns `true` if there are no `Node`s in the list

```js
class LinkedList {
	constructor() {
		this.head = null;
		this.tail = null;
		this.length = 0;
	}
	isEmpty() {
		return this.length === 0;
	}
}
```

4. Create the `push` method on the `LinkedList` class which deals with adding new items to the list.
-  If the list is empty, set the `head` and `tail` to the new `Node` and increment the `length` property by one.

```js
class LinkedList {
	constructor() {
		this.head = null;
		this.tail = null;
		this.length = 0;
	}
	isEmpty() {
		return this.length === 0;
	}
	push(value) {
		const newNode = new Node(value);
	
		if (this.isEmpty()) {
			this.head = newNode;
			this.tail = newNode;
		}
		
		this.length++;
	}
}
```
-  If the list isn't empty, set the current tail's `next` pointer to the new `Node`,  set the list's `tail` pointer to the new `Node`, and increment the list's `length` property by one.

```js
class LinkedList {
	constructor() {
		this.head = null;
		this.tail = null;
		this.length = 0;
	}
	isEmpty() {
		return this.length === 0;
	}
	push(value) {
		const newNode = new Node(value);
		
		if (this.isEmpty()) {
			this.head = newNode;
			this.tail = newNode;
		}
		
		if (!this.isEmpty()) {
			this.tail.next = newNode;
			this.tail = newNode;
		}
		
		this.length++;
	}
}
```