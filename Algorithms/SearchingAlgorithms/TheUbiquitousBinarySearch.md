# The Ubiquitous Binary Search

## What is The Ubiquitous Binary Search?

The Ubiquitous Binary Search is a binary search algorithm that is used to find the index of an element in a sorted array. The algorithm is also known as the binary search algorithm.

## The Ubiquitous Binary Search Algorithm

The Ubiquitous Binary Search algorithm is as follows:

1. Set the left index to 0 and the right index to the length of the array minus 1.
2. If the left index is greater than the right index, return -1.
3. Set the middle index to the left index plus the right index divided by 2.
4. If the element at the middle index is the element to be searched, return the middle index.
5. If the element at the middle index is greater than the element to be searched, set the right index to the middle index minus 1.
6. If the element at the middle index is less than the element to be searched, set the left index to the middle index plus 1.
7. Repeat steps 2 to 6 until the element is found.
8. If the element is not found, return -1.

## The Ubiquitous Binary Search Implementation

A The Ubiquitous Binary Search algorithm can be implemented in C as following:

```c
int binarySearch(int array[], int size, int element) {
    int left = 0;
    int right = size - 1;
    while (left <= right) {
        int middle = (left + right) / 2;
        if (array[middle] == element) {
            return middle;
        } else if (array[middle] < element) {
            left = middle + 1;
        } else {
            right = middle - 1;
        }
    }
    return -1;
}
```

## The Ubiquitous Binary Search Complexity

The time complexity of Ubiquitous Binary Search is O(log n).

[**Go Back To Searching Algorithms**](README.md)
