# Questions

## Table of Contents

- [Questions](#questions)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Data Structures Questions](#data-structures-questions)
  - [Database Questions](#database-questions)
  - [Random Questions](#random-questions)
  - [IQ Questions](#iq-questions)

## Introduction

This section contains questions that can be asked in an interview. The questions are divided into 6 categories:

- [Data Structure](../DataStructure/README.md)
- [Algorithms](../Algorithms/README.md)
- [Database](../Database/README.md)
- [Random](#random-questions)
- [IQ](#iq-questions)

## Data Structures Questions

- What is the difference between an array and a linked list?

Ans: An array is a data structure that stores a fixed-size sequential collection of elements of the same type. A linked list is a data structure that stores a dynamic-size sequential collection of elements of the same type.

- What is the difference between a stack and a queue?

Ans: A stack is a data structure that stores a collection of elements and only allows access in a last-in-first-out order. A queue is a data structure that stores a collection of elements and only allows access in a first-in-first-out order.

- How to represent inorder traversal of a binary tree?

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

- How to represent postorder traversal of a binary tree?

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

- What is the time complexity of the following operations on a hash table?

  - Search
  - Insert
  - Delete

  - Ans: The time complexity of the above operations on a hash table is O(1).

## Database Questions

- What is the difference between a primary key and a foreign key?
  - Ans: A primary key is a column or a set of columns that uniquely identifies each row in a table. A foreign key is a column or a set of columns that refers to a primary key in another table.
- What is the difference between a clustered index and a non-clustered index?
  - Ans: A clustered index is a type of index in which the order of the rows in the table is the same as the order of the rows in the index. A non-clustered index is a type of index in which the order of the rows in the table is not the same as the order of the rows in the index.
- [What is the difference between a left join and a right join?](../Database/DQL.md#left-join-vs-right-join)

- What Indexing?

  - Ans: Indexing is a way of sorting a number of records on multiple fields. Creating an [index](../Database/DDL.md#create-index) on a field in a table creates another data structure which holds the field value, and pointer to the record it relates to. This index structure is then sorted, allowing Binary Searches to be performed on it.

- What is ERD?

  - Ans: ERD stands for Entity Relationship Diagram. It is a graphical representation of entities and their relationships to each other.

- What are the constraints in SQL?

  - Ans: Constraints are the rules enforced on data columns on table. These are used to limit the type of data that can go into a table. This ensures the accuracy and reliability of the data in the database. The following are some constraints in SQL:

    - NOT NULL Constraint: Ensures that a column cannot have a NULL value.
    - DEFAULT Constraint: Provides a default value for a column when none is specified.
    - UNIQUE Constraint: Ensures that all values in a column are different.
    - CHECK Constraint: Ensures that all values in a column satisfies a specific condition.

## Random Questions

- Swap an array of integers using recursion.

Ans:

```c
    void swap(int *a, int *b) {
        int temp = *a;
        *a = *b;
        *b = temp;
    }

    void swapArray(int *arr, int start, int end) {
        if (start >= end) {
            return;
        }
        swap(&arr[start], &arr[end]);
        swapArray(arr, start + 1, end - 1);
    }
```

- A leap year is a year that is divisible by 4, but not by 100, unless it is also divisible by 400. Write a function that takes a year as a parameter and returns true if the year is a leap year, and false otherwise.

```python
def isLeapYear(year):
    return year % 4 == 0 and (year % 100 != 0 or year % 400 == 0)
```

- Using the `isLeapYear` function, write a function that takes a year and print the following 4 leap years.

```python
def printLeapYears(year):
    count = 0
    while count < 4:
        year += (4-(year%4))
        if isLeapYear(year):
            print(year)
            count += 1
```

- Which better store password in string or char array?

  -Ans: char array is better because it can be cleared after use.

e.g.

```java
    char[] password = new char[10];
    // code to get password
    // code to use password
    Arrays.fill(password, '0');
```

- What errors appear in compile time and what errors appear in runtime?

  -Ans: Syntax errors appear in compile time. Runtime errors appear in runtime.

- Write a function that takes an array of integers and a target integer and returns true if there are 2 integers in the array that add up to the target integer, and false otherwise.

  - O(n<sup>2</sup>) solution

    ```python
    def twoSum(nums, target):
        for i in range(len(nums)):
            for j in range(i+1, len(nums)):
                if nums[i] + nums[j] == target:
                    return True
        return False
    ```

  - O(n) solution

    ```python

    def twoSum(nums, target):
        count = {}
        for num in nums:
            if num in count:
                return True
            else:
                count[target - num] = 1
        return False
    ```

- Write a function takes two strings of numbers and returns which number is greater.

```python
def compare(num1:str,num2:str):
    return num1 if int(num1) > int(num2) else num2
```

- Write a function that takes an array of integers and returns the most frequent integer in the array.

```python
def mostFrequent(nums):
    count = {}
    for num in nums:
        if num in count:
            count[num] += 1
        else:
            count[num] = 1
    return max(count, key=count.get)
```

- Write a function that takes two strings and returns a string that contains only the characters that are not common to both strings.

```python
def uncommonChars(str1, str2):
    count = {}
    for char in str1:
        if char in count:
            count[char] += 1
        else:
            count[char] = 1
    for char in str2:
        if char in count:
            count[char] += 1
        else:
            count[char] = 1
    return ''.join([char for char in count if count[char] == 1])
```

## IQ Questions

- Swap two variables without using a temporary variable.

```c
    void swap(int *a, int *b) {
        *a = *a + *b;
        *b = *a - *b;
        *a = *a - *b;
    }
```

- You have 8 balls. One of them is defective and weighs less than the others. You have a balance scale.

  - Find the defective ball in 3 weighings.
    Ans: Divide the balls into 2 groups of 4 balls each. Weigh the 2 groups. take the lighter group and divide it into 2 groups of 2 balls each. Weigh the 2 groups. Take the lighter group and divide it into 2 groups of 1 ball each. Weigh the 2 groups. The lighter ball is the defective ball.
  - Find the defective ball in 2 weighings.
    Ans: Divide the balls into 3 groups of (3,3,2), weigh the first 2 groups (3,3), if they are equal, then the defective ball is in the third group (2), otherwise the defective ball is in the lighter group (3). Divide the lighter group (3) into 2 groups of (1,1), weigh the 2 groups, if they are equal, then the defective ball is the one that was not weighed, otherwise the defective ball is the lighter ball.
  - Same strategy can be used for 12 balls, 27 balls, 81 balls, etc.

- You have 3 jars that are all mislabeled. One jar contains Apple, another contains Orange, and the third jar contains a mixture of both Apple and Orange. You are allowed to pick as many fruits as you want from each jar to fix the labels on the jars. What is the minimum number of fruits that you have to pick and from which jars to correctly label them?

  - Ans: Pick a fruit from the jar labeled Apple and Orange. If the fruit is Apple, then the jar labeled Apple contains Apple, the jar labeled Orange contains Orange, and the jar labeled Apple and Orange contains Apple. If the fruit is Orange, then the jar labeled Apple contains Orange, the jar labeled Orange contains Apple, and the jar labeled Apple and Orange contains Orange.

- You have a 3 gallon jug and a 5 gallon jug. How can you measure out exactly 4 gallons?

  - Ans: Fill the 5 gallon jug and pour it into the 3 gallon jug until the 3 gallon jug is full. Empty the 3 gallon jug. Pour the remaining 2 gallons from the 5 gallon jug into the 3 gallon jug. Fill the 5 gallon jug and pour it into the 3 gallon jug until the 3 gallon jug is full. The 5 gallon jug now contains 4 gallons.

- You have a field in the first day of the year. You plant a flower in the field. The flower doubles in size every day. It takes 100 days for the flower to cover the entire field. How many days does it take for the flower to cover half the field?

  - Ans: 99 days. The flower doubles in size every day. On the 99th day, the flower covers half the field. On the 100th day, the flower covers the entire field.

- You have a cake and you want to cut it into 8 equal pieces. You can only make 3 cuts. How can you cut the cake into 8 equal pieces?

  - Ans: Cut the cake into 4 equal pieces. Stack the 4 pieces on top of each other. Cut the cake into 4 equal pieces. Stack the 4 pieces on top of each other. Cut the cake into 4 equal pieces. The cake is now cut into 8 equal pieces.

[**Go Back**](../README.md)
