# Data Manipulation Language (DML)

## Table of contents

- [Data Manipulation Language (DML)](#data-manipulation-language-dml)
  - [Table of contents](#table-of-contents)
  - [DML](#dml)
    - [INSERT](#insert)
    - [UPDATE](#update)
    - [DELETE](#delete)

## DML

DML stands for Data Manipulation Language. DML is used to retrieve, store, modify, delete, insert and update data in database.

### INSERT

The INSERT INTO statement is used to insert new records in a table.

```sql
INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);
```

or insert a bulk of records

```sql
INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...),
       (value1, value2, value3, ...),
       (value1, value2, value3, ...),
       ...
```

### UPDATE

The UPDATE statement is used to modify the existing records in a table.

```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

### DELETE

The DELETE statement is used to delete existing records in a table.

```sql
DELETE FROM table_name
WHERE condition;
```

[**Go back**](README.md)

