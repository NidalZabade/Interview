# Linear Search

## What is Linear Search?

Linear Search is a searching algorithm that searches for an element in a collection by comparing the element with each element in the collection. If the element is found, the algorithm returns the index of the element. If the element is not found, the algorithm returns -1.

## Linear Search Algorithm

The Linear Search algorithm is as follows:

1. Start from the first element of the collection.
2. If the first element is the element to be searched, return the index of the first element.
3. If the first element is not the element to be searched, go to the next element.
4. Repeat steps 2 and 3 until the last element.

## Linear Search Implementation

A Linear Search algorithm can be implemented in C as following:

```c
int linearSearch(int array[], int size, int element) {
    for (int i = 0; i < size; i++) {
        if (array[i] == element) {
            return i;
        }
    }
    return -1;
}
```

## Linear Search Complexity

The time complexity of Linear Search is O(n)

[**Go Back To Searching Algorithms**](README.md)
