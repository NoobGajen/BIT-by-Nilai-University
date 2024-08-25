# Keys in SQL

### 1. **Primary Key**

**Definition**: A primary key is a column (or a set of columns) in a table that uniquely identifies each row in that table. A table can have only one primary key, and the values in this key must be unique and cannot be NULL.

**Example**: In a `Customers` table, you might use the `CustomerID` column as the primary key to ensure each customer has a unique identifier.

```sql
CREATE TABLE Customers (
    CustomerID INT PRIMARY KEY,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    Email VARCHAR(100)
);
```

### 2. **Foreign Key**

**Definition**: A foreign key is a column (or a set of columns) in one table that creates a link between two tables. It references the primary key in another table, ensuring that the values in the foreign key column match one of the values in the primary key column of the referenced (parent) table. This maintains referential integrity between the two tables.

**Example**: In an `Orders` table, the `CustomerID` column can be a foreign key that links to the `CustomerID` column in the `Customers` table, ensuring that each order is associated with a valid customer.

```sql
CREATE TABLE Orders (
    OrderID INT PRIMARY KEY,
    OrderDate DATE,
    CustomerID INT,
    FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID)
);
```

### 3. **Unique Key**

**Definition**: A unique key ensures that all values in a column (or a set of columns) are unique across the table. Unlike the primary key, a table can have multiple unique keys, and these keys can include NULL values.

**Example**: In the `Customers` table, you might want to ensure that each email address is unique. You can apply a unique key to the `Email` column.

```sql
ALTER TABLE Customers 
ADD CONSTRAINT UQ_Email UNIQUE (Email);
```

### 4. **Candidate Key**

**Definition**: A candidate key is a column (or a set of columns) that can uniquely identify any database record without referring to any other data. A table can have multiple candidate keys, and one of these is selected as the primary key.

**Example**: In an `Employees` table, both `EmployeeID` and `SocialSecurityNumber` could serve as candidate keys because each can uniquely identify an employee. You might choose `EmployeeID` as the primary key and leave `SocialSecurityNumber` as a candidate key.

```sql
CREATE TABLE Employees (
    EmployeeID INT,
    SocialSecurityNumber VARCHAR(11),
    Email VARCHAR(100),
    PRIMARY KEY (EmployeeID),
    UNIQUE (SocialSecurityNumber),
    UNIQUE (Email)
);
```

### 5. **Composite Key**

**Definition**: A composite key is a primary key that consists of two or more columns. It is used when a single column is not sufficient to uniquely identify a record.

**Example**: In a `CourseRegistrations` table, both `StudentID` and `CourseID` together can uniquely identify each record, forming a composite key.

```sql
CREATE TABLE CourseRegistrations (
    StudentID INT,
    CourseID INT,
    RegistrationDate DATE,
    PRIMARY KEY (StudentID, CourseID)
);
```

### 6. **Super Key**

**Definition**: A super key is a set of one or more columns that can uniquely identify a record in a table. It may include additional columns beyond what is necessary for uniqueness, meaning that a super key can be a candidate key plus some extra columns.

**Example**: In a `Products` table, the combination of `ProductID` and `SerialNumber` forms a super key, even though `ProductID` alone could uniquely identify each product. This is because the combination provides more information than necessary to ensure uniqueness.

```sql
CREATE TABLE Products (
    ProductID INT,
    ProductName VARCHAR(100),
    SerialNumber VARCHAR(100),
    PRIMARY KEY (ProductID),
    UNIQUE (ProductID, SerialNumber)
);
```
