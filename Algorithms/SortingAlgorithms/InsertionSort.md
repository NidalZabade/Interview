
# Insertion Sort

## What is Insertion Sort?

Insertion Sort is a sorting algorithm that inserts each element into its correct position in the sorted part of the array.

## Insertion Sort Algorithm

The Insertion Sort algorithm is as follows:

1. Insert the element into the sorted part of the array.

## Insertion Sort Implementation

The Insertion Sort implementation in C is as follows:

```c
void insertionSort(int array[], int size) {
    for (int i = 1; i < size; i++) {
        int key = array[i];
        int j = i - 1;
        while (j >= 0 && array[j] > key) { // Move elements of array[0..i-1], that are greater than key, to one position ahead of their current position
            array[j + 1] = array[j];
            j--;
        }
        array[j + 1] = key;
    }
}
```

## Insertion Sort Complexity

The time complexity of Insertion Sort is O(n^2).

[**Go Back**](Overview.md)
