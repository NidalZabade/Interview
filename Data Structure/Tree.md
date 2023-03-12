# Tree

## Table of Contents

- [Tree](#tree)
  - [Table of Contents](#table-of-contents)
  - [What is a Tree?](#what-is-a-tree)
  - [Tree Types](#tree-types)
    - [Binary Tree](#binary-tree)
      - [Binary Tree Implementation](#binary-tree-implementation)
      - [Binary Tree Operations](#binary-tree-operations)
        - [Insertion](#insertion)
        - [Deletion](#deletion)
        - [Traversal](#traversal)
          - [Preorder](#preorder)
          - [Inorder](#inorder)
          - [Postorder](#postorder)
    - [Binary Search Tree](#binary-search-tree)
      - [Binary Search Tree Implementation](#binary-search-tree-implementation)
      - [Binary Search Tree Operations](#binary-search-tree-operations)
        - [Insertion](#insertion-1)
        - [Deletion](#deletion-1)
        - [Traversal](#traversal-1)
          - [Preorder](#preorder-1)
          - [Inorder](#inorder-1)
          - [Postorder](#postorder-1)
    - [AVL Tree](#avl-tree)
      - [AVL Tree Implementation](#avl-tree-implementation)
      - [AVL Tree Operations](#avl-tree-operations)
        - [Insertion](#insertion-2)
        - [Deletion](#deletion-2)
        - [Traversal](#traversal-2)
    - [B-Tree](#b-tree)
      - [Properties](#properties)
      - [Operations](#operations)
        - [Search](#search)
        - [Insertion](#insertion-3)
        - [Deletion](#deletion-3)
        - [Traversal](#traversal-3)
    - [Splay Tree](#splay-tree)
        - [Insertion](#insertion-4)
        - [Splay](#splay)
        - [Deletion](#deletion-4)
        - [Traversal](#traversal-4)

## What is a Tree?

A tree is a data structure that stores a collection of elements. The elements are organized in a hierarchical structure. The elements are called nodes. Each node has a value and a list of references to other nodes. The references are called children. The first node is called the root node. The root node does not have a parent node. The nodes that do not have any children are called leaf nodes.

## Tree Types

There are two types of trees: binary tree and binary search tree.

### Binary Tree

A binary tree is a tree in which each node has at most two children. The children are called left child and right child.

#### Binary Tree Implementation

```c
struct Node {
    int data;
    struct Node *left;
    struct Node *right;
};
```

#### Binary Tree Operations

There are three types of operations that can be performed on a binary tree: insertion, deletion, and traversal.

##### Insertion

To insert a node to a binary tree, you need to provide the value of the node. The node is then added to the tree (using recursion).

```c
struct Node *insertNode(struct Node *root, int data) {
    if (root == NULL) {
        struct Node *node = (struct Node *)malloc(sizeof(struct Node));
        node->data = data;
        node->left = NULL;
        node->right = NULL;
        return node;
    } else {
        if (data < root->data) {
            root->left = insertNode(root->left, data);
        } else {
            root->right = insertNode(root->right, data);
        }
        return root;
    }
}
```

For example, to insert 1, 2, and 3 to a binary tree, you need to call the insertNode function three times.

```c
root = insertNode(root, 1);
root = insertNode(root, 2);
root = insertNode(root, 3);
```

##### Deletion

To delete a node from a binary tree, you need to provide the value of the node. The node is then removed from the tree (using recursion).

```c
struct Node *deleteNode(struct Node *root, int data) {
    if (root == NULL) {
        return NULL;
    } else {
        if (data < root->data) {
            root->left = deleteNode(root->left, data);
        } else if (data > root->data) {
            root->right = deleteNode(root->right, data);
        } else {
            if (root->left == NULL && root->right == NULL) {
                free(root);
                return NULL;
            } else if (root->left == NULL) {
                struct Node *temp = root->right;
                free(root);
                return temp;
            } else if (root->right == NULL) {
                struct Node *temp = root->left;
                free(root);
                return temp;
            } else {
                struct Node *temp = root->right;
                while (temp->left != NULL) {
                    temp = temp->left;
                }
                root->data = temp->data;
                root->right = deleteNode(root->right, temp->data);
            }
        }
        return root;
    }
}
```

For example, to delete 1, 2, and 3 from a binary tree, you need to call the deleteNode function three times.

```c
root = deleteNode(root, 1);
root = deleteNode(root, 2);
root = deleteNode(root, 3);
```

##### Traversal

There are three types of traversal that can be performed on a binary tree: preorder, inorder, and postorder.

###### Preorder

To traverse a binary tree in preorder, you need to provide the root node of the tree. The traversal starts from the root node. The root node is then traversed in preorder. The traversal ends when all the nodes are traversed.

```c

void preorder(struct Node *root) {
    if (root != NULL) {
        printf("%d ", root->data);
        preorder(root->left);
        preorder(root->right);
    }
}
```

For example, to traverse a binary tree in preorder, you need to call the preorder function.

```c
preorder(root);
```

###### Inorder

To traverse a binary tree in inorder, you need to provide the root node of the tree. The traversal starts from the root node. The root node is then traversed in inorder. The traversal ends when all the nodes are traversed.

```c
void inorder(struct Node *root) {
    if (root != NULL) {
        inorder(root->left);
        printf("%d ", root->data);
        inorder(root->right);
    }
}
```

For example, to traverse a binary tree in inorder, you need to call the inorder function.

```c
inorder(root);
```

###### Postorder

To traverse a binary tree in postorder, you need to provide the root node of the tree. The traversal starts from the root node. The root node is then traversed in postorder. The traversal ends when all the nodes are traversed.

```c
void postorder(struct Node *root) {
    if (root != NULL) {
        postorder(root->left);
        postorder(root->right);
        printf("%d ", root->data);
    }
}
```

For example, to traverse a binary tree in postorder, you need to call the postorder function.

```c
postorder(root);
```

### Binary Search Tree

A binary search tree is a binary tree in which each node has at most two children. The children are called left child and right child. The left child has a value that is less than the value of the parent node. The right child has a value that is greater than the value of the parent node.

#### Binary Search Tree Implementation

```c
struct Node {
    int data;
    struct Node *left;
    struct Node *right;
};
```

#### Binary Search Tree Operations

There are three types of operations that can be performed on a binary search tree: insertion, deletion, and traversal.

##### Insertion

To insert a node to a binary search tree, you need to provide the value of the node. The node is then added to the tree (using recursion).

```c
struct Node *insertNode(struct Node *root, int data) {
    if (root == NULL) {
        struct Node *node = (struct Node *)malloc(sizeof(struct Node));
        node->data = data;
        node->left = NULL;
        node->right = NULL;
        return node;
    } else {
        if (data < root->data) {
            root->left = insertNode(root->left, data);
        } else {
            root->right = insertNode(root->right, data);
        }
        return root;
    }
}
```

For example, to insert 1, 2, and 3 to a binary search tree, you need to call the insertNode function three times.

```c
root = insertNode(root, 1);
root = insertNode(root, 2);
root = insertNode(root, 3);
```

##### Deletion

To delete a node from a binary search tree, you need to provide the value of the node. The node is then removed from the tree (using recursion).

```c
struct Node *deleteNode(struct Node *root, int data) {
    if (root == NULL) {
        return NULL;
    } else {
        if (data < root->data) {
            root->left = deleteNode(root->left, data);
        } else if (data > root->data) {
            root->right = deleteNode(root->right, data);
        } else {
            if (root->left == NULL && root->right == NULL) {
                free(root);
                return NULL;
            } else if (root->left == NULL) {
                struct Node *temp = root->right;
                free(root);
                return temp;
            } else if (root->right == NULL) {
                struct Node *temp = root->left;
                free(root);
                return temp;
            } else {
                struct Node *temp = root->right;
                while (temp->left != NULL) {
                    temp = temp->left;
                }
                root->data = temp->data;
                root->right = deleteNode(root->right, temp->data);
            }
        }
        return root;
    }
}
```

For example, to delete 1, 2, and 3 from a binary search tree, you need to call the deleteNode function three times.

```c
root = deleteNode(root, 1);
root = deleteNode(root, 2);
root = deleteNode(root, 3);
```

##### Traversal

There are three types of traversal that can be performed on a binary search tree: preorder, inorder, and postorder.

###### Preorder

To traverse a binary search tree in preorder, you need to provide the root node of the tree. The traversal starts from the root node. The root node is then traversed in preorder. The traversal ends when all the nodes are traversed.

```c
void preorder(struct Node *root) {
    if (root != NULL) {
        printf("%d ", root->data);
        preorder(root->left);
        preorder(root->right);
    }
}
```

For example, to traverse a binary search tree in preorder, you need to call the preorder function.

```c
preorder(root);
```

###### Inorder

To traverse a binary search tree in inorder, you need to provide the root node of the tree. The traversal starts from the root node. The root node is then traversed in inorder. The traversal ends when all the nodes are traversed.

```c
void inorder(struct Node *root) {
    if (root != NULL) {
        inorder(root->left);
        printf("%d ", root->data);
        inorder(root->right);
    }
}
```

For example, to traverse a binary search tree in inorder, you need to call the inorder function.

```c
inorder(root);
```

###### Postorder

To traverse a binary search tree in postorder, you need to provide the root node of the tree. The traversal starts from the root node. The root node is then traversed in postorder. The traversal ends when all the nodes are traversed.

```c
void postorder(struct Node *root) {
    if (root != NULL) {
        postorder(root->left);
        postorder(root->right);
        printf("%d ", root->data);
    }
}
```

For example, to traverse a binary search tree in postorder, you need to call the postorder function.

```c
postorder(root);
```

### AVL Tree

An AVL tree is a binary search tree in which the difference between the heights of the left and right subtrees of any node is at most one. The left subtree of a node has a height that is less than or equal to the height of the right subtree of the node. The right subtree of a node has a height that is less than or equal to the height of the left subtree of the node.

#### AVL Tree Implementation

```c
struct Node {
    int data;
    int height;
    struct Node *left;
    struct Node *right;
};
```

#### AVL Tree Operations

There are three types of operations that can be performed on an AVL tree: insertion, deletion, and traversal.

##### Insertion

To insert a node to an AVL tree, you need to provide the value of the node. The node is then added to the tree (using recursion).

```c
int height(struct Node *root) {
    if (root == NULL) {
        return -1;
    } else {
        return root->height;
    }
}

int max(int a, int b) {
    return a > b ? a : b;
}

struct Node *rotateLeft(struct Node *root) {
    struct Node *temp = root->right;
    root->right = temp->left;
    temp->left = root;
    root->height = max(height(root->left), height(root->right)) + 1;
    temp->height = max(height(temp->left), height(temp->right)) + 1;
    return temp;
}

struct Node *rotateRight(struct Node *root) {
    struct Node *temp = root->left;
    root->left = temp->right;
    temp->right = root;
    root->height = max(height(root->left), height(root->right)) + 1;
    temp->height = max(height(temp->left), height(temp->right)) + 1;
    return temp;
}

struct Node *rotateLeftRight(struct Node *root) {
    root->left = rotateLeft(root->left);
    return rotateRight(root);
}

struct Node *rotateRightLeft(struct Node *root) {
    root->right = rotateRight(root->right);
    return rotateLeft(root);
}

struct Node *insertNode(struct Node *root, int data) {
    if (root == NULL) {
        struct Node *temp = (struct Node *)malloc(sizeof(struct Node));
        temp->data = data;
        temp->height = 0;
        temp->left = NULL;
        temp->right = NULL;
        return temp;
    } else {
        if (data < root->data) {
            root->left = insertNode(root->left, data);
            if (height(root->left) - height(root->right) == 2) {
                if (data < root->left->data) {
                    root = rotateRight(root);
                } else {
                    root = rotateLeftRight(root);
                }
            }
        } else {
            root->right = insertNode(root->right, data);
            if (height(root->right) - height(root->left) == 2) {
                if (data > root->right->data) {
                    root = rotateLeft(root);
                } else {
                    root = rotateRightLeft(root);
                }
            }
        }
        root->height = max(height(root->left), height(root->right)) + 1;
        return root;
    }
}
```

For example, to insert 1, 2, and 3 to an AVL tree, you need to call the insertNode function three times.

```c
root = insertNode(root, 1);
root = insertNode(root, 2);
root = insertNode(root, 3);
```

##### Deletion

To delete a node from an AVL tree, you need to provide the value of the node. The node is then deleted from the tree (using recursion).

```c
struct Node *deleteNode(struct Node *root, int data) {
    if (root == NULL) {
        return NULL;
    } else {
        if (data < root->data) {
            root->left = deleteNode(root->left, data);
            if (height(root->right) - height(root->left) == 2) {
                if (height(root->right->left) > height(root->right->right)) {
                    root = rotateRightLeft(root);
                } else {
                    root = rotateLeft(root);
                }
            }
        } else if (data > root->data) {
            root->right = deleteNode(root->right, data);
            if (height(root->left) - height(root->right) == 2) {
                if (height(root->left->right) > height(root->left->left)) {
                    root = rotateLeftRight(root);
                } else {
                    root = rotateRight(root);
                }
            }
        } else {
            if (root->left == NULL && root->right == NULL) {
                free(root);
                return NULL;
            } else if (root->left == NULL) {
                struct Node *temp = root->right;
                free(root);
                return temp;
            } else if (root->right == NULL) {
                struct Node *temp = root->left;
                free(root);
                return temp;
            } else {
                struct Node *temp = root->right;
                while (temp->left != NULL) {
                    temp = temp->left;
                }
                root->data = temp->data;
                root->right = deleteNode(root->right, temp->data);
            }
        }
        root->height = max(height(root->left), height(root->right)) + 1;
        return root;
    }
}
```

For example, to delete 1, 2, and 3 from an AVL tree, you need to call the deleteNode function three times.

```c
root = deleteNode(root, 1);
root = deleteNode(root, 2);
root = deleteNode(root, 3);
```

##### Traversal

To traverse an AVL tree, you need to provide the root of the tree. The tree is then traversed in preorder, inorder, or postorder (using recursion).

```c
void preorder(struct Node *root) {
    if (root != NULL) {
        printf("%d ", root->data);
        preorder(root->left);
        preorder(root->right);
    }
}

void inorder(struct Node *root) {
    if (root != NULL) {
        inorder(root->left);
        printf("%d ", root->data);
        inorder(root->right);
    }
}

void postorder(struct Node *root) {
    if (root != NULL) {
        postorder(root->left);
        postorder(root->right);
        printf("%d ", root->data);
    }
}
```

For example, to traverse an AVL tree in preorder, you need to call the preorder function.

```c
preorder(root);
```

### B-Tree

A B-tree is a self-balancing tree data structure that keeps data sorted and allows searches, sequential access, insertions, and deletions in logarithmic time. The B-tree is a generalization of a binary search tree in that a node can have more than two children. Unlike self-balancing binary search trees, the B-tree is optimized for systems that read and write large blocks of data. It is commonly used in databases and file systems.

#### Properties

A B-tree is a rooted tree that satisfies the following properties:

- Every node has at most m children.
- Every non-leaf node (except root) has at least ⌈m/2⌉ children.
- The root has at least two children if it is not a leaf node.
- A non-leaf node with k children contains k−1 keys.
- All leaves appear in the same level and contain no keys.

#### Operations

##### Search

To search a B-tree, you need to provide the root of the tree and the value to search. The tree is then searched (using recursion).

```c
struct Node *search(struct Node *root, int data) {
    if (root == NULL) {
        return NULL;
    } else {
        int i = 0;
        while (i < root->count && data > root->data[i]) {
            i++;
        }
        if (i < root->count && data == root->data[i]) {
            return root;
        } else if (root->leaf) {
            return NULL;
        } else {
            return search(root->child[i], data);
        }
    }
}
```

For example, to search a B-tree, you need to call the search function.

```c
struct Node *node = search(root, 1);
```

##### Insertion

To insert a node to a B-tree, you need to provide the root of the tree and the value of the node. The node is then inserted to the tree (using recursion).

```c
struct Node *insert(struct Node *root, int data) {
    if (root == NULL) {
        root = (struct Node *)malloc(sizeof(struct Node));
        root->data[0] = data;
        root->count = 1;
        root->leaf = true;
        return root;
    } else {
        if (root->count == 2 * t - 1) {
            struct Node *s = (struct Node *)malloc(sizeof(struct Node));
            s->child[0] = root;
            s->leaf = false;
            splitChild(s, 0);
            int i = 0;
            if (s->data[0] < data) {
                i++;
            }
            insertNonFull(s->child[i], data);
            return s;
        } else {
            insertNonFull(root, data);
            return root;
        }
    }
}

void insertNonFull(struct Node *root, int data) {
    int i = root->count - 1;
    if (root->leaf) {
        while (i >= 0 && data < root->data[i]) {
            root->data[i + 1] = root->data[i];
            i--;
        }
        root->data[i + 1] = data;
        root->count++;
    } else {
        while (i >= 0 && data < root->data[i]) {
            i--;
        }
        i++;
        if (root->child[i]->count == 2 * t - 1) {
            splitChild(root, i);
            if (root->data[i] < data) {
                i++;
            }
        }
        insertNonFull(root->child[i], data);
    }
}

void splitChild(struct Node *root, int i) {
    struct Node *y = root->child[i];
    struct Node *z = (struct Node *)malloc(sizeof(struct Node));
    z->leaf = y->leaf;
    z->count = t - 1;
    for (int j = 0; j < t - 1; j++) {
        z->data[j] = y->data[j + t];
    }
    if (!y->leaf) {
        for (int j = 0; j < t; j++) {
            z->child[j] = y->child[j + t];
        }
    }
    y->count = t - 1;
    for (int j = root->count; j >= i + 1; j--) {
        root->child[j + 1] = root->child[j];
    }
    root->child[i + 1] = z;
    for (int j = root->count - 1; j >= i; j--) {
        root->data[j + 1] = root->data[j];
    }
    root->data[i] = y->data[t - 1];
    root->count++;
}
```

For example, to insert 1, 2, and 3 to a B-tree, you need to call the insert function three times.

```c
root = insert(root, 1);
root = insert(root, 2);
root = insert(root, 3);
```

##### Deletion

To delete a node from a B-tree, you need to provide the root of the tree and the value of the node. The node is then deleted from the tree (using recursion).

```c
struct Node *remove(struct Node *root, int data) {
    if (root == NULL) {
        return NULL;
    } else {
        int i = 0;
        while (i < root->count && data > root->data[i]) {
            i++;
        }
        if (i < root->count && data == root->data[i]) {
            if (root->leaf) {
                for (int j = i + 1; j < root->count; j++) {
                    root->data[j - 1] = root->data[j];
                }
                root->count--;
                return root;
            } else {
                if (root->child[i]->count >= t) {
                    int predecessor = getPredecessor(root, i);
                    root->data[i] = predecessor;
                    root->child[i] = remove(root->child[i], predecessor);
                } else if (root->child[i + 1]->count >= t) {
                    int successor = getSuccessor(root, i);
                    root->data[i] = successor;
                    root->child[i + 1] = remove(root->child[i + 1], successor);
                } else {
                    merge(root, i);
                    root->child[i] = remove(root->child[i], data);
                }
                return root;
            }
        } else if (root->leaf) {
            return NULL;
        } else {
            if (root->child[i]->count == t - 1) {
                if (i > 0 && root->child[i - 1]->count >= t) {
                    borrowFromPrevious(root, i);
                } else if (i < root->count && root->child[i + 1]->count >= t) {
                    borrowFromNext(root, i);
                } else {
                    if (i < root->count) {
                        merge(root, i);
                    } else {
                        merge(root, i - 1);
                    }
                }
            }
            return remove(root->child[i], data);
        }
    }
}

int getPredecessor(struct Node *root, int i) {
    struct Node *current = root->child[i];
    while (!current->leaf) {
        current = current->child[current->count];
    }
    return current->data[current->count - 1];
}

int getSuccessor(struct Node *root, int i) {
    struct Node *current = root->child[i + 1];
    while (!current->leaf) {
        current = current->child[0];
    }
    return current->data[0];
}

void borrowFromPrevious(struct Node *root, int i) {
    struct Node *child = root->child[i];
    struct Node *sibling = root->child[i - 1];
    for (int j = child->count - 1; j >= 0; j--) {
        child->data[j + 1] = child->data[j];
    }
    if (!child->leaf) {
        for (int j = child->count; j >= 0; j--) {
            child->child[j + 1] = child->child[j];
        }
    }
    child->data[0] = root->data[i - 1];
    if (!child->leaf) {
        child->child[0] = sibling->child[sibling->count];
    }
    root->data[i - 1] = sibling->data[sibling->count - 1];
    child->count++;
    sibling->count--;
}

void borrowFromNext(struct Node *root, int i) {
    struct Node *child = root->child[i];
    struct Node *sibling = root->child[i + 1];
    child->data[child->count] = root->data[i];
    if (!child->leaf) {
        child->child[child->count + 1] = sibling->child[0];
    }
    root->data[i] = sibling->data[0];
    for (int j = 1; j < sibling->count; j++) {
        sibling->data[j - 1] = sibling->data[j];
    }
    if (!sibling->leaf) {
        for (int j = 1; j <= sibling->count; j++) {
            sibling->child[j - 1] = sibling->child[j];
        }
    }
    child->count++;
    sibling->count--;
}

void merge(struct Node *root, int i) {
    struct Node *child = root->child[i];
    struct Node *sibling = root->child[i + 1];
    child->data[t - 1] = root->data[i];
    for (int j = 0; j < sibling->count; j++) {
        child->data[j + t] = sibling->data[j];
    }
    if (!child->leaf) {
        for (int j = 0; j <= sibling->count; j++) {
            child->child[j + t] = sibling->child[j];
        }
    }
    for (int j = i + 1; j < root->count; j++) {
        root->data[j - 1] = root->data[j];
    }
    for (int j = i + 2; j <= root->count; j++) {
        root->child[j - 1] = root->child[j];
    }
    child->count += sibling->count + 1;
    root->count--;
    free(sibling);
}
```

For example, to delete 1, 2, and 3 from a B-tree, you need to call the remove function three times.

```c
root = remove(root, 1);
root = remove(root, 2);
root = remove(root, 3);
```

##### Traversal

To traverse a B-tree, you need to provide the root of the tree. The tree is then traversed (using recursion).

```c
void traverse(struct Node *root) {
    if (root == NULL) {
        return;
    }
    int i;
    for (i = 0; i < root->count; i++) {
        if (!root->leaf) {
            traverse(root->child[i]);
        }
        printf("%d ", root->data[i]);
    }
    if (!root->leaf) {
        traverse(root->child[i]);
    }
}
```

For example, to traverse a B-tree, you need to call the traverse function.

```c
traverse(root);
```

### Splay Tree

A splay tree is a self-adjusting binary search tree with the additional property that recently accessed elements are quick to access again. It performs basic operations such as insertion, look-up and removal in O(log n) amortized time. The amortized time complexity of the above operations is O(log n) because of the sublinear amortized time complexity of the splay operation.

##### Insertion

To insert a node in a splay tree, you need to provide the root of the tree and the data to be inserted. The tree is then modified (using recursion).

```c
struct Node *insert(struct Node *root, int data) {
    if (root == NULL) {
        return newNode(data);
    }
    if (data < root->data) {
        root->left = insert(root->left, data);
    } else if (data > root->data) {
        root->right = insert(root->right, data);
    } else {
        return root;
    }
    return splay(root, data);
}
```

For example, to insert 1, 2, and 3 in a splay tree, you need to call the insert function three times.

```c
root = insert(root, 1);
root = insert(root, 2);
root = insert(root, 3);
```

##### Splay

To splay a node in a splay tree, you need to provide the root of the tree and the data to be splayed. The tree is then modified (using recursion).

```c
struct Node *splay(struct Node *root, int data) {
    if (root == NULL || root->data == data) {
        return root;
    }
    if (root->data > data) {
        if (root->left == NULL) {
            return root;
        }
        if (root->left->data > data) {
            root->left->left = splay(root->left->left, data);
            root = rightRotate(root);
        } else if (root->left->data < data) {
            root->left->right = splay(root->left->right, data);
            if (root->left->right != NULL) {
                root->left = leftRotate(root->left);
            }
        }
        return (root->left == NULL) ? root : rightRotate(root);
    } else {
        if (root->right == NULL) {
            return root;
        }
        if (root->right->data > data) {
            root->right->left = splay(root->right->left, data);
            if (root->right->left != NULL) {
                root->right = rightRotate(root->right);
            }
        } else if (root->right->data < data) {
            root->right->right = splay(root->right->right, data);
            root = leftRotate(root);
        }
        return (root->right == NULL) ? root : leftRotate(root);
    }
}
```

##### Deletion

To delete a node in a splay tree, you need to provide the root of the tree and the data to be deleted. The tree is then modified (using recursion).

```c
struct Node *remove(struct Node *root, int data) {
    struct Node *temp;
    if (root == NULL) {
        return NULL;
    }
    root = splay(root, data);
    if (data != root->data) {
        return root;
    }
    if (root->left == NULL) {
        temp = root;
        root = root->right;
    } else {
        temp = root;
        root = splay(root->left, data);
        root->right = temp->right;
    }
    free(temp);
    return root;
}
```

For example, to delete 1, 2, and 3 from a splay tree, you need to call the remove function three times.

```c
root = remove(root, 1);
root = remove(root, 2);
root = remove(root, 3);
```

##### Traversal

To traverse a splay tree, you need to provide the root of the tree. The tree is then traversed (using recursion).

```c
void traverse(struct Node *root) {
    if (root == NULL) {
        return;
    }
    traverse(root->left);
    printf("%d ", root->data);
    traverse(root->right);
}
```

For example, to traverse a splay tree, you need to call the traverse function.

```c
traverse(root);
```
