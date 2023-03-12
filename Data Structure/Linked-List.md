# Linked List

## Table of Contents

- [Linked List](#linked-list)
  - [Table of Contents](#table-of-contents)
  - [What is a Linked List?](#what-is-a-linked-list)
  - [Types of Linked Lists](#types-of-linked-lists)
    - [Singly Linked List](#singly-linked-list)
      - [Singly Linked List Implementation](#singly-linked-list-implementation)
      - [Singly Linked List Operations](#singly-linked-list-operations)
        - [Insertion](#insertion)
        - [Deletion](#deletion)
    - [Doubly Linked List](#doubly-linked-list)
      - [Doubly Linked List Implementation](#doubly-linked-list-implementation)
    - [Circular Linked List](#circular-linked-list)
      - [Circular Linked List Implementation](#circular-linked-list-implementation)
    - [Doubly Circular Linked List](#doubly-circular-linked-list)
      - [Doubly Circular Linked List Implementation](#doubly-circular-linked-list-implementation)
  - [Array vs Linked List](#array-vs-linked-list)

## What is a Linked List?

A linked list is a data structure that stores a collection of elements. Each element is called a node. Each node contains two parts: data and a link. The data part contains the value of the node. The link part contains the address of the next node.

## Types of Linked Lists

There are four types of linked lists: singly linked list, doubly linked list, circular linked list, and doubly circular linked list.

### Singly Linked List

A singly linked list is a linked list in which each node has a link to the next node.

#### Singly Linked List Implementation

A singly linked list can be implemented using a class in C.

```c
struct Node {
    int data;
    struct Node *next;
};

struct Node *head = NULL;

struct Node *createNode(int data) {
    struct Node *node = (struct Node *)malloc(sizeof(struct Node));
    node->data = data;
    node->next = NULL;
    return node;
}
```

#### Singly Linked List Operations

There are two types of operations that can be performed on a singly linked list: insertion and deletion.

##### Insertion

To insert a node to a singly linked list, you need to provide the value of the node. The node is then added to the end of the list.

```c
void insertNode(int data) {
    struct Node *node = createNode(data);
    if (head == NULL) {
        head = node;
    } else {
        struct Node *temp = head;
        while (temp->next != NULL) {
            temp = temp->next;
        }
        temp->next = node;
    }
}
```
For example, to insert 1, 2, and 3 to a singly linked list, you need to call the insertNode function three times.

```c
insertNode(1);
insertNode(2);
insertNode(3);
```

##### Deletion

To delete a node from a singly linked list, you need to provide the value of the node. The node is then removed from the list.

```c
void deleteNode(int data) {
    struct Node *temp = head;
    if (temp->data == data) {
        head = temp->next;
        free(temp);
    } else {
        while (temp->next != NULL) {
            if (temp->next->data == data) {
                struct Node *node = temp->next;
                temp->next = node->next;
                free(node);
                break;
            }
            temp = temp->next;
        }
    }
}
```

For example, to delete 2 from a singly linked list, you need to call the deleteNode function once.

```c
deleteNode(2);
```

### Doubly Linked List

A doubly linked list is a linked list in which each node has a link to the next node and the previous node.

#### Doubly Linked List Implementation

A doubly linked list can be implemented using a class in C.

```c
struct Node {
    int data;
    struct Node *prev;
    struct Node *next;
};

struct Node *head = NULL;

struct Node *createNode(int data) {
    struct Node *node = (struct Node *)malloc(sizeof(struct Node));
    node->data = data;
    node->prev = NULL;
    node->next = NULL;
    return node;
}

void insertNode(int data) {
    struct Node *node = createNode(data);
    if (head == NULL) {
        head = node;
    } else {
        struct Node *temp = head;
        while (temp->next != NULL) {
            temp = temp->next;
        }
        temp->next = node;
        node->prev = temp;
    }
}

void deleteNode(int data) {
    struct Node *temp = head;
    if (temp->data == data) {
        head = temp->next;
        head->prev = NULL;
        free(temp);
    } else {
        while (temp->next != NULL) {
            if (temp->next->data == data) {
                struct Node *node = temp->next;
                temp->next = node->next;
                if (node->next != NULL) {
                    node->next->prev = temp;
                }
                free(node);
                break;
            }
            temp = temp->next;
        }
    }
}

void printList() {
    struct Node *temp = head;
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}
```

### Circular Linked List

A circular linked list is a linked list in which the last node points to the first node.

#### Circular Linked List Implementation

A circular linked list can be implemented using a class in C.

```c
struct Node {
    int data;
    struct Node *next;
};

struct Node *head = NULL;

struct Node *createNode(int data) {
    struct Node *node = (struct Node *)malloc(sizeof(struct Node));
    node->data = data;
    node->next = NULL;
    return node;
}

void insertNode(int data) {
    struct Node *node = createNode(data);
    if (head == NULL) {
        head = node;
        node->next = head;
    } else {
        struct Node *temp = head;
        while (temp->next != head) {
            temp = temp->next;
        }
        temp->next = node;
        node->next = head;
    }
}

void deleteNode(int data) {
    struct Node *temp = head;
    if (temp->data == data) {
        head = temp->next;
        struct Node *node = head;
        while (node->next != temp) {
            node = node->next;
        }
        node->next = head;
        free(temp);
    } else {
        while (temp->next != head) {
            if (temp->next->data == data) {
                struct Node *node = temp->next;
                temp->next = node->next;
                free(node);
                break;
            }
            temp = temp->next;
        }
    }
}

void printList() {
    struct Node *temp = head;
    while (temp->next != head) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("%d ", temp->data);
    printf("\n");
}
```

### Doubly Circular Linked List

A doubly circular linked list is a linked list in which the last node points to the first node and each node has a link to the next node and the previous node.

#### Doubly Circular Linked List Implementation

A doubly circular linked list can be implemented using a class in C.

```c
struct Node {
    int data;
    struct Node *prev;
    struct Node *next;
};

struct Node *head = NULL;

struct Node *createNode(int data) {
    struct Node *node = (struct Node *)malloc(sizeof(struct Node));
    node->data = data;
    node->prev = NULL;
    node->next = NULL;
    return node;
}

void insertNode(int data) {
    struct Node *node = createNode(data);
    if (head == NULL) {
        head = node;
        node->next = head;
        node->prev = head;
    } else {
        struct Node *temp = head;
        while (temp->next != head) {
            temp = temp->next;
        }
        temp->next = node;
        node->prev = temp;
        node->next = head;
        head->prev = node;
    }
}

void deleteNode(int data) {
    struct Node *temp = head;
    if (temp->data == data) {
        head = temp->next;
        head->prev = temp->prev;
        temp->prev->next = head;
        free(temp);
    } else {
        while (temp->next != head) {
            if (temp->next->data == data) {
                struct Node *node = temp->next;
                temp->next = node->next;
                node->next->prev = temp;
                free(node);
                break;
            }
            temp = temp->next;
        }
    }
}

void printList() {
    struct Node *temp = head;
    while (temp->next != head) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("%d ", temp->data);
    printf("\n");
}
```

## [Array](Array.md) vs Linked List

| Operation | Array | Linked List |
| --------- | ----- | ----------- |
| Read      | O(1)  | O(n)        |
| Write     | O(1)  | O(n)        |
| Search    | O(n)  | O(n)        |
| Delete    | O(n)  | O(n)        |
