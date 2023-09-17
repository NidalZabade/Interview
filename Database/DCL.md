# DATA CONTROL LANGUAGE (DCL)

## Table of contents

- [DATA CONTROL LANGUAGE (DCL)](#data-control-language-dcl)
  - [Table of contents](#table-of-contents)
  - [DCL](#dcl)
    - [GRANT](#grant)
    - [REVOKE](#revoke)

## DCL

Data Control Language (DCL) is a subset of SQL statements that enable database administrators to control access to the database. These statements are used to grant database access privileges to users and roles. They are also used to revoke privileges previously granted to users and roles.

### GRANT

The GRANT statement is used to give user access privileges to a database.

```sql
GRANT privilege_name
ON object_name
TO {user_name |PUBLIC |role_name}
[WITH GRANT OPTION];
```

### REVOKE

The REVOKE statement is used to remove user access privileges to a database.

```sql
REVOKE privilege_name
ON object_name
FROM {user_name |PUBLIC |role_name};
```

[**Go back**](../README.md)
