# Questions

## Table of Contents

- [Questions](#questions)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [OOP Questions](#oop-questions)
  - [Data Structures Questions](#data-structures-questions)
  - [Database Questions](#database-questions)
  - [Random Questions](#random-questions)
  - [IQ Questions](#iq-questions)

## Introduction

This section contains questions that can be asked in an interview. The questions are divided into 6 categories:

- [OOP](../OOP/README.md)
- [Data Structure](../DataStructure/README.md)
- [Algorithms](../Algorithms/README.md)
- [Database](../Database/README.md)
- [Random](#random-questions)
- [IQ](#iq-questions)

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

- What is the difference between a mutable and an immutable object?

Ans: A mutable object can be changed after it is created. An immutable object cannot be changed after it is created.

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

- What are the constraints in SQL?
  Ans: Constraints are the rules enforced on data columns on table. These are used to limit the type of data that can go into a table. This ensures the accuracy and reliability of the data in the database. The following are some constraints in SQL:

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

Ans: char array is better because it can be cleared after use.

e.g.

```java
    char[] password = new char[10];
    // code to get password
    // code to use password
    Arrays.fill(password, '0');
```

- What errors appear in compile time and what errors appear in runtime?

Ans: Syntax errors appear in compile time. Runtime errors appear in runtime.

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
  Ans: Pick a fruit from the jar labeled Apple and Orange. If the fruit is Apple, then the jar labeled Apple contains Apple, the jar labeled Orange contains Orange, and the jar labeled Apple and Orange contains Apple. If the fruit is Orange, then the jar labeled Apple contains Orange, the jar labeled Orange contains Apple, and the jar labeled Apple and Orange contains Orange.

- You have a 3 gallon jug and a 5 gallon jug. How can you measure out exactly 4 gallons?

  Ans: Fill the 5 gallon jug and pour it into the 3 gallon jug until the 3 gallon jug is full. Empty the 3 gallon jug. Pour the remaining 2 gallons from the 5 gallon jug into the 3 gallon jug. Fill the 5 gallon jug and pour it into the 3 gallon jug until the 3 gallon jug is full. The 5 gallon jug now contains 4 gallons.

- You have a field in the first day of the year. You plant a flower in the field. The flower doubles in size every day. It takes 100 days for the flower to cover the entire field. How many days does it take for the flower to cover half the field?

  Ans: 99 days.

- You have a cake and you want to cut it into 8 equal pieces. You can only make 3 cuts. How can you cut the cake into 8 equal pieces?

  Ans: Cut the cake into 4 equal pieces. Stack the 4 pieces on top of each other. Cut the cake into 4 equal pieces. Stack the 4 pieces on top of each other. Cut the cake into 4 equal pieces. The cake is now cut into 8 equal pieces.

[**Go Back**](../README.md)
