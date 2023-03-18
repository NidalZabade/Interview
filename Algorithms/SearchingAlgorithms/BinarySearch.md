# Binary Search

## What is Binary Search?

Binary Search is a searching algorithm that searches for an element in a collection by comparing the element with the middle element of the collection. If the element is found, the algorithm returns the index of the element. If the element is not found, the algorithm searches for the element in the left or right half of the collection depending on the value of the middle element.

## Binary Search Algorithm

The Binary Search algorithm is as follows:

1. Start from the middle element of the collection.
2. If the middle element is the element to be searched, return the index of the middle element.
3. If the middle element is not the element to be searched, go to the left or right half of the collection depending on the value of the middle element.
4. Repeat steps 1, 2, and 3 until the element is found.
5. If the element is not found, return -1.

## Binary Search Implementation

A Binary Search algorithm can be implemented in C as following:

```c
int binarySearch(int array[], int size, int element) {
    int low = 0;
    int high = size - 1;
    while (low <= high) {
        int mid = (low + high) / 2;
        if (array[mid] == element) {
            return mid;
        } else if (array[mid] < element) {
            low = mid + 1;
        } else {
            high = mid - 1;
        }
    }
    return -1;
}
```

## Binary Search Complexity

The time complexity of Binary Search is O(log n).

[**Go Back To Searching Algorithms**](README.md)