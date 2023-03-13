# Selection Sort

## What is Selection Sort?

Selection sort is a sorting algorithm that selects the smallest element from an unsorted list in each iteration and places that element at the beginning of the unsorted list.

## Selection Sort Algorithm

The Selection Sort algorithm is as follows:

1. Select the smallest element from the unsorted list.
2. Swap the smallest element with the element at the beginning of the unsorted list.
3. Repeat steps 1 and 2 until the list is sorted.

## Selection Sort Implementation

The Selection Sort implementation in C is as follows:

```c
void selectionSort(int array[], int size) {
    for (int step = 0; step < size - 1; step++) {
        int min_idx = step;
        for (int i = step + 1; i < size; i++) {
            // To sort in descending order, change > to < in this line.
            // Select the minimum element in each loop.
            if (array[i] < array[min_idx])
                min_idx = i;
        }
        // put min at the correct position
        int temp = array[step];
        array[step] = array[min_idx];
        array[min_idx] = temp;
    }
}
```

## Selection Sort Complexity

The time complexity of Selection Sort is O(n^2).

[**Go Back**](Overview.md)
