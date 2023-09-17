# Data Definition Language (DDL)

## Table of contents

- [Data Definition Language (DDL)](#data-definition-language-ddl)
  - [Table of contents](#table-of-contents)
  - [DDL](#ddl)
    - [CREATE DATABASE](#create-database)
    - [DROP DATABASE](#drop-database)
    - [CREATE TABLE](#create-table)
      - [Data types](#data-types)
    - [ALTER TABLE](#alter-table)
    - [RENAME TABLE](#rename-table)
    - [DROP TABLE](#drop-table)
    - [CREATE INDEX](#create-index)
    - [DROP INDEX](#drop-index)
    - [TRUNCATE TABLE](#truncate-table)
    - [PRIMARY KEY](#primary-key)
    - [FOREIGN KEY](#foreign-key)
    - [AUTO INCREMENT](#auto-increment)
    - [CHECK](#check)
    - [DEFAULT](#default)
    - [UNIQUE](#unique)
    - [NOT NULL](#not-null)

## DDL

DDL stands for Data Definition Language. DDL is used to create and modify the structure of database objects in database.

### CREATE DATABASE

The CREATE DATABASE statement is used to create a new database.

```sql
CREATE DATABASE database_name;
```

### DROP DATABASE

The DROP DATABASE statement is used to drop an existing database.

```sql
DROP DATABASE database_name;
```

### CREATE TABLE

The CREATE TABLE statement is used to create a new table in a database.

```sql
CREATE TABLE table_name (
  column1 datatype,
  column2 datatype,
  column3 datatype,
  ...
);
```

#### Data types

| Data type | Description |
| --------- | ----------- |
| INT       | Integer     |
| VARCHAR   | String      |
| DATE      | Date        |
| DECIMAL   | Decimal     |
| BLOB      | Binary      |
| TEXT      | Text        |

### ALTER TABLE

The ALTER TABLE statement is used to add, delete, or modify columns in an existing table.

```sql
ALTER TABLE table_name
ADD column_name datatype;

ALTER TABLE table_name
DROP COLUMN column_name;

ALTER TABLE table_name
MODIFY COLUMN column_name datatype;
```

### RENAME TABLE

The RENAME TABLE statement is used to rename an existing table in a database.

```sql
RENAME TABLE table_name TO new_table_name;
```

### DROP TABLE

The DROP TABLE statement is used to drop an existing table in a database.

```sql
DROP TABLE table_name;
```

### CREATE INDEX

The CREATE INDEX statement is used to create indexes in tables, which can be used to locate rows with specific column values quickly.

```sql
CREATE INDEX index_name
ON table_name (column1, column2, ...);
```

### DROP INDEX

The DROP INDEX statement is used to delete an index in a table.

```sql
DROP INDEX index_name
ON table_name;
```

### TRUNCATE TABLE

The TRUNCATE TABLE statement is used to delete the data inside a table, but not the table itself.

```sql
TRUNCATE TABLE table_name;
```

### PRIMARY KEY

The PRIMARY KEY constraint uniquely identifies each record in a table.

```sql
CREATE TABLE table_name (
  column1 datatype NOT NULL,
  column2 datatype NOT NULL,
  column3 datatype NOT NULL,
  ...
  PRIMARY KEY (one or more columns)
);
```

### FOREIGN KEY

A FOREIGN KEY is a key used to link two tables together.

A FOREIGN KEY is a field (or collection of fields) in one table that refers to the PRIMARY KEY in another table.

```sql
CREATE TABLE table_name1 (
  column1 datatype NOT NULL,
  column2 datatype,
  column3 datatype,
  ...
  PRIMARY KEY (one or more columns)
);

CREATE TABLE table_name2 (
  column1 datatype NOT NULL,
  column2 datatype,
  column3 datatype,
  ...
  FOREIGN KEY (column1, column2, ... column_n)
  REFERENCES table_name1 (column1, column2, ... column_n)
);
```

### AUTO INCREMENT

Auto-increment allows a unique number to be generated automatically when a new record is inserted into a table.

```sql
CREATE TABLE table_name (
  column1 datatype AUTO_INCREMENT,
  column2 datatype,
  column3 datatype,
  ...
);
```

### CHECK

The CHECK constraint is used to limit the value range that can be placed in a column.

```sql
CREATE TABLE table_name (
  column1 datatype CHECK (condition),
  column2 datatype,
  column3 datatype,
  ...
);
```

### DEFAULT

The DEFAULT constraint is used to provide a default value for a column.

```sql

CREATE TABLE table_name (
  column1 datatype DEFAULT default_value,
  column2 datatype,
  column3 datatype,
  ...
);
```

### UNIQUE

The UNIQUE constraint ensures that all values in a column are different.

Both the UNIQUE and PRIMARY KEY constraints provide a guarantee for uniqueness for a column or set of columns.

```sql
CREATE TABLE table_name (
  column1 datatype UNIQUE,
  column2 datatype,
  column3 datatype,
  ...
);
```

### NOT NULL

The NOT NULL constraint enforces a column to NOT accept NULL values.

```sql
CREATE TABLE table_name (
  column1 datatype NOT NULL,
  column2 datatype,
  column3 datatype,
  ...
);
```

[**Go back**](README.md)
