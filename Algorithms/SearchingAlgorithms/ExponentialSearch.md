# Exponential Search

## What is Exponential Search?

The idea is to start with subarray size 1, compare its last element with x, then try size 2, then 4 and so on until last element of a subarray is not greater. Once we find an index i (after repeated doubling of i), we know that the element must be present between i/2 and i (Why i/2? because we could not find a greater value in previous iteration)

## Exponential Search Algorithm

The Exponential Search algorithm is as follows:

1. Find the range where the element is present.
2. Do Binary Search in the found range.
3. If the element is not found, return -1.
4. If the element is found, return the index of the element.
5. Repeat steps 1, 2, 3, and 4 until the element is found.

## Exponential Search Implementation

An Exponential Search algorithm can be implemented in C as following:

```c
int binarySearch(int array[], int low, int high, int element) {
    if (high >= low) {
        int mid = low + (high - low) / 2;
        if (array[mid] == element) {
            return mid;
        } else if (array[mid] > element) {
            return binarySearch(array, low, mid - 1, element);
        } else {
            return binarySearch(array, mid + 1, high, element);
        }
    }
    return -1;
}

int exponentialSearch(int array[], int size, int element) {
    if (array[0] == element) {
        return 0;
    }
    int i = 1;
    while (i < size && array[i] <= element) {
        i *= 2;
    }
    return binarySearch(array, i / 2, min(i, size - 1), element);
}

```

## Exponential Search Complexity

The time complexity of Exponential Search is O(log(n)).

[**Go Back To Searching Algorithms**](README.md)
