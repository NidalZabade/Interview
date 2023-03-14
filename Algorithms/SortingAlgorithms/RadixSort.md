# Radix Sort

## What is Radix Sort?

Radix sort is a sorting algorithm that sorts the elements by grouping the individual digits of the same place value. The elements are first sorted according to the least significant digit (LSD), then moving to more significant digits.

## Radix Sort Algorithm

The Radix Sort algorithm is as follows:

1. Find the maximum number in the array.
2. Find the number of digits in the maximum number.
3. Sort the elements according to each digit, starting from the least significant digit to the most significant digit.
4. Repeat steps 1 to 3 until the list is sorted.

## Radix Sort Implementation

The Radix Sort implementation in C is as follows:

```c
void radixSort(int array[], int size) {
    // Find the maximum number to know number of digits
    int max = getMax(array, size);

    // Do counting sort for every digit. Note that instead
    // of passing digit number, exp is passed. exp is 10^i
    // where i is current digit number
    for (int exp = 1; max / exp > 0; exp *= 10)
        countSort(array, size, exp);
}

// A utility function to get maximum value in array[]
int getMax(int array[], int size) {
    int max = array[0];
    for (int i = 1; i < size; i++)
        if (array[i] > max)
            max = array[i];
    return max;
}

// A function to do counting sort of array[] according to
// the digit represented by exp.

void countSort(int array[], int size, int exp) {
    int output[size]; // output array
    int i, count[10] = {0};

    // Store count of occurrences in count[]
    for (i = 0; i < size; i++)
        count[(array[i] / exp) % 10]++;

    // Change count[i] so that count[i] now contains actual
    // position of this digit in output[]
    for (i = 1; i < 10; i++)
        count[i] += count[i - 1];

    // Build the output array
    for (i = size - 1; i >= 0; i--) {
        output[count[(array[i] / exp) % 10] - 1] = array[i];
        count[(array[i] / exp) % 10]--;
    }

    // Copy the output array to array[], so that array[] now
    // contains sorted numbers according to current digit
    for (i = 0; i < size; i++)
        array[i] = output[i];
}
```

## Radix Sort Complexity

The time complexity of Radix Sort is O(d(n+b)) where d is the number of digits, n is the number of elements in the array and b is the base for representing numbers.

[**Go Back To Sorting Algorithms**](README.md)
