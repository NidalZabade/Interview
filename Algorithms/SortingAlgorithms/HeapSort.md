# Heap Sort

## What is Heap Sort?

Heap Sort is a sorting algorithm that sorts the elements by creating a [**heap data structure**](../../DataStructure/Heap.md) and repeatedly extracting the maximum element from the heap.

## Heap Sort Algorithm

The Heap Sort algorithm is as follows:

1. Create a [**heap data structure**](../../DataStructure/Heap.md) from the elements of the array.
2. Extract the maximum element from the heap and place it at the end of the array.
3. Repeat step 2 until the heap is empty.

## Heap Sort Implementation

The Heap Sort implementation in C is as follows:

```c
void heapSort(int array[], int size) {
    // Build heap (rearrange array)
    for (int i = size / 2 - 1; i >= 0; i--)
        heapify(array, size, i);

    // One by one extract an element from heap
    for (int i = size - 1; i >= 0; i--) {
        // Move current root to end
        int temp = array[0];
        array[0] = array[i];
        array[i] = temp;

        // call max heapify on the reduced heap
        heapify(array, i, 0);
    }
}

// To heapify a subtree rooted with node i which is

// an index in arr[]. n is size of heap

void heapify(int array[], int size, int i) {
    int largest = i; // Initialize largest as root
    int left = 2 * i + 1; // left = 2*i + 1
    int right = 2 * i + 2; // right = 2*i + 2

    // If left child is larger than root
    if (left < size && array[left] > array[largest])
        largest = left;

    // If right child is larger than largest so far
    if (right < size && array[right] > array[largest])
        largest = right;

    // If largest is not root
    if (largest != i) {
        int swap = array[i];
        array[i] = array[largest];
        array[largest] = swap;

        // Recursively heapify the affected sub-tree
        heapify(array, size, largest);
    }
}
```

## Heap Sort Complexity

The time complexity of Heap Sort is O(n log n).

[**Go Back To Sorting Algorithms**](Overview.md)
