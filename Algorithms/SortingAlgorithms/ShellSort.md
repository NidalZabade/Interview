# Shell Sort

## What is Shell Sort?

Shell Sort is a sorting algorithm that sorts the elements by comparing elements that are far apart from each other by a gap. The algorithm compares elements that are far apart from each other and swaps them if they are not in the correct order. The algorithm repeats this process until all the elements are in the correct order.

## Shell Sort Algorithm

The Shell Sort algorithm is as follows:

1. Sort the elements by comparing elements that are far apart from each other by a gap.
2. Reduce the gap by dividing it by 2.
3. Repeat steps 1 and 2 until the gap is 1.
4. Sort the elements by comparing adjacent elements.
5. Repeat steps 1 to 4 until the elements are sorted.

## Shell Sort Implementation

The Shell Sort implementation in C is as follows:

```c
void shellSort(int array[], int size) {
    for (int gap = size / 2; gap > 0; gap /= 2) {
        for (int i = gap; i < size; i++) {
            int temp = array[i];
            int j;
            for (j = i; j >= gap && array[j - gap] > temp; j -= gap) {
                array[j] = array[j - gap];
            }
            array[j] = temp;
        }
    }
}
```

## Shell Sort Complexity

The time complexity of Shell Sort is O(n^2).

[**Go Back To Sorting Algorithms**](README.md)
