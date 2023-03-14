# Hash Table

## Table of Contents

- [Hash Table](#hash-table)
  - [Table of Contents](#table-of-contents)
  - [What is a Hash Table?](#what-is-a-hash-table)
  - [Hash Table Implementation](#hash-table-implementation)
  - [Hash Function](#hash-function)
  - [Hash Collision](#hash-collision)
    - [Separate Chaining](#separate-chaining)
    - [Open Addressing](#open-addressing)
      - [Linear Probing](#linear-probing)
      - [Quadratic Probing](#quadratic-probing)
      - [Double Hashing](#double-hashing)
  - [Hash Table Load Factor](#hash-table-load-factor)
  - [Hash Table Rehashing](#hash-table-rehashing)

## What is a Hash Table?

A hash table is a data structure that stores a collection of elements. Each element is identified by a key. The key is a number that represents the position of the element in the hash table. The first element in the hash table has a key of 0, the second element has a key of 1, and so on.

## Hash Table Implementation

A hash table can be implemented using an array in c.

```c
int hashTable[10];
```

## Hash Function

A hash function is a function that takes a key and returns the position of the element in the hash table. The hash function is used to calculate the position of the element in the hash table.

```c
int hashFunction(int key) {
    return key % 10;
}
```

## Hash Collision

A hash collision occurs when two elements have the same key. This can happen when the hash function returns the same key for two different elements. There are two ways to handle hash collisions:

- Separate Chaining
- Open Addressing

### Separate Chaining

Separate chaining is a method of handling hash collisions. In separate chaining, each element in the hash table is a linked list. When a hash collision occurs, the element is added to the linked list.

```c
struct Node {
    int key;
    int value;
    struct Node *next;
};

struct Node *hashTable[10];

int hashFunction(int key) {
    return key % 10;
}

void insert(int key, int value) {
    int hashKey = hashFunction(key);
    struct Node *newNode = (struct Node *)malloc(sizeof(struct Node));
    newNode->key = key;
    newNode->value = value;
    newNode->next = NULL;
    if (hashTable[hashKey] == NULL) {
        hashTable[hashKey] = newNode;
    } else {
        struct Node *currentNode = hashTable[hashKey];
        while (currentNode->next != NULL) {
            currentNode = currentNode->next;
        }
        currentNode->next = newNode;
    }
}

int search(int key) {
    int hashKey = hashFunction(key);
    if (hashTable[hashKey] == NULL) {
        return -1;
    } else {
        struct Node *currentNode = hashTable[hashKey];
        while (currentNode != NULL) {
            if (currentNode->key == key) {
                return currentNode->value;
            }
            currentNode = currentNode->next;
        }
        return -1;
    }
}

void delete(int key) {
    int hashKey = hashFunction(key);
    if (hashTable[hashKey] == NULL) {
        return;
    } else {
        struct Node *currentNode = hashTable[hashKey];
        struct Node *previousNode = NULL;
        while (currentNode != NULL) {
            if (currentNode->key == key) {
                if (previousNode == NULL) {
                    hashTable[hashKey] = currentNode->next;
                } else {
                    previousNode->next = currentNode->next;
                }
                free(currentNode);
                return;
            }
            previousNode = currentNode;
            currentNode = currentNode->next;
        }
    }
}
```

### Open Addressing

Open addressing is a method of handling hash collisions. In open addressing, each element in the hash table is a single element. When a hash collision occurs, the element is added to the next available position in the hash table.

There are three types of open addressing:

- Linear Probing
- Quadratic Probing
- Double Hashing

#### Linear Probing

In linear probing, the next available position in the hash table is calculated by adding 1 to the current position.

```c
int hashTable[10];

int hashFunction(int key) {
    return key % 10;
}

int linearProbing(int key) {
    int hashKey = hashFunction(key);
    int i = 0;
    while (hashTable[(hashKey + i) % 10] != 0) {
        i++;
    }
    return (hashKey + i) % 10;
}

void insert(int key) {
    int hashKey = linearProbing(key);
    hashTable[hashKey] = key;
}

int search(int key) {
    int hashKey = hashFunction(key);
    int i = 0;
    while (hashTable[(hashKey + i) % 10] != key) {
        if (hashTable[(hashKey + i) % 10] == 0) {
            return -1;
        }
        i++;
    }
    return (hashKey + i) % 10;
}

void delete(int key) {
    int hashKey = hashFunction(key);
    int i = 0;
    while (hashTable[(hashKey + i) % 10] != key) {
        if (hashTable[(hashKey + i) % 10] == 0) {
            return;
        }
        i++;
    }
    hashTable[(hashKey + i) % 10] = 0;
}
```

#### Quadratic Probing

In quadratic probing, the next available position in the hash table is calculated by adding i^2 to the current position.

```c
int hashTable[10];

int hashFunction(int key) {
    return key % 10;
}

int quadraticProbing(int key) {
    int hashKey = hashFunction(key);
    int i = 0;
    while (hashTable[(hashKey + i * i) % 10] != 0) {
        i++;
    }
    return (hashKey + i * i) % 10;
}

void insert(int key) {
    int hashKey = quadraticProbing(key);
    hashTable[hashKey] = key;
}

int search(int key) {
    int hashKey = hashFunction(key);
    int i = 0;
    while (hashTable[(hashKey + i * i) % 10] != key) {
        if (hashTable[(hashKey + i * i) % 10] == 0) {
            return -1;
        }
        i++;
    }
    return (hashKey + i * i) % 10;
}

void delete(int key) {
    int hashKey = hashFunction(key);
    int i = 0;
    while (hashTable[(hashKey + i * i) % 10] != key) {
        if (hashTable[(hashKey + i * i) % 10] == 0) {
            return;
        }
        i++;
    }
    hashTable[(hashKey + i * i) % 10] = 0;
}
```

#### Double Hashing

In double hashing, the next available position in the hash table is calculated by adding i \* hashFunction2(key) to the current position.

```c
int hashTable[10];

int hashFunction1(int key) {
    return key % 10;
}

int hashFunction2(int key) {
    return 7 - (key % 7);
}

int doubleHashing(int key) {
    int hashKey = hashFunction1(key);
    int i = 0;
    while (hashTable[(hashKey + i * hashFunction2(key)) % 10] != 0) {
        i++;
    }
    return (hashKey + i * hashFunction2(key)) % 10;
}

void insert(int key) {
    int hashKey = doubleHashing(key);
    hashTable[hashKey] = key;
}

int search(int key) {
    int hashKey = hashFunction1(key);
    int i = 0;
    while (hashTable[(hashKey + i * hashFunction2(key)) % 10] != key) {
        if (hashTable[(hashKey + i * hashFunction2(key)) % 10] == 0) {
            return -1;
        }
        i++;
    }
    return (hashKey + i * hashFunction2(key)) % 10;
}

void delete(int key) {
    int hashKey = hashFunction1(key);
    int i = 0;
    while (hashTable[(hashKey + i * hashFunction2(key)) % 10] != key) {
        if (hashTable[(hashKey + i * hashFunction2(key)) % 10] == 0) {
            return;
        }
        i++;
    }
    hashTable[(hashKey + i * hashFunction2(key)) % 10] = 0;
}
```

## Hash Table Load Factor

The load factor of a hash table is the ratio of the number of elements in the hash table to the size of the hash table. The load factor is used to determine when the hash table needs to be resized.

The load factor is calculated by dividing the number of elements in the hash table by the size of the hash table.

```c
loadFactor = numberOfElements / sizeOfHashTable
```

The load factor is usually represented as a decimal number between 0 and 1. A load factor of 0.75 means that the hash table is 75% full.

The load factor is used to determine when the hash table needs to be resized. When the load factor is greater than 0.75, the hash table needs to be resized.

## Hash Table Rehashing

Rehashing is the process of resizing a hash table. When the load factor of a hash table is greater than 0.75, the hash table needs to be resized.

When a hash table is resized, the elements in the hash table are rehashed and added to the new hash table.

```c
int hashTable[10];

int hashFunction(int key) {
    return key % 10;
}

int linearProbing(int key) {
    int hashKey = hashFunction(key);
    int i = 0;
    while (hashTable[(hashKey + i) % 10] != 0) {
        i++;
    }
    return (hashKey + i) % 10;
}

void insert(int key) {
    int hashKey = linearProbing(key);
    hashTable[hashKey] = key;
}

int search(int key) {
    int hashKey = hashFunction(key);
    int i = 0;
    while (hashTable[(hashKey + i) % 10] != key) {
        if (hashTable[(hashKey + i) % 10] == 0) {
            return -1;
        }
        i++;
    }
    return (hashKey + i) % 10;
}

void delete(int key) {
    int hashKey = hashFunction(key);
    int i = 0;
    while (hashTable[(hashKey + i) % 10] != key) {
        if (hashTable[(hashKey + i) % 10] == 0) {
            return;
        }
        i++;
    }
    hashTable[(hashKey + i) % 10] = 0;
}

void rehash() {
    int temp[10];
    for (int i = 0; i < 10; i++) {
        temp[i] = hashTable[i];
        hashTable[i] = 0;
    }
    for (int i = 0; i < 10; i++) {
        if (temp[i] != 0) {
            insert(temp[i]);
        }
    }
}
```

[**Go Back To Data Structure**](README.md)
