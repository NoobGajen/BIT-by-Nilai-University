# Demonstrating ORDER BY Operations for Various Data Types in MySQL

This is a small demonstration of `ORDER BY` operations for each data type to achieve our desired results. So let's start from the beginning to avoid any sort of confusion.

We are creating the table with attributes using various unrelated data types for experimental purposes. Please do not consider this approach for real-life scenarios or in a production server.

### Creating the Database and Table

```sql
-- Creating a new database
CREATE DATABASE IF NOT EXISTS school_db;
USE school_db;

-- Creating the student_marks table with various data types
CREATE TABLE IF NOT EXISTS student_marks (
    Roll_number INT PRIMARY KEY,
    Name VARCHAR(255) NOT NULL,
    English_mark VARCHAR(255),
    Nepali_mark FLOAT,
    Math_mark DECIMAL(5,0),
    Social_mark CHAR(2)
);
```

### Inserting Data

```sql
INSERT INTO student_marks (Roll_number, Name, English_mark, Nepali_mark, Math_mark, Social_mark) VALUES
(1, 'Sandesh Paudel', "85", 78, 92, '88'),
(2, 'Diwash Bist', 72, "83", '75', 80),
(3, 'Gajendra Mahato', 65, 70, "60", '62'),
(4, 'AniKet Mulguthi', "90", '88', 95, '93'),
(5, 'Rakesh Rai', 55, "60", 50, '58');
```

### Ordering by Attributes

**Ordering by `Name` with `VARCHAR` DataType**

```sql
-- Order by Name in ascending order
SELECT * FROM student_marks ORDER BY Name ASC;

-- Order by Name in descending order
SELECT * FROM student_marks ORDER BY Name DESC;
```

**Ordering by `Roll_number` with `INT` DataType**

```sql
-- Order by Roll_number in ascending order
SELECT * FROM student_marks ORDER BY Roll_number ASC;

-- Order by Roll_number in descending order
SELECT * FROM student_marks ORDER BY Roll_number DESC;
```

**Ordering by `English_mark` with `VARCHAR` DataType**

```sql
-- Order by English_mark in ascending order
SELECT * FROM student_marks ORDER BY English_mark ASC;

-- Order by English_mark in descending order
SELECT * FROM student_marks ORDER BY English_mark DESC;
```

**Ordering by `Nepali_mark` with `FLOAT` DataType**

```sql
-- Order by Nepali_mark in ascending order
SELECT * FROM student_marks ORDER BY Nepali_mark ASC;

-- Order by Nepali_mark in descending order
SELECT * FROM student_marks ORDER BY Nepali_mark DESC;
```

**Ordering by `Math_mark` with `DECIMAL` DataType**

```sql
-- Order by Math_mark in ascending order
SELECT * FROM student_marks ORDER BY Math_mark ASC;

-- Order by Math_mark in descending order
SELECT * FROM student_marks ORDER BY Math_mark DESC;
```

**Ordering by `Social_mark` with `CHAR` DataType**

```sql
-- Order by Social_mark in ascending order
SELECT * FROM student_marks ORDER BY Social_mark ASC;

-- Order by Social_mark in descending order
SELECT * FROM student_marks ORDER BY Social_mark DESC;
```
