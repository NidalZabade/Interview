# Sentinel Linear Search

## What is Sentinel Linear Search?

Sentinel Linear Search is a searching algorithm that searches for an element in a collection by comparing the element with each element in the collection. If the element is found, the algorithm returns the index of the element. If the element is not found, the algorithm returns -1.

## Sentinel Linear Search Algorithm

The Sentinel Linear Search algorithm is as follows:

1. Start from the first element of the collection.
2. If the first element is the element to be searched, return the index of the first element.
3. If the first element is not the element to be searched, go to the next element.
4. Repeat steps 2 and 3 until the last element.

## Sentinel Linear Search Implementation

A Sentinel Linear Search algorithm can be implemented in C as following:

```c
int sentinelLinearSearch(int array[], int size, int element) {
    int last = array[size - 1];
    array[size - 1] = element;
    int i = 0;
    while (array[i] != element) {
        i++;
    }
    array[size - 1] = last;
    if ((i < size - 1) || (element == array[size - 1])) {
        return i;
    } else {
        return -1;
    }
}
```

## Sentinel Linear Search Complexity

The time complexity of Sentinel Linear Search is O(n).

[**Go Back To Searching Algorithms**](README.md)
