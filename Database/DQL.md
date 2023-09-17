# Data Query Language (DQL)

## Table of contents

- [Data Query Language (DQL)](#data-query-language-dql)
  - [Table of contents](#table-of-contents)
  - [DQL](#dql)
    - [SELECT](#select)
    - [SELECT DISTINCT](#select-distinct)
    - [WHERE](#where)
    - [AND, OR and NOT](#and-or-and-not)
    - [ORDER BY](#order-by)
    - [GROUP BY](#group-by)
    - [HAVING](#having)
    - [LIMIT](#limit)
    - [OFFSET](#offset)
    - [IN](#in)
    - [BETWEEN](#between)
    - [LIKE](#like)
    - [JOIN](#join)
      - [INNER JOIN](#inner-join)
      - [LEFT JOIN](#left-join)
      - [RIGHT JOIN](#right-join)
      - [OUTER JOIN](#outer-join)
      - [LEFT JOIN vs RIGHT JOIN](#left-join-vs-right-join)
    - [UNION](#union)
    - [UNION ALL](#union-all)
    - [INTERSECT](#intersect)
    - [EXCEPT](#except)
    - [ANY](#any)
    - [ALL](#all)
    - [EXISTS](#exists)
    - [CASE](#case)

## DQL

DQL stands for Data Query Language. DQL is used to fetch data from the database.

### SELECT

The SELECT statement is used to select data from a database.

The data returned is stored in a result table, called the result-set.

```sql
SELECT column1, column2, ...
FROM table_name;
```

### SELECT DISTINCT

The SELECT DISTINCT statement is used to return only distinct (different) values.

```sql
SELECT DISTINCT column1, column2, ...
FROM table_name;
```

### WHERE

The WHERE clause is used to filter records.

The WHERE clause is used to extract only those records that fulfill a specified condition.

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

### AND, OR and NOT

The WHERE clause can be combined with AND, OR, and NOT operators.

The AND and OR operators are used to filter records based on more than one condition:

- The AND operator displays a record if all the conditions separated by AND are TRUE.
- The OR operator displays a record if any of the conditions separated by OR is TRUE.
- The NOT operator displays a record if the condition(s) is NOT TRUE.

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition1 AND condition2 AND condition3 ...;
```

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition1 OR condition2 OR condition3 ...;
```

```sql
SELECT column1, column2, ...
FROM table_name
WHERE NOT condition;
```

### ORDER BY

The ORDER BY keyword is used to sort the result-set in ascending or descending order.

The ORDER BY keyword sorts the records in ascending order by default. To sort the records in descending order, use the DESC keyword.

```sql
SELECT column1, column2, ...
FROM table_name
ORDER BY column1, column2, ... ASC|DESC;
```

### GROUP BY

The GROUP BY statement groups rows that have the same values into summary rows, like "find the number of customers in each country".
The GROUP BY statement is often used with aggregate functions (COUNT, MAX, MIN, SUM, AVG) to group the result-set by one or more columns.

```sql
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
ORDER BY column_name(s);
```

### HAVING

The HAVING clause was added to SQL because the WHERE keyword could not be used with aggregate functions.

```sql
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
HAVING condition
ORDER BY column_name(s);
```

### LIMIT

The LIMIT clause is used to specify the number of records to return.

```sql
SELECT column_name(s)
FROM table_name
WHERE condition
LIMIT number;
```

### OFFSET

The OFFSET clause specifies the number of rows to skip before starting to return rows from the query.

```sql
SELECT column_name(s)
FROM table_name
WHERE condition
LIMIT number OFFSET offset;
```

### IN

The IN operator allows you to specify multiple values in a WHERE clause.

```sql
SELECT column_name(s)
FROM table_name
WHERE column_name IN (value1, value2, ...);
```

### BETWEEN

The BETWEEN operator selects values within a given range. The values can be numbers, text, or dates.

The BETWEEN operator is inclusive: begin and end values are included.

```sql
SELECT column_name(s)
FROM table_name
WHERE column_name BETWEEN value1 AND value2;
```

### LIKE

The LIKE operator is used in a WHERE clause to search for a specified pattern in a column.

There are two wildcards often used in conjunction with the LIKE operator:

- % - The percent sign represents zero, one, or multiple characters
- \_ - The underscore represents a single character

```sql
SELECT column_name(s)
FROM table_name
WHERE column_name LIKE pattern;
```

### JOIN

A JOIN clause is used to combine rows from two or more tables, based on a related column between them.

```sql
SELECT column_name(s)
FROM table1
INNER JOIN table2
ON table1.column_name = table2.column_name;
```

#### INNER JOIN

The INNER JOIN keyword selects records that have matching values in both tables.

```sql
SELECT column_name(s)
FROM table1
INNER JOIN table2
ON table1.column_name = table2.column_name;
```

#### LEFT JOIN

The LEFT JOIN keyword returns all records from the left table (table1), and the matched records from the right table (table2). The result is NULL from the right side, if there is no match.

```sql
SELECT column_name(s)
FROM table1
LEFT JOIN table2
ON table1.column_name = table2.column_name;
```

#### RIGHT JOIN

The RIGHT JOIN keyword returns all records from the right table (table2), and the matched records from the left table (table1). The result is NULL from the left side, when there is no match.

```sql
SELECT column_name(s)
FROM table1
RIGHT JOIN table2
ON table1.column_name = table2.column_name;
```

#### OUTER JOIN

The OUTER JOIN keyword returns all records when there is a match in left (table1) or right (table2) table records.

```sql
SELECT column_name(s)
FROM table1
FULL OUTER JOIN table2
ON table1.column_name = table2.column_name
WHERE condition;
```

#### LEFT JOIN vs RIGHT JOIN

| LEFT JOIN                                                                                                                                                                          | RIGHT JOIN                                                                                                                                                                         |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| LEFT JOIN returns all records from the left table (table1), and the matched records from the right table (table2). The result is NULL from the right side, when there is no match. | RIGHT JOIN returns all records from the right table (table2), and the matched records from the left table (table1). The result is NULL from the left side, when there is no match. |

### UNION

The UNION operator is used to combine the result-set of two or more SELECT statements.

Each SELECT statement within UNION must have the same number of columns.
The columns must also have similar data types.
The columns in each SELECT statement must also be in the same order.

```sql
SELECT column_name(s) FROM table1
UNION
SELECT column_name(s) FROM table2;
```

### UNION ALL

The UNION ALL operator is used to combine the result-set of two or more SELECT statements.

The UNION ALL operator is faster than the UNION operator, because UNION ALL does not remove duplicate rows.

```sql
SELECT column_name(s) FROM table1
UNION ALL
SELECT column_name(s) FROM table2;
```

### INTERSECT

The INTERSECT operator is used to combine the result-set of two or more SELECT statements.

The INTERSECT operator returns rows that are available in all SELECT statements.

```sql
SELECT column_name(s) FROM table1
INTERSECT
SELECT column_name(s) FROM table2;
```

### EXCEPT

The EXCEPT operator is used to combine the result-set of two or more SELECT statements.

The EXCEPT operator returns the rows that are only in the first SELECT statement but not in the second SELECT statement.

```sql
SELECT column_name(s) FROM table1
EXCEPT
SELECT column_name(s) FROM table2;
```

### ANY

The ANY operator returns true if any of the subquery values meet the condition.

```sql
SELECT column_name(s)
FROM table_name
WHERE column_name operator ANY
(SELECT column_name FROM table_name WHERE condition);
```

### ALL

The ALL operator returns true if all of the subquery values meet the condition.

```sql
SELECT column_name(s)
FROM table_name
WHERE column_name operator ALL
(SELECT column_name FROM table_name WHERE condition);
```

### EXISTS

The EXISTS operator is used to test for the existence of any record in a subquery.

```sql
SELECT column_name(s)
FROM table_name
WHERE EXISTS
(SELECT column_name FROM table_name WHERE condition);
```

### CASE

The CASE statement goes through conditions and returns a value when the first condition is met (like an IF-THEN-ELSE statement).

So, once a condition is true, it will stop reading and return the result.

If no conditions are true, it returns the value in the ELSE clause.

If there is no ELSE part and no conditions are true, it returns NULL.

```sql
SELECT column_name,
CASE
    WHEN condition1 THEN result1
    WHEN condition2 THEN result2
    WHEN conditionN THEN resultN
    ELSE result
END
FROM table_name;
```

[**Go back**](README.md)
