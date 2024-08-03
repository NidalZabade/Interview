# Database Questions

## Table of contents

- [Database Questions](#database-questions)
  - [Table of contents](#table-of-contents)
    - [What is the difference between a primary key and a foreign key?](#what-is-the-difference-between-a-primary-key-and-a-foreign-key)
    - [What is the difference between a clustered index and a non-clustered index?](#what-is-the-difference-between-a-clustered-index-and-a-non-clustered-index)
    - [What is the difference between a left join and a right join?](#what-is-the-difference-between-a-left-join-and-a-right-join)
    - [What Indexing?](#what-indexing)
    - [What is ERD?](#what-is-erd)
    - [What are the constraints in SQL?](#what-are-the-constraints-in-sql)

### What is the difference between a primary key and a foreign key?

Ans: A primary key is a column or a set of columns that uniquely identifies each row in a table. A foreign key is a column or a set of columns that refers to a primary key in another table.

### What is the difference between a clustered index and a non-clustered index?

Ans: A clustered index is a type of index in which the order of the rows in the table is the same as the order of the rows in the index. A non-clustered index is a type of index in which the order of the rows in the table is not the same as the order of the rows in the index.

### [What is the difference between a left join and a right join?](../Database/DQL.md#left-join-vs-right-join)

### What Indexing?

Ans: Indexing is a way of sorting a number of records on multiple fields. Creating an [index](../Database/DDL.md#create-index) on a field in a table creates another data structure which holds the field value, and pointer to the record it relates to. This index structure is then sorted, allowing Binary Searches to be performed on it.

### What is ERD?

Ans: ERD stands for Entity Relationship Diagram. It is a graphical representation of entities and their relationships to each other.

### What are the constraints in SQL?

Ans: Constraints are the rules enforced on data columns on table. These are used to limit the type of data that can go into a table. This ensures the accuracy and reliability of the data in the database. The following are some constraints in SQL:

- NOT NULL Constraint: Ensures that a column cannot have a NULL value.
- DEFAULT Constraint: Provides a default value for a column when none is specified.
- UNIQUE Constraint: Ensures that all values in a column are different.
- CHECK Constraint: Ensures that all values in a column satisfies a specific condition.

[**Go Back**](README.md)
