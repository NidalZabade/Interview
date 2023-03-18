# Fibonacci Search

## What is Fibonacci Search?

Fibonacci Search is a searching algorithm that searches for an element in a collection based on the Fibonacci numbers. If the element is found, the algorithm returns the index of the element. If the element is not found, the algorithm returns -1.

## Fibonacci Search Algorithm

The Fibonacci Search algorithm is as follows:

1. Find the smallest Fibonacci number that is greater than or equal to the size of the collection.
2. Start from the first element of the collection.
3. If the first element is the element to be searched, return the index of the first element.
4. If the first element is not the element to be searched, jump ahead a number of steps equal to the previous Fibonacci number.
5. Repeat steps 3 and 4 until the element is found or the end of the collection is reached.
6. If the element is not found, return -1.

## Fibonacci Search Implementation

A Fibonacci Search algorithm can be implemented in C as following:

```c
int fibonacciSearch(int array[], int size, int element) {
    int fibMMm2 = 0;
    int fibMMm1 = 1;
    int fibM = fibMMm2 + fibMMm1;
    while (fibM < size) {
        fibMMm2 = fibMMm1;
        fibMMm1 = fibM;
        fibM = fibMMm2 + fibMMm1;
    }
    int offset = -1;
    while (fibM > 1) {
        int i = min(offset + fibMMm2, size - 1);
        if (array[i] < element) {
            fibM = fibMMm1;
            fibMMm1 = fibMMm2;
            fibMMm2 = fibM - fibMMm1;
            offset = i;
        } else if (array[i] > element) {
            fibM = fibMMm2;
            fibMMm1 = fibMMm1 - fibMMm2;
            fibMMm2 = fibM - fibMMm1;
        } else {
            return i;
        }
    }
    if (fibMMm1 && array[offset + 1] == element) {
        return offset + 1;
    }
    return -1;
}
```

## Fibonacci Search Complexity

The time complexity of Fibonacci Search is O(log n).

[**Go Back To Searching Algorithms**](README.md)
