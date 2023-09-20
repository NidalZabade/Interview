# Questions

## Table of Contents

- [Questions](#questions)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [OOP Questions](#oop-questions)
  - [Data Structures Questions](#data-structures-questions)
  - [Database Questions](#database-questions)
  - [Random Questions](#random-questions)

## Introduction

This section contains questions that can be asked in an interview. The questions are divided into 3 categories:

- [OOP](../OOP/README.md)
- [Data Structure](../DataStructure/README.md)
- [Algorithms](../Algorithms/README.md)

## OOP Questions

- [What is OOP?](../OOP/README.md#what-is-oop)
- [What is class?](../OOP/Class.md#what-is-a-class)
- [What is object?](../OOP/Class.md#object)
- [What is the difference between an interface and an abstract class?](../OOP/Abstraction.md#abstract-vs-interface)
- [What is Polymorphism?](../OOP/Polymorphism.md#what-is-polymorphism)
- [What is Encapsulation?](../OOP/Encapsulation.md#what-is-encapsulation)
- What is the difference between == and equals()?

Ans: == is used to compare primitive types and references. equals() is used to compare objects.

For example:

```java
    String s1 = "Hello";
    String s2 = "Hello";
    String s3 = new String("Hello");

    System.out.println(s1 == s2); // true
    System.out.println(s1 == s3); // false
    System.out.println(s1.equals(s3)); // true
    System.out.println(s1.equals(s2)); // true
```

- What is the difference between a checked exception and an unchecked exception?

Ans: Checked exceptions are checked at compile time. Unchecked exceptions are checked at runtime.

For example:

```java
    public void readFile() throws IOException {
        // code to read file
    }
```

In the above example, IOException is a checked exception. If the code in readFile() throws an IOException, then the readFile() method must either handle the exception or declare that it throws the exception. If readFile() does not handle the exception or declare that it throws the exception, then the code will not compile.

```java
    public void readFile() {
        // code to read file
    }
```

In the above example, there is no checked exception. If the code in readFile() throws an exception, then the readFile() method must either handle the exception or declare that it throws the exception. If readFile() does not handle the exception or declare that it throws the exception, then the code will compile.

- What is the difference between a final, finally, and finalize?

Ans: final is a keyword used to make a variable constant. finally is a block that is always executed whether an exception is handled or not. finalize is a method that is called by the garbage collector on an object before garbage collection.

- What is the difference between a static and a non-static method?

Ans: A static method can be called without creating an object of the class. A non-static method must be called by creating an object of the class.

- What is the difference between a static and a non-static variable?

Ans: A static variable is shared by all the objects of the class. A non-static variable is not shared by all the objects of the class.

- What is the difference between a constructor and a method?

Ans: A constructor is used to initialize the object. A method is used to perform some operations.

- What is the difference between a class and an object?

Ans: A class is a blueprint from which objects are created. An object is an instance of a class.

- What is the difference between a class and an interface?

Ans: A class can have both abstract and concrete methods. An interface can have only abstract methods.

- Represent a family consisting of a father, mother, and children using OOP.

```java
class Person {
    private String name;
    private int age;
    private Person father;
    private Person mother;

    public Person(String name, int age, Person father, Person mother) {
        this.name = name;
        this.age = age;
        this.father = father;
        this.mother = mother;
    }

    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }

    public Person getFather() {
        return father;
    }

    public Person getMother() {
        return mother;
    }

}

class Family {
    private Person father;
    private Person mother;
    private List<Person> children;

    public Family(Person father, Person mother, List<Person> children) {
        this.father = father;
        this.mother = mother;
        this.children = children;
    }

    public Person getFather() {
        return father;
    }

    public Person getMother() {
        return mother;
    }

    public List<Person> getChildren() {
        return children;
    }
}
```

- [What is the SOLID principle?](../OOP/SOLID.md#introduction)

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

Ans: The time complexity of the above operations on a hash table is O(1).

## Database Questions

- What is the difference between a primary key and a foreign key?
  Ans: A primary key is a column or a set of columns that uniquely identifies each row in a table. A foreign key is a column or a set of columns that refers to a primary key in another table.
- What is the difference between a clustered index and a non-clustered index?
  Ans: A clustered index is a type of index in which the order of the rows in the table is the same as the order of the rows in the index. A non-clustered index is a type of index in which the order of the rows in the table is not the same as the order of the rows in the index.
- [What is the difference between a left join and a right join?](../Database/DQL.md#left-join-vs-right-join)

- What Indexing?
  Ans: Indexing is a way of sorting a number of records on multiple fields. Creating an [index](../Database/DDL.md#create-index) on a field in a table creates another data structure which holds the field value, and pointer to the record it relates to. This index structure is then sorted, allowing Binary Searches to be performed on it.

- What is ERD?
  Ans: ERD stands for Entity Relationship Diagram. It is a graphical representation of entities and their relationships to each other.

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

- Swap two variables without using a temporary variable.

```c
    void swap(int *a, int *b) {
        *a = *a + *b;
        *b = *a - *b;
        *a = *a - *b;
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

[**Go Back**](../README.md)
