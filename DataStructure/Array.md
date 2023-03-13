# Array

## Table of Contents

- [Array](#array)
  - [Table of Contents](#table-of-contents)
  - [What is an Array?](#what-is-an-array)
  - [Types of Arrays](#types-of-arrays)
    - [Static Array](#static-array)
      - [Static Array Implementation](#static-array-implementation)
    - [Dynamic Array](#dynamic-array)
      - [Dynamic Array Implementation](#dynamic-array-implementation)
  - [Array Operations](#array-operations)
    - [Read](#read)
    - [Write](#write)
    - [Search](#search)
  - [Array Time Complexity](#array-time-complexity)
  - [Array vs Linked List](#array-vs-linked-list)

## What is an Array?

An array is a data structure that stores a collection of elements. Each element is identified by an index. The index is a number that represents the position of the element in the array. The first element in the array has an index of 0, the second element has an index of 1, and so on.

## Types of Arrays

There are two types of arrays: static and dynamic.

### Static Array

A static array is an array that has a fixed size. Once an array is created, its size cannot be changed.

#### Static Array Implementation

A static array can be implemented using an array in C or C++.

```c
int array[10];
```

### Dynamic Array

A dynamic array is an array that can grow or shrink in size. The size of a dynamic array is not fixed.

#### Dynamic Array Implementation

A dynamic array can be implemented using a vector in C++.

```c++
vector<int> array;
```

## Array Operations

There are two types of operations that can be performed on an array: read and write.

### Read

To read an element from an array, you need to provide the index of the element. The element is then returned.

```c
int element = array[index];
```

### Write

To write an element to an array, you need to provide the index of the element and the value of the element. The element is then written to the array.

```c
array[index] = element;
```

For example, to write 1, 2, and 3 to an array, you need to call the write function three times.

```c
array[0] = 1;
array[1] = 2;
array[2] = 3;
```

### Search

To search an element from an array, you need to provide the value of the element. The element is then searched in the array. If the element is found, the index of the element is returned. If the element is not found, -1 is returned.

```c
int index = -1;
for (int i = 0; i < array.size(); i++) {
    if (array[i] == element) {
        index = i;
        break;
    }
}
```

## Array Time Complexity

| Operation | Time Complexity |
| --------- | --------------- |
| Read      | O(1)            |
| Write     | O(1)            |
| Search    | O(n)            |
| Delete    | O(n)            |

## Array vs [Linked List](Linked-List.md)

| Operation | Array | Linked List |
| --------- | ----- | ----------- |
| Read      | O(1)  | O(n)        |
| Write     | O(1)  | O(n)        |
| Search    | O(n)  | O(n)        |
| Delete    | O(n)  | O(n)        |

[**Go Back To Data Structure**](Overview.md)
