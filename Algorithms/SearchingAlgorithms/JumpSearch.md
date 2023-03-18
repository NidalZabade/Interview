# Jump Search

## What is Jump Search?

Jump Search is a searching algorithm that searches for an element in a sorted collection by jumping ahead a fixed number of steps at a time. If the element is found, the algorithm returns the index of the element. If the element is not found, the algorithm returns -1.

## Jump Search Algorithm

The Jump Search algorithm is as follows:

1. Start from the first element of the collection.
2. If the first element is the element to be searched, return the index of the first element.
3. If the first element is not the element to be searched, jump ahead a fixed number of steps.
4. Repeat steps 2 and 3 until the element is found or the end of the collection is reached.
5. If the element is not found, return -1.

## Jump Search Implementation

A Jump Search algorithm can be implemented in C as following:

```c
int jumpSearch(int array[], int size, int element) {
    int step = sqrt(size);
    int prev = 0;
    while (array[min(step, size) - 1] < element) {
        prev = step;
        step += sqrt(size);
        if (prev >= size) {
            return -1;
        }
    }
    while (array[prev] < element) {
        prev++;
        if (prev == min(step, size)) {
            return -1;
        }
    }
    if (array[prev] == element) {
        return prev;
    }
    return -1;
}
```

## Jump Search Complexity

The time complexity of Jump Search is O(sqrt(n)).

[**Go Back To Searching Algorithms**](README.md)
