# Merge Sort

## What is Merge Sort?

Merge Sort is a sorting algorithm that sorts the elements by dividing the array into two halves, sorting the two halves independently, and finally merging the two sorted halves.

## Merge Sort Algorithm

The Merge Sort algorithm is as follows:

1. Divide the unsorted list into n sublists, each containing one element (a list of one element is considered sorted).
2. Repeatedly merge sublists to produce new sorted sublists until there is only one sublist remaining. This will be the sorted list.

## Merge Sort Implementation

The Merge Sort implementation in C is as follows:

```c
void merge(int array[], int left, int mid, int right) {
    // We have left to mid and mid+1 to right already sorted.
    int i, j, k;
    int n1 = mid - left + 1;
    int n2 = right - mid;

    // create temp arrays
    int L[n1], R[n2];

    // Copy data to temp arrays L[] and R[]
    for (i = 0; i < n1; i++)
        L[i] = array[left + i];
    for (j = 0; j < n2; j++)
        R[j] = array[mid + 1 + j];

    // Merge the temp arrays back into array[left..right]
    i = 0; // Initial index of first subarray
    j = 0; // Initial index of second subarray
    k = left; // Initial index of merged subarray
    while (i < n1 && j < n2) {
        if (L[i] <= R[j]) {
            array[k] = L[i];
            i++;
        }
        else {
            array[k] = R[j];
            j++;
        }
        k++;
    }

    // Copy the remaining elements of L[], if there are any
    while (i < n1) {
        array[k] = L[i];
        i++;
        k++;
    }

    // Copy the remaining elements of R[], if there are any
    while (j < n2) {
        array[k] = R[j];
        j++;
        k++;
    }
}

// left is for left index and right is right index of the
// sub-array of array to be sorted

void mergeSort(int array[], int left, int right) {
    if (left < right) {
        // Same as (left+right)/2, but avoids overflow for
        // large left and right
        int mid = left + (right - left) / 2;

        // Sort first and second halves
        mergeSort(array, left, mid);
        mergeSort(array, mid + 1, right);

        merge(array, left, mid, right);
    }
}
```

## Merge Sort Complexity

The time complexity of Merge Sort is O(n log n) in all 3 cases (worst, average and best) as merge sort always divides the array into two halves and take linear time to merge two halves.

[**Go Back To Sorting Algorithms**](README.md)
