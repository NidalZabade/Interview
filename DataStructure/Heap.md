# Heap

## Table of Contents

- [Heap](#heap)
  - [Table of Contents](#table-of-contents)
  - [What is Heap?](#what-is-heap)
  - [Heap Implementation](#heap-implementation)
  - [Heap Types](#heap-types)
    - [Max Heap](#max-heap)
    - [Min Heap](#min-heap)
  - [Heapify](#heapify)
    - [Max Heapify](#max-heapify)
      - [Max Heapify Implementation](#max-heapify-implementation)
    - [Min Heapify](#min-heapify)
      - [Min Heapify Implementation](#min-heapify-implementation)
  - [Heap Operations](#heap-operations)
  - [Insert](#insert)
  - [Delete](#delete)

## What is Heap?

A heap is a data structure that stores a collection of elements. A heap is a complete binary tree. A complete binary tree is a binary tree in which every level, except possibly the last, is completely filled, and all nodes are as far left as possible.

## Heap Implementation

A heap can be implemented using an array in c.

```c
int heap[10];
```

## Heap Types

There are two types of heaps:

* Max Heap
* Min Heap
  
### Max Heap

A max heap is a heap in which the value of each node is greater than or equal to the value of its parent, with the maximum value in the root node.

### Min Heap

A min heap is a heap in which the value of each node is less than or equal to the value of its parent, with the minimum value in the root node.

## Heapify

To maintain the heap property, the heap must be heapified. Heapify is the process of converting a binary tree into a heap.

### Max Heapify

To max heapify a binary tree, the following steps are performed:

* If the node is a leaf node, stop.
* If the node is not a leaf node, compare the node with its children.
* If the node is greater than or equal to its children, stop.
* If the node is less than its children, swap the node with the largest child.

#### Max Heapify Implementation

```c
void maxHeapify(int index) {
    int leftChildIndex = 2 * index + 1;
    int rightChildIndex = 2 * index + 2;
    int largestIndex = index;
    if (leftChildIndex < size && heap[leftChildIndex] > heap[largestIndex]) {
        largestIndex = leftChildIndex;
    }
    if (rightChildIndex < size && heap[rightChildIndex] > heap[largestIndex]) {
        largestIndex = rightChildIndex;
    }
    if (largestIndex != index) {
        int temp = heap[index];
        heap[index] = heap[largestIndex];
        heap[largestIndex] = temp;
        maxHeapify(largestIndex);
    }
}
```

### Min Heapify

To min heapify a binary tree, the following steps are performed:

* If the node is a leaf node, stop.
* If the node is not a leaf node, compare the node with its children.
* If the node is less than or equal to its children, stop.
* If the node is greater than its children, swap the node with the smallest child.

#### Min Heapify Implementation

```c
void minHeapify(int index) {
    int leftChildIndex = 2 * index + 1;
    int rightChildIndex = 2 * index + 2;
    int smallestIndex = index;
    if (leftChildIndex < size && heap[leftChildIndex] < heap[smallestIndex]) {
        smallestIndex = leftChildIndex;
    }
    if (rightChildIndex < size && heap[rightChildIndex] < heap[smallestIndex]) {
        smallestIndex = rightChildIndex;
    }
    if (smallestIndex != index) {
        int temp = heap[index];
        heap[index] = heap[smallestIndex];
        heap[smallestIndex] = temp;
        minHeapify(smallestIndex);
    }
}
```

## Heap Operations

A heap supports the following operations:

* Insert
* Delete    

## Insert

To insert an element into a heap, the element is added to the end of the heap. Then, the heap is heapified `Either Max or Min Heapify`.

```c
void insert(int value) {
    heap[size] = value;
    size++;
    heapify();
}
```

## Delete

To delete an element from a heap, the first element is removed from the heap. Then, the heap is heapified `Either Max or Min Heapify`.

```c
int delete() {
    int value = heap[0];
    heap[0] = heap[size - 1];
    size--;
    heapify();
    return value;
}
```

[**Go Back**](Overview.md)