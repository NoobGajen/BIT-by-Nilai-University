# Formatting Dates in MySQL

This is a short tutorial on formatting dates in MySQL using the `DATE_FORMAT` function. The key concept to understand is the `Date Format Specifiers` used by the `DATE_FORMAT` function.

To avoid any confusion, let's start from the beginning. You can skip the steps for creating the database and table if you are already familiar with these processes.

### Creating a New Database

```sql
CREATE DATABASE IF NOT EXISTS college_db;
```

This SQL command creates a new database named `college_db` if it does not already exist.

#### Listing Existing Databases

```sql
SHOW DATABASES;
```

This SQL command lists all the existing databases on your MySQL server.

#### Selecting a Database

```sql
USE college_db;
```

This SQL command selects the `college_db` database to work with.

### Creating a New Table

#### Creating a New Table Named 'student'

```sql
CREATE TABLE IF NOT EXISTS student (
    SN INT PRIMARY KEY AUTO_INCREMENT,
    Name VARCHAR(255) NOT NULL,
    Faculty VARCHAR(255) DEFAULT 'Information Technology',
    Address VARCHAR(255) NOT NULL DEFAULT 'Nepal',
    Phone_number VARCHAR(255) UNIQUE,
    Reg_Date TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

This SQL command creates a detailed `student` table with specific attributes and constraints if it does not already exist.

#### Inserting Data

```sql
INSERT INTO student (Name, Faculty, Address, Phone_number) VALUES 
('Gajendra Mahato', 'Information Technology', 'Nepal', '9812345678');
```

This SQL command inserts a new record into the `student` table.

### Performing Date Operations

Now that we have our `student` table and data, let's perform some date operations using the `DATE_FORMAT` function.

#### Formatting Dates

```sql
SELECT Name, DATE_FORMAT(Reg_Date, '%W, %M %d, %Y') AS formatted_date FROM student;
```

<figure><img src=".gitbook/assets/Formatting Dates.png" alt=""><figcaption></figcaption></figure>

This query formats the `Reg_Date` field in `Day of the Week, Month Name, Day, Year` format.

#### Examples of Date Formats Using `DATE_FORMAT` Function

Here are some possible formats you can achieve with the `DATE_FORMAT` function using `Date Format Specifiers`:

```sql
-- YYYY-MM-DD
SELECT Name, DATE_FORMAT(Reg_Date, '%Y-%m-%d') AS formatted_date FROM student;

-- YY-MM-DD
SELECT Name, DATE_FORMAT(Reg_Date, '%y-%m-%d') AS formatted_date FROM student;

-- DD-MM-YYYY
SELECT Name, DATE_FORMAT(Reg_Date, '%d-%m-%Y') AS formatted_date FROM student;

-- DD/MM/YYYY
SELECT Name, DATE_FORMAT(Reg_Date, '%d/%m/%Y') AS formatted_date FROM student;

-- MM-DD-YYYY
SELECT Name, DATE_FORMAT(Reg_Date, '%m-%d-%Y') AS formatted_date FROM student;

-- MM/DD/YYYY
SELECT Name, DATE_FORMAT(Reg_Date, '%m/%d/%Y') AS formatted_date FROM student;

-- YYYY/MM/DD
SELECT Name, DATE_FORMAT(Reg_Date, '%Y/%m/%d') AS formatted_date FROM student;

-- YY/MM/DD
SELECT Name, DATE_FORMAT(Reg_Date, '%y/%m/%d') AS formatted_date FROM student;

-- Full Date and Time
SELECT Name, DATE_FORMAT(Reg_Date, '%Y-%m-%d %H:%i:%s') AS formatted_date FROM student;

-- 12-Hour Time with AM/PM
SELECT Name, DATE_FORMAT(Reg_Date, '%Y-%m-%d %r') AS formatted_date FROM student;

-- Day of the Week, Month Name, Day, Year
SELECT Name, DATE_FORMAT(Reg_Date, '%W, %M %d, %Y') AS formatted_date FROM student;

-- Day-Month-Year with Full Month Name
SELECT Name, DATE_FORMAT(Reg_Date, '%d-%M-%Y') AS formatted_date FROM student;

-- Month-Day-Year with Full Month Name
SELECT Name, DATE_FORMAT(Reg_Date, '%M-%d-%Y') AS formatted_date FROM student;

-- Day-Month-Year with Abbreviated Month Name
SELECT Name, DATE_FORMAT(Reg_Date, '%d-%b-%Y') AS formatted_date FROM student;

-- Month-Day-Year with Abbreviated Month Name
SELECT Name, DATE_FORMAT(Reg_Date, '%b-%d-%Y') AS formatted_date FROM student;

-- Year, Full Month Name, Day
SELECT Name, DATE_FORMAT(Reg_Date, '%Y %M %d') AS formatted_date FROM student;

-- Year, Abbreviated Month Name, Day
SELECT Name, DATE_FORMAT(Reg_Date, '%Y %b %d') AS formatted_date FROM student;

-- Day, Full Month Name, Year
SELECT Name, DATE_FORMAT(Reg_Date, '%d %M %Y') AS formatted_date FROM student;

-- Day, Abbreviated Month Name, Year
SELECT Name, DATE_FORMAT(Reg_Date, '%d %b %Y') AS formatted_date FROM student;

-- Month Name, Day, Year
SELECT Name, DATE_FORMAT(Reg_Date, '%M %d, %Y') AS formatted_date FROM student;

-- Abbreviated Month Name, Day, Year
SELECT Name, DATE_FORMAT(Reg_Date, '%b %d, %Y') AS formatted_date FROM student;

-- Month/Day/Year
SELECT Name, DATE_FORMAT(Reg_Date, '%c/%e/%Y') AS formatted_date FROM student;

-- Day/Month/Year
SELECT Name, DATE_FORMAT(Reg_Date, '%e/%c/%Y') AS formatted_date FROM student;

-- Year-Month-Day Hour:Minute
SELECT Name, DATE_FORMAT(Reg_Date, '%Y-%m-%d %H:%i') AS formatted_date FROM student;

-- Hour:Minute:Second
SELECT Name, DATE_FORMAT(Reg_Date, '%H:%i:%s') AS formatted_date FROM student;

-- Hour:Minute AM/PM
SELECT Name, DATE_FORMAT(Reg_Date, '%h:%i %p') AS formatted_date FROM student;

-- Day of the Month with Suffix
SELECT Name, DATE_FORMAT(Reg_Date, '%D %M %Y') AS formatted_date FROM student;

-- ISO 8601 Date
SELECT Name, DATE_FORMAT(Reg_Date, '%Y-%m-%dT%H:%i:%s') AS formatted_date FROM student;

-- Unix Timestamp
SELECT Name, UNIX_TIMESTAMP(Reg_Date) AS formatted_date FROM student;
```

### Date Format Specifiers in MySQL

Here are some possible formats you we achieve with the `DATE_FORMAT` function using `Date Format Specifiers`

| Format | Description                                                                  | Example                                                                    |
| ------ | ---------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| `%a`   | Abbreviated weekday name (Sun to Sat)                                        | `SELECT DATE_FORMAT('2024-07-28', '%a');` returns `Sun`                    |
| `%b`   | Abbreviated month name (Jan to Dec)                                          | `SELECT DATE_FORMAT('2024-07-28', '%b');` returns `Jul`                    |
| `%c`   | Numeric month name (0 to 12)                                                 | `SELECT DATE_FORMAT('2024-07-28', '%c');` returns `7`                      |
| `%D`   | Day of the month as a numeric value, followed by suffix (1st, 2nd, 3rd, ...) | `SELECT DATE_FORMAT('2024-07-28', '%D');` returns `28th`                   |
| `%d`   | Day of the month as a numeric value (01 to 31)                               | `SELECT DATE_FORMAT('2024-07-28', '%d');` returns `28`                     |
| `%e`   | Day of the month as a numeric value (0 to 31)                                | `SELECT DATE_FORMAT('2024-07-28', '%e');` returns `28`                     |
| `%f`   | Microseconds (000000 to 999999)                                              | `SELECT DATE_FORMAT('2024-07-28 12:34:56.789123', '%f');` returns `789123` |
| `%H`   | Hour (00 to 23)                                                              | `SELECT DATE_FORMAT('2024-07-28 14:34:56', '%H');` returns `14`            |
| `%h`   | Hour (00 to 12)                                                              | `SELECT DATE_FORMAT('2024-07-28 14:34:56', '%h');` returns `02`            |
| `%I`   | Hour (00 to 12)                                                              | `SELECT DATE_FORMAT('2024-07-28 14:34:56', '%I');` returns `02`            |
| `%i`   | Minutes (00 to 59)                                                           | `SELECT DATE_FORMAT('2024-07-28 14:34:56', '%i');` returns `34`            |
| `%j`   | Day of the year (001 to 366)                                                 | `SELECT DATE_FORMAT('2024-07-28', '%j');` returns `210`                    |
| `%k`   | Hour (0 to 23)                                                               | `SELECT DATE_FORMAT('2024-07-28 14:34:56', '%k');` returns `14`            |
| `%l`   | Hour (1 to 12)                                                               | `SELECT DATE_FORMAT('2024-07-28 14:34:56', '%l');` returns `2`             |
| `%M`   | Month name in full (January to December)                                     | `SELECT DATE_FORMAT('2024-07-28', '%M');` returns `July`                   |
| `%m`   | Month name as a numeric value (00 to 12)                                     | `SELECT DATE_FORMAT('2024-07-28', '%m');` returns `07`                     |
| `%p`   | AM or PM                                                                     | `SELECT DATE_FORMAT('2024-07-28 14:34:56', '%p');` returns `PM`            |
| `%r`   | Time in 12-hour AM or PM format (hh:mm:ss AM/PM)                             | `SELECT DATE_FORMAT('2024-07-28 14:34:56', '%r');` returns `02:34:56 PM`   |
| `%S`   | Seconds (00 to 59)                                                           | `SELECT DATE_FORMAT('2024-07-28 14:34:56', '%S');` returns `56`            |
| `%s`   | Seconds (00 to 59)                                                           | `SELECT DATE_FORMAT('2024-07-28 14:34:56', '%s');` returns `56`            |
| `%T`   | Time in 24-hour format (hh:mm:ss)                                            | `SELECT DATE_FORMAT('2024-07-28 14:34:56', '%T');` returns `14:34:56`      |
| `%U`   | Week where Sunday is the first day of the week (00 to 53)                    | `SELECT DATE_FORMAT('2024-07-28', '%U');` returns `30`                     |
| `%u`   | Week where Monday is the first day of the week (00 to 53)                    | `SELECT DATE_FORMAT('2024-07-28', '%u');` returns `30`                     |
| `%V`   | Week where Sunday is the first day of the week (01 to 53). Used with %X      | `SELECT DATE_FORMAT('2024-07-28', '%V');` returns `30`                     |
| `%v`   | Week where Monday is the first day of the week (01 to 53). Used with %x      | `SELECT DATE_FORMAT('2024-07-28', '%v');` returns `30`                     |
| `%W`   | Weekday name in full (Sunday to Saturday)                                    | `SELECT DATE_FORMAT('2024-07-28', '%W');` returns `Sunday`                 |
| `%w`   | Day of the week where Sunday=0 and Saturday=6                                | `SELECT DATE_FORMAT('2024-07-28', '%w');` returns `0`                      |
| `%X`   | Year for the week where Sunday is the first day of the week. Used with %V    | `SELECT DATE_FORMAT('2024-07-28', '%X');` returns `2024`                   |
| `%x`   | Year for the week where Monday is the first day of the week. Used with %v    | `SELECT DATE_FORMAT('2024-07-28', '%x');` returns `2024`                   |
| `%Y`   | Year as a numeric, 4-digit value                                             | `SELECT DATE_FORMAT('2024-07-28', '%Y');` returns `2024`                   |
| `%y`   | Year as a numeric, 2-digit value                                             | `SELECT DATE_FORMAT('2024-07-28', '%y');` returns `24`                     |

For more information, please refer to the [W3Schools tutorial on MySQL DATE\_FORMAT](https://www.w3schools.com/sql/func\_mysql\_date\_format.asp).
