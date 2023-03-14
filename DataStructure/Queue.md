# Queue

## What is a Queue?

A queue is a data structure that stores a collection of elements. The elements are added and removed from the queue in a particular order. The order is called First In First Out (FIFO). The first element added to the queue is the first element removed from the queue.

## Queue Implementation

A queue can be implemented using a class in C.

```c
struct Node {
    int data;
    struct Node *next;
};

struct Node *front = NULL;

struct Node *rear = NULL;

struct Node *createNode(int data) {
    struct Node *node = (struct Node *)malloc(sizeof(struct Node));
    node->data = data;
    node->next = NULL;
    return node;
}
```

## Queue Operations

There are two types of operations that can be performed on a queue: enqueue and dequeue.

### Enqueue

To enqueue an element to a queue, you need to provide the value of the element. The element is then added to the end of the queue.

```c
void enqueue(int data) {
    struct Node *node = createNode(data);
    if (front == NULL) {
        front = node;
        rear = node;
    } else {
        rear->next = node;
        rear = node;
    }
}
```

For example, to enqueue 1, 2, and 3 to a queue, you need to call the enqueue function three times.

```c
enqueue(1);
enqueue(2);
enqueue(3);
```

### Dequeue

To dequeue an element from a queue, you need to call the dequeue function. The element at the front of the queue is removed.

```c
int dequeue() {
    if (front == NULL) {
        printf("Queue is empty");
        return -1;
    } else {
        struct Node *temp = front;
        int data = temp->data;
        front = front->next;
        free(temp);
        return data;
    }
}
```

For example, to dequeue and print 1, 2, and 3 from a queue, you need to call the dequeue function three times.

```c
printf("%d ", dequeue());
printf("%d ", dequeue());
printf("%d ", dequeue());
```
The output of the above code is:

```c
1 2 3
```
[**Go Back To Data Structure**](README.md)