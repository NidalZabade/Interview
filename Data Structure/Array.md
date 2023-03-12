# Array

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