# Data Structure Questions

## Table of Contents

- [Data Structure Questions](#data-structure-questions)
  - [Table of Contents](#table-of-contents)
    - [What is the difference between an array and a linked list?](#what-is-the-difference-between-an-array-and-a-linked-list)
    - [What is the difference between a stack and a queue?](#what-is-the-difference-between-a-stack-and-a-queue)
    - [How to represent inorder traversal of a binary tree?](#how-to-represent-inorder-traversal-of-a-binary-tree)
    - [How to represent postorder traversal of a binary tree?](#how-to-represent-postorder-traversal-of-a-binary-tree)
    - [What is the time complexity of the following operations on a hash table?](#what-is-the-time-complexity-of-the-following-operations-on-a-hash-table)

### What is the difference between an array and a linked list?

Ans: An array is a data structure that stores a fixed-size sequential collection of elements of the same type. A linked list is a data structure that stores a dynamic-size sequential collection of elements of the same type.

### What is the difference between a stack and a queue?

Ans: A stack is a data structure that stores a collection of elements and only allows access in a last-in-first-out order. A queue is a data structure that stores a collection of elements and only allows access in a first-in-first-out order.

### How to represent inorder traversal of a binary tree?

Ans: Inorder traversal of a binary tree is the process of visiting the left child, then the root and finally the right child.

```c
    void inorderTraversal(struct TreeNode *root) {
        if (root == NULL) {
            return;
        }
        inorderTraversal(root->left);
        printf("%d ", root->val);
        inorderTraversal(root->right);
    }
```

- How to represent preorder traversal of a binary tree?

Ans: Preorder traversal of a binary tree is the process of visiting the root, then the left child and finally the right child.

```c
    void preorderTraversal(struct TreeNode *root) {
        if (root == NULL) {
            return;
        }
        printf("%d ", root->val);
        preorderTraversal(root->left);
        preorderTraversal(root->right);
    }
```

### How to represent postorder traversal of a binary tree?

Ans: Postorder traversal of a binary tree is the process of visiting the left child, then the right child and finally the root.

```c
    void postorderTraversal(struct TreeNode *root) {
        if (root == NULL) {
            return;
        }
        postorderTraversal(root->left);
        postorderTraversal(root->right);
        printf("%d ", root->val);
    }
```

### What is the time complexity of the following operations on a hash table?

- Search
- Insert
- Delete

- Ans: The time complexity of the above operations on a hash table is O(1).

[**Go Back**](README.md)
