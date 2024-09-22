# Data Control Language (DCL)

## Creating a User

#### Syntax

```sql
CREATE USER 'username'@'hostname' IDENTIFIED BY 'password';
```

#### Example

```sql
CREATE USER 'gajen'@'localhost' IDENTIFIED BY 'MySup3rS3cur3P@ssw0rd';
```

* **Command:** Creates a new user.
* **Username:** `gajen`
* **Hostname:** `localhost` (only allows connections from the local machine)
* **Password:** `MySup3rS3cur3P@ssw0rd`

## Granting Privileges

#### Syntax

```sql
GRANT ALL PRIVILEGES ON database_name.* TO 'username'@'hostname';
```

#### Example

```sql
GRANT ALL PRIVILEGES ON database_name.* TO 'gajen'@'localhost';
```

* **Command:** Grants all privileges on a specific database.
* **Database Name:** Replace `database_name` with the actual name of your database.
* **User:** `gajen`
* **Hostname:** `localhost`

## Granting Privileges

#### Syntax

```sql
GRANT privilege1, privilege2, ... ON database_name.* TO 'username'@'hostname' WITH GRANT OPTION;
```

### [Common Privileges: ](https://dev.mysql.com/doc/refman/8.4/en/privileges-provided.html)

1. **ALL PRIVILEGES**: Grants all available privileges.
2. **SELECT**: Allows reading data from a table.
3. **INSERT**: Allows inserting data into a table.
4. **UPDATE**: Allows updating existing data in a table.
5. **DELETE**: Allows deleting data from a table.
6. **CREATE**: Allows creating new databases and tables.
7. **ALTER**: Allows modifying existing databases and tables.
8. **DROP**: Allows deleting databases and tables.
9. **INDEX**: Allows creating and dropping indexes.
10. **REFERENCES**: Allows creating foreign key references.
11. **EXECUTE**: Allows executing stored routines.
12. **CREATE VIEW**: Allows creating views.
13. **SHOW VIEW**: Allows viewing the definition of views.
14. **CREATE ROUTINE**: Allows creating stored routines.
15. **ALTER ROUTINE**: Allows altering stored routines.
16. **EVENT**: Allows creating, altering, and dropping events.
17. **TRIGGER**: Allows creating and dropping triggers.
18. **GRANT OPTION**: Allows the user to grant or revoke privileges to other users.
19. **LOCK TABLES**: Allows locking tables for read or write operations.
20. **RELOAD**: Allows reloading the grant tables and flushing logs.

#### Example

```sql
GRANT CREATE, ALTER, DROP, INSERT, UPDATE, DELETE, SELECT, REFERENCES ON sakila.rental TO 'gajen'@'localhost' WITH GRANT OPTION;
```

* **Command:** Grants all privileges on a specific database.
* **User:** `gajen`
* **Hostname:** `localhost`
* **Privileges:** CREATE, ALTER, DROP, INSERT, UPDATE, DELETE, SELECT, REFERENCES
* **Grant Option:** Allows `gajen` to grant these privileges to other users.

## Granting All Privileges

#### Syntax

```sql
GRANT ALL PRIVILEGES ON *.* TO 'username'@'hostname' WITH GRANT OPTION;
```

#### Example

```sql
GRANT ALL PRIVILEGES ON *.* TO 'gajen'@'localhost' WITH GRANT OPTION;
```

* **Command:** Grants all possible privileges on all databases.
* **User:** `gajen`
* **Hostname:** `localhost`
* **Grant Option:** Allows `gajen` to grant these privileges to other users.

## Revoking Privileges

#### Syntax

```sql
REVOKE type_of_permission ON database_name.table_name FROM 'username'@'hostname';
```

#### Example

```sql
REVOKE CREATE, INSERT, SELECT ON sakila.rental FROM 'gajen'@'localhost';
```

* **Command:** Removes specific privileges from the user.
* **Database Name:** Replace `database_name` with the actual name of your database.
* **Table Name:** Replace `table_name` with the actual name of your table.
* **User:** `gajen`
* **Hostname:** Replace `host` with the actual hostname where the user connects from.

## Listing all users

#### Syntax

```sql
SELECT User, Host FROM mysql.user;
```

* **Command:** Lists all usernames and their corresponding hosts in the MySQL database.

### Here are some useful columns you can include while listing users:

* **`authentication_string`**: Displays the hashed password for the user (if applicable).
* **`select_priv`**: Indicates whether the user has SELECT privileges.
* **`insert_priv`**: Indicates whether the user has INSERT privileges.
* **`update_priv`**: Indicates whether the user has UPDATE privileges.
* **`delete_priv`**: Indicates whether the user has DELETE privileges.
* **`create_priv`**: Indicates whether the user has CREATE privileges.
* **`drop_priv`**: Indicates whether the user has DROP privileges.
* **`grant_priv`**: Indicates whether the user can grant privileges to others.
* **`super_priv`**: Indicates whether the user has superuser privileges.
* **`ssl_type`**: Indicates if the user is required to use SSL for connections.

## Listing User Privileges

#### Syntax

```sql
SHOW GRANTS FOR 'username'@'hostname';
```

#### Example

```sql
SHOW GRANTS FOR 'gajen'@'localhost';
```

* **Command:** Displays all the privileges assigned to the user `gajen`.

## Deleting a User

#### Syntax

```sql
DROP USER 'username'@'hostname';
```

#### Example

```sql
DROP USER 'gajen'@'localhost';
```

* **Command:** Deletes the specified user from the database.
* **User:** `gajen`
* **Hostname:** `localhost`
