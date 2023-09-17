# Database

## Table of contents

- [Database](#database)
  - [Table of contents](#table-of-contents)
  - [What is a databases?](#what-is-a-databases)
  - [Types of databases](#types-of-databases)
  - [Relational databases](#relational-databases)
    - [Relational database example](#relational-database-example)
  - [Non-relational databases](#non-relational-databases)
    - [Non-relational database example](#non-relational-database-example)
  - [SQL vs NoSQL](#sql-vs-nosql)
  - [SQL](#sql)
  - [ORM](#orm)
    - [ORM example](#orm-example)

## What is a databases?

A database is a collection of information that is organized so that it can be easily accessed, managed and updated.

## Types of databases

There are several types of databases, here are some of them:

- Relational databases
- Non-relational databases

## Relational databases

A relational database is a type of database that stores and provides access to data points that are related to one another. Relational databases are based on the relational model, an intuitive, straightforward way of representing data in tables. In a relational database, each row in the table is a record with a unique ID called the key. The columns of the table hold attributes of the data, and each record usually has a value for each attribute, making it easy to establish the relationships among data points.

### Relational database example

| ID  | Name  | Age | City     |
| --- | ----- | --- | -------- |
| 1   | John  | 30  | New York |
| 2   | Mary  | 25  | London   |
| 3   | Peter | 40  | Paris    |

## Non-relational databases

A non-relational database is a database that does not incorporate the table/key model that relational database management systems (RDBMS) promote. Instead, non-relational databases use a storage model that is optimized for the specific requirements of the type of data being stored. Non-relational databases are also referred to as NoSQL databases — with the SQL referring to structured query language — to indicate that they do not use the same language as relational databases to query data.

### Non-relational database example

```json
{
  "id": 1,
  "name": "John",
  "age": 30,
  "city": "New York"
}
```

## SQL vs NoSQL

| SQL                                                                                                                 | NoSQL                                                                                                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| SQL databases are primarily called as Relational Databases (RDBMS)                                                  | NoSQL database are primarily called as non-relational or distributed database.                                                                                                                |
| SQL databases are table based databases                                                                             | NoSQL databases are document based, key-value pairs, graph databases or wide-column stores                                                                                                    |
| SQL databases have predefined schema                                                                                | NoSQL databases have dynamic schema for unstructured data                                                                                                                                     |
| SQL databases are vertically scalable                                                                               | NoSQL databases are horizontally scalable                                                                                                                                                     |
| SQL databases uses SQL ( structured query language ) for defining and manipulating the data, which is very powerful | NoSQL database, queries are focused on collection of documents. Sometimes it is also called as UnQL (Unstructured Query Language). The syntax of using UnQL varies from database to database. |
| SQL database examples: MySql, Oracle, Sqlite, Postgres and MS-SQL                                                   | NoSQL database examples: MongoDB, BigTable, Redis, RavenDb, Cassandra, Hbase, Neo4j and CouchDb                                                                                               |

## SQL

SQL stands for Structured Query Language. SQL is used to communicate with a database.
SQL divides commands into the following categories:

- [Data Definition Language (DDL)](DDL.md)
- [Data Query Language (DQL)](DQL.md)
- [Data Manipulation Language (DML)](DML.md)
- [Data Control Language (DCL)](DCL.md)

## ORM

ORM stands for Object-Relational Mapping. ORM is a programming technique for converting data between relational databases and object oriented programming languages such as Java, C#, etc.

### ORM example

```java
@Entity
@Table(name = "users")
public class User {
  @Id
  @GeneratedValue(strategy = GenerationType.IDENTITY)
  private Long id;

  @Column(name = "first_name")
  private String firstName;

  @Column(name = "last_name")
  private String lastName;

  @Column(name = "email")
  private String email;

  // getters and setters
}
```

[**Go Back**](../README.md)
