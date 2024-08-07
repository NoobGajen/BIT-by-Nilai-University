# Comprehensive Guide for Creating and Managing Databases and Tables in MySQL

## Introduction to MySQL

MySQL is an open-source relational database management system (RDBMS) based on Structured Query Language (SQL). It is widely used for managing and organizing data due to its reliability, ease of use, and support for various programming languages. MySQL is commonly used in web applications and is an essential component of the LAMP (Linux, Apache, MySQL, PHP/Python/Perl) stack.

## Constraints in MySQL

Constraints are rules applied to columns in a table to ensure the validity and integrity of the data. Common constraints include:

* **NOT NULL**: Ensures that a column cannot have a NULL value.
* **UNIQUE**: Ensures that all values in a column are unique.
* **PRIMARY KEY**: Uniquely identifies each record in a table.
* **FOREIGN KEY**: Ensures the referential integrity of the data in one table to match values in another table.
* **CHECK**: Ensures that the value in a column meets a specific condition.
* **DEFAULT**: Sets a default value for a column if no value is specified.

***

## Data Definition Language (DDL)

DDL is a subset of SQL commands used to define and manage the structure of database objects such as tables, indexes, and schemas. DDL commands are responsible for creating, altering, and deleting the structure of database objects.

* **Examples**:
  * `CREATE`: Creates new tables, indexes, or databases.
  * `ALTER`: Modifies existing database objects.
  * `DROP`: Deletes database objects.
  * `TRUNCATE`: Removes all records from a table but keep the table structure.

### 1.1 Creating a New Database

```sql
CREATE DATABASE college_db;
```

* This SQL command creates a new database named `college_db`.

### 1.2 Listing Existing Databases

```sql
SHOW DATABASES;
```

* This SQL command lists all the existing databases in your MySQL server.

### 1.3 Selecting a Database

```sql
USE college_db;
```

* This SQL command selects the `college_db` database to work with.

### 1.4 Creating a New Table

#### 1.4.1 Creating a New Table Named 'student'

```sql
CREATE TABLE student (
    SN INT PRIMARY KEY AUTO_INCREMENT,
    Name VARCHAR(255) NOT NULL,
    Faculty VARCHAR(255) DEFAULT 'Information Technology',
    Address VARCHAR(255) NOT NULL DEFAULT 'Nepal',
    Phone_number VARCHAR(255) UNIQUE,
    Reg_Date TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

* This SQL command creates a detailed `student` table with specific attributes and constraints.

### 1.5 Listing Tables in the Current Database

```sql
SHOW TABLES;
```

* This SQL command lists all the tables in

the currently selected database.

### 1.6 Describing Tables in the Current Database

```sql
DESCRIBE student;
-- OR,
DESC student;
```

This SQL command provides a detailed description of the `student` table, including column names, data types, constraints, and default values. where,

* **Field**: The name of the column.
* **Type**: The data type of the column.
* **Null**: Whether the column can contain NULL values (`YES` or `NO`).
* **Key**: Key constraints (e.g., `PRI` for primary key, `UNI` for unique key).
* **Default**: The default value for the column, if any.
* **Extra**: Any additional information about the column (e.g., `auto_increment` for automatically incrementing numbers).

### 1.7 Adding Multiple Attributes to an Existing Table

```sql
ALTER TABLE student
    ADD Email VARCHAR(255),
    ADD Age INT CHECK (Age > 16);
```

* `Email`: A `VARCHAR` column with a maximum length of 255 characters.
* `Age`: An `INT` column with a `CHECK` constraint to ensure that the age value is greater than 16.

### 1.8 Adding Multiple Attributes to an Existing Table by Specifying a Attribute/Column's Place

```sql
ALTER TABLE student
    ADD Roll_no VARCHAR(3) AFTER Name,
    ADD Section VARCHAR(3) DEFAULT 'A' AFTER Faculty;
```

* `Roll_no`: A `VARCHAR(3)` column added after the `Name` column.
* `Section`: A `VARCHAR(3)` column with a default value of `'A'`, added after the `Faculty` column.

### 1.9 Dropping Attributes from a Table

```sql
ALTER TABLE student DROP COLUMN Email;
-- OR,
ALTER TABLE student DROP Email;
```

* This SQL command removes the `Email` column from the `student` table.

### 1.10 Renaming Attributes in a Table

```sql
ALTER TABLE student CHANGE COLUMN Roll_no Roll_number VARCHAR(255);
-- OR,
ALTER TABLE student CHANGE Roll_no Roll_number VARCHAR(255);
-- OR,
ALTER TABLE student RENAME COLUMN Roll_no TO Roll_number;
```

* These SQL command change/rename the `Roll_no` column to `Roll_number` and keeps the data type as `VARCHAR(255)`.

### 1.11 Changing Data Types of Attributes in a Table

```sql
ALTER TABLE student MODIFY COLUMN Phone_number BIGINT;
-- OR,
ALTER TABLE student MODIFY Phone_number BIGINT;
```

* This SQL command changes the data type of the `Phone_number` column to `BIGINT`.

### 1.12 Creating a New Table by Copying Data and Structure

The `CREATE TABLE ... AS SELECT` command allows you to create a new table by copying both the structure and the data from an existing table. This approach is useful when you need to duplicate data, create a similar table for further processing, or work with a subset of data from an existing table.

#### 1.12.1 Creating the `person` Table

To create a new table named `person` with the same structure and data as the `student` table, use the following SQL command:

```sql
CREATE TABLE person AS 
SELECT * FROM student;
```

* `CREATE TABLE person AS` specifies the creation of a new table called `person`.
* `SELECT * FROM student` selects all columns and rows from the `student` table.
* The new `person` table will inherit the entire column structure and all data from the `student` table.

#### 1.12.2 Creating a Table from a Table in Another Database

If you want to create a table in the current database by copying data from a table in another database, use the following SQL command:

```sql
CREATE TABLE teacher AS 
SELECT * FROM school.teacher;
```

* `CREATE TABLE teacher AS` specifies the creation of a new table named `teacher` in the current database.
* `SELECT * FROM school.teacher` selects all columns and rows from the `teacher` table located in the `school` database.
* The new `teacher` table will inherit the column structure and all data from the `school.teacher` table.

#### 1.12.3 Verifying the New Table

After executing the command, you should verify that the new table has been created correctly and contains the expected data:

**Check the Structure of the New Table**:

```sql
DESC person;
```

or

```sql
DESC teacher;
```

* `DESC person;` or `DESC teacher;` describes the structure of the table, including column names and data types.

**View the First Few Records in the New Table**:

```sql
SELECT * FROM person LIMIT 10;
```

or

```sql
SELECT * FROM teacher LIMIT 10;
```

* `SELECT * FROM person LIMIT 10;` or `SELECT * FROM teacher LIMIT 10;` retrieves the first 10 rows from the table to confirm that the data was copied correctly.

### 1.13 Dropping/Deleting Tables

```sql
DROP TABLE student;
```

* This SQL command deletes the `student` table from the database.

### 1.14 Dropping/Deleting Databases

```sql
DROP DATABASE college_db;
```

* This SQL command deletes the `college_db` database and all its tables.

### 1.15 Truncate Table

```sql
TRUNCATE TABLE student;
```

* This SQL command removes all rows from the `student` table, effectively resetting it without deleting the table structure.

***

## Data Manipulation Language (DML)

DML is a subset of SQL commands used to manage and manipulate data within database objects. DML commands allow for the retrieval, insertion, updating, and deletion of data in a database.

* **Examples**:
  * `INSERT`: Adds new data to a table.
  * `SELECT`: Retrieves data from the database.
  * `UPDATE`: Modifies existing data in a table.
  * `DELETE`: Removes data from a table.

### 2.1 Inserting Record/Data (`INSERT`)

#### 2.1.1 Inserting a Single Record/Data

```sql
INSERT INTO student (Name, Faculty, Address, Phone_number) VALUES 
('Diwash Bist', 'Information Technology', 'Nepal', '9812131416');
```

* This command adds a single row to the `student` table with the specified values for the `Name`, `Faculty`, `Address`, and `Phone_number` columns.

#### 2.1.2 Inserting a Multiple Records/Datas

```sql
INSERT INTO student (Name, Faculty, Address, Phone_number) VALUES 
('Gajendra Mahato', 'Information Systems', 'Nepal', '9812345678'),
('Sandesh Paudel', 'Computer Engineering', 'United Kingdom', '4453678874'),
('Aniket Mulguthi', 'Software Engineering', 'Japan', '8126489760');
```

* This command adds three rows to the `student` table with the specified values for each record. Each record is enclosed in parentheses and separated by commas.

### 2.2 Selecting Record/Data (`SELECT`)

#### 2.2.1 Selecting All Columns

```sql
SELECT * FROM student;
```

* This SQL command retrieves all columns and rows from the `student` table.

#### 2.2.2 Selecting Specific Columns

```sql
SELECT Name, Faculty FROM student;
```

* This SQL command retrieves the `Name` and `Faculty` columns from the `student` table.

#### 2.2.3 Select with Filtering

**2.2.3.1 Using `WHERE`**

The `WHERE` clause is used to filter records based on a specified condition.

```sql
SELECT * FROM student WHERE Address = 'Nepal';
```

* This command selects all columns from the `student` table where the `Address` is 'Nepal'.

**2.2.3.2 Using `AND`**

The `AND` operator is used to filter records based on multiple conditions.

```sql
SELECT * FROM student WHERE Address = 'Nepal' AND Faculty = 'Information Technology';
```

* This command selects all columns from the `student` table where the `Address` is 'Nepal' and the `Faculty` is 'Information Technology'.

**2.2.3.3 Using `OR`**

The `OR` operator is used to filter records where at least one of the conditions is true.

```sql
SELECT * FROM student WHERE Address = 'Nepal' OR Faculty = 'Computer Engineering';
```

* This command selects all columns from the `student` table where either the `Address` is 'Nepal' or the `Faculty` is 'Computer Engineering'.

**2.2.3.4 Using `NOT`**

The `NOT` operator is used to filter records that do not match the specified condition.

```sql
SELECT * FROM student WHERE NOT Address = 'Nepal';
```

* This command selects all columns from the `student` table where the `Address` is not 'Nepal'.

**2.2.3.5 Using `BETWEEN`**

The `BETWEEN` operator is used to filter records within a certain range. It can be used for numbers, text, or dates.

```sql
SELECT * FROM student WHERE SN BETWEEN 2 AND 4;
```

* This command selects all columns from the `student` table where the `SN` is between 2 and 4.

**2.2.3.6 Using `LIKE`**

The `LIKE` operator is used for pattern matching in strings.

```sql
SELECT * FROM student WHERE Name LIKE 'G%';
```

* This command selects all columns from the `student` table where the `Name` starts with 'G'.

**2.2.3.7 Using Wildcards with `LIKE`**

Wildcards are used with the `LIKE` operator to perform pattern matching. Common wildcards include:

* `%` (percent sign) - represents zero or more characters
* `_` (underscore) - represents a single character

```sql
SELECT * FROM student WHERE Name LIKE 'S_____h%';
```

* This command selects all columns from the `student` table where the `Name` starts with 'S', has any 5 characters in the next position, and follows with any sequence of characters.

### 2.3 Updating Data

```sql
UPDATE student
SET Address = 'Lalitpur'
WHERE Name = 'Gajendra Mahato';
```

* This SQL command updates the `Address` column to 'Lalitpur' for the row where the `Name` is 'Gajendra Mahato'.

### 2.4 Deleting Data

```sql
DELETE FROM student
WHERE Address = 'Japan';
```

* This SQL command deletes rows from the `student` table where the `Address` is `Japan`.

### 2.5 Locking Tables

#### 2.5.1 Putting Tables into Read-Only Mode

```sql
LOCK TABLES student READ;
```

* This SQL command locks the `student` table in read-only mode, preventing write operations.

#### 2.5.2 Returning Tables to Write Mode

```sql
UNLOCK TABLES;
```

* This SQL command unlocks the `student` table, allowing write operations again.

#### 2.5.3 Checking if Tables are Locked

```sql
SHOW OPEN TABLES WHERE In_use > 0;
```

* This SQL command lists tables that are currently locked.

## Important SQL Commands

### 💚 Create a Table

First, create a table with necessary attributes. For example, we'll create an `employee` table.

```sql
CREATE TABLE employee (
    id INT AUTO_INCREMENT PRIMARY KEY,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    position VARCHAR(50) DEFAULT 'Employee',
    salary DECIMAL(10, 2) DEFAULT 0.00,
    hire_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### 💚 Insert Data

Insert at least 5 rows of data into the `employee` table.

```sql
INSERT INTO employee (first_name, last_name, position, salary, hire_date) VALUES
('Sandesh', 'Paudel', 'Software Engineer', 75000, '2022-01-15'),
('Santosh', 'Karki', 'Project Manager', 85000, '2021-03-22'),
('Diwash', 'Bist', 'Data Analyst', 72000, '2023-07-09'),
('Gajendra', 'Mahato', 'DevOps Engineer', 80000, '2022-11-01'),
('Shimant', 'Bhattarai', 'UX Designer', 67000, '2021-05-30');
```

### 💚 Select Data

Retrieve data from the `employee` table.

```sql
SELECT * FROM employee;
```

To filter data, use the `WHERE` clause.

```sql
SELECT * FROM employee WHERE position = 'Software Engineer';
```

To sort data, use `ORDER BY`.

```sql
SELECT * FROM employee ORDER BY salary DESC;
```

### 💚 Update Data

Update existing records in the `employee` table.

```sql
UPDATE employee
SET salary = 78000
WHERE id = 1;
```

### 💚 Delete Data

Remove records from the `employee` table.

```sql
DELETE FROM employee
WHERE id = 5;
```

### 💚 Alter Table

Modify the `employee` table structure. For example, add a new column `email`.

```sql
ALTER TABLE employee
ADD COLUMN email VARCHAR(100);
```

### 💚 Drop Table

Remove the `employee` table from the database.

```sql
DROP TABLE employee;
```
