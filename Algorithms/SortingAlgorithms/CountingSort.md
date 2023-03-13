# Counting Sort

## What is Counting Sort?

Counting Sort is a sorting algorithm that sorts the elements by counting the number of occurrences of each unique element in the array. The elements are sorted based on the count of each element.

## Counting Sort Algorithm

The Counting Sort algorithm is as follows:

1. Find the minimum and maximum values in the array.
2. Initialize an array of length (max - min + 1) with all elements 0.
3. Store the count of each element at their respective index in the count array.
4. Store the cumulative sum of the elements of the count array.
5. Find the index of each element of the original array in the count array.
6. Place the elements in the output array.
7. Copy the sorted elements into the original array.
8. Repeat steps 1 to 7 until the list is sorted.

## Counting Sort Implementation

The Counting Sort implementation in C is as follows:

```c
void countingSort(int array[], int size) {
    int output[size];
    int max = array[0];
    int min = array[0];

    // Find the largest element of the array
    for (int i = 1; i < size; i++) {
        if (array[i] > max)
            max = array[i];
    }

    // Find the smallest element of the array
    for (int i = 1; i < size; i++) {
        if (array[i] < min)
            min = array[i];
    }

    int range = max - min + 1;
    int count[range];
    memset(count, 0, sizeof(count));

    // Store the count of each element
    for (int i = 0; i < size; i++) {
        count[array[i] - min]++;
    }

    // Store the cumulative count of each array
    for (int i = 1; i < range; i++) {
        count[i] += count[i - 1];
    }

    // Find the index of each element of the original array in count array, and
    // place the elements in output array
    for (int i = size - 1; i >= 0; i--) {
        output[count[array[i] - min] - 1] = array[i];
        count[array[i] - min]--;
    }

    // Copy the sorted elements into original array
    for (int i = 0; i < size; i++) {
        array[i] = output[i];
    }
}
```

## Counting Sort Complexity

The time complexity of Counting Sort is O(n+k) where n is the number of elements in input array and k is the range of input.

[**Go Back to Sorting Algorithms**](Overview.md)
