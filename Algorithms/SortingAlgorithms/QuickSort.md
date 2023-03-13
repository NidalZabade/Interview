# Quick Sort

## What is Quick Sort?

Quick Sort is a sorting algorithm that sorts the elements by partitioning the array into two sub-arrays and then sorting the sub-arrays recursively.

## Quick Sort Algorithm

The Quick Sort algorithm is as follows:

1. Select a pivot element from the array, usually the last element.
2. Partition the other elements into two sub-arrays, according to the pivot element such that all the elements less than the pivot are in one sub-array and all the elements greater than the pivot are in the other sub-array.
3. Sort the two sub-arrays recursively.
4. Combine the sorted sub-arrays to form the sorted array.
5. Repeat steps 1 to 4 until the list is sorted.

## Quick Sort Implementation

The Quick Sort implementation in C is as follows:

```c
void quickSort(int array[], int low, int high) {
    if (low < high) {
        // Select pivot position and put all the elements smaller 
        // than pivot on left and greater than pivot on right
        int pi = partition(array, low, high);

        // Sort the elements on the left of pivot
        quickSort(array, low, pi - 1);

        // Sort the elements on the right of pivot
        quickSort(array, pi + 1, high);
    }
}

int partition(int array[], int low, int high) {
    // Select the pivot element
    int pivot = array[high];
    // pointer for greater element
    int i = (low - 1);

    for (int j = low; j < high; j++) {
        if (array[j] < pivot) {
            i++;

            // swap arr[i] and arr[j]
            int temp = array[i];
            array[i] = array[j];
            array[j] = temp;
        }
    }

    // swap arr[i+1] and arr[high] (or pivot)
    int temp = array[i + 1];
    array[i + 1] = array[high];
    array[high] = temp;

    return (i + 1);
}
```

## Quick Sort Complexity

The time complexity of Quick Sort is O(n log n).

[**Go Back To Sorting Algorithms**](Overview.md)
