# Bubble Sort

## What is Bubble Sort?

Bubble Sort is a sorting algorithm that compares adjacent elements and swaps them if they are not in the correct order. The algorithm repeats this process until all the elements are in the correct order.

## Bubble Sort Algorithm

The Bubble Sort algorithm is as follows:

1. Compare the first element with the second element.
2. If the first element is greater than the second element, swap them.
3. Compare the second element with the third element.
4. If the second element is greater than the third element, swap them.
5. Repeat steps 1 to 4 until the last element.

## Bubble Sort Implementation

A Bubble Sort algorithm can be implemented using a class in C.

```c
void bubbleSort(int array[], int size) {
    for (int i = 0; i < size - 1; i++) {
        for (int j = 0; j < size - i - 1; j++) {
            if (array[j] > array[j + 1]) {
                int temp = array[j];
                array[j] = array[j + 1];
                array[j + 1] = temp;
            }
        }
    }
}
```

## Bubble Sort Complexity

The time complexity of Bubble Sort is O(n^2).

[**Go Back To Sorting Algorithms**](README.md)
