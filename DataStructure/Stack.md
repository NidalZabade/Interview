# Stack

## What is Stack?

A stack is a data structure that stores a collection of elements. The elements are added and removed from the stack in a particular order. The order is called Last In First Out (LIFO). The last element added to the stack is the first element removed from the stack.

## Stack Implementation

A stack can be implemented using a class in C.

```c
struct Node {
    int data;
    struct Node *next;
};

struct Node *top = NULL;

struct Node *createNode(int data) {
    struct Node *node = (struct Node *)malloc(sizeof(struct Node));
    node->data = data;
    node->next = NULL;
    return node;
}


```

## Stack Operations

There are two types of operations that can be performed on a stack: push and pop.

### Push

To push an element to a stack, you need to provide the value of the element. The element is then added to the top of the stack.

```c
void push(int data) {
    struct Node *node = createNode(data);
    if (top == NULL) {
        top = node;
    } else {
        node->next = top;
        top = node;
    }
}
```
For example, to push 1, 2, and 3 to a stack, you need to call the push function three times.
```c 
push(1);
push(2);
push(3);
```

### Pop

To pop an element from a stack, you need to call the pop function. The element at the top of the stack is removed.

```c
int pop() {
    if (top == NULL) {
        printf("Stack is empty.\n");
        return -1;
    } else {
        struct Node *temp = top;
        top = top->next;
        int data = temp->data;
        free(temp);
        return data;
    }
}
```
For example, to pop and print 3, 2, and 1 from a stack, you need to call the pop function three times.
```c
printf("%d\n", pop());
printf("%d\n", pop());
printf("%d\n", pop());
```
The output of the above code is:
```c
3
2
1
```
[**Go Back**](Overview.md)