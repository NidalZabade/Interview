# Ternary Search

## What is Ternary Search?

Ternary Search  decrease (by constant) and conquer algorithm that can be used to find an element in an array. It is similar to binary search where we divide the array into two parts but in this algorithm, we divide the given array into three parts and determine which has the key (searched element).

## Ternary Search Algorithm

The algorithm is as follows:

1. Divide the array into three parts.
2. Determine which has the key (searched element).
3. Repeat steps 1 and 2 until the element is found.
4. If the element is not found, return -1.

## Ternary Search Implementation

A Ternary Search algorithm can be implemented in C as following:

```c
int ternarySearch(int array[], int size, int element) {
    int left = 0;
    int right = size - 1;
    while (left <= right) {
        int middle1 = left + (right - left) / 3;
        int middle2 = right - (right - left) / 3;
        if (array[middle1] == element) {
            return middle1;
        } else if (array[middle2] == element) {
            return middle2;
        } else if (array[middle1] > element) {
            right = middle1 - 1;
        } else if (array[middle2] < element) {
            left = middle2 + 1;
        } else {
            left = middle1 + 1;
            right = middle2 - 1;
        }
    }
    return -1;
}
```

## Ternary Search Complexity

The time complexity of Ternary Search is O(log n base 3).

[**Go Back To Searching Algorithms**](README.md)
