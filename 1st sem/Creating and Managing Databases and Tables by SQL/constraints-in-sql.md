# Constraints in SQL

Constraints are rules applied to columns in a table to ensure the accuracy, validity, and integrity of the data stored within a database. They enforce certain conditions on the data, preventing invalid entries and maintaining consistency across the database. By using constraints, we can define the specific properties of the data that can be stored, ensuring that the database operates reliably and according to the intended design.

Constraints can be broadly categorized into 2 types:

1.  [Key Constraints](constraints-in-sql.md#id-1.-key-constraints)

    Key Constraints are rules applied to columns in a database table to enforce the uniqueness and integrity of data. They ensure that each record can be uniquely identified and that relationships between different tables are properly maintained.
2.  [Domain Constraints](constraints-in-sql.md#id-2.-domain-constraints)

    Domain Constraints are rules applied to columns to restrict the type, format, and range of data that can be entered. They ensure that the data stored in the column meets specific criteria and fits defined standards.

## 1.) Key Constraints

Key Constraints are rules applied to columns in a database table to enforce the uniqueness and integrity of data. They ensure that each record can be uniquely identified and that relationships between different tables are properly maintained.

### Type of Key Constraints:

<figure><img src=".gitbook/assets/Types of Keys in SQL.png" alt=""><figcaption></figcaption></figure>

### 1. **Primary Key**

A primary key is a column (or a set of columns) in a table that uniquely identifies each row in that table. A table can have only one primary key, and the values in this key must be unique and cannot be NULL.

**Characteristics:**

* **Uniqueness**: Ensures that no two rows can have the same primary key value.
* **Non-nullable**: Cannot contain NULL values.
* **Immutable**: Should not change once set; ideally, its value remains constant.
* **Single-column or Composite**: Can be a single column or a combination of multiple columns (composite key).

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

A foreign key is a column (or a set of columns) in one table that creates a link between two tables. It references the primary key in another table, ensuring that the values in the foreign key column match one of the values in the primary key column of the referenced (parent) table. This maintains referential integrity between the two tables.

**Characteristics:**

* **Establishes Relationships**: Creates a link between two tables, enforcing referential integrity.
* **Referential Integrity**: Ensures that values in the foreign key column match values in the primary key column of another table.
* **Nullable**: Can contain NULL values, unless explicitly restricted.
* **Non-unique**: Can have duplicate values.

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

A unique key ensures that all values in a column (or a set of columns) are unique across the table. Unlike the primary key, a table can have multiple unique keys, and these keys can include NULL values (depending on the SQL implementation).

**Characteristics:**

* **Uniqueness**: Ensures that all values in the unique key column(s) are unique across the table.
* **Nullable**: Can contain NULL values (subject to specific SQL implementations; some databases might allow multiple NULLs).
* **Single-column or Composite**: Can be a single column or a combination of multiple columns.
* **Non-primary**: Unlike primary keys, a table can have multiple unique keys.

**Example**: In the `Customers` table, you might want to ensure that each email address is unique. You can apply a unique key to the `Email` column.

```sql
CREATE TABLE Customers (
    CustomerName VARCHAR(100),      -- Regular column for customer name
    Email VARCHAR(100) UNIQUE       -- Unique Key: Ensures all email addresses are unique
);
```

### 4. **Composite Key**

A composite key is a primary key that consists of two or more columns. It is used when a single column is not sufficient to uniquely identify a record.

**Characteristics:**

* **Uniqueness**: Ensures that the combination of multiple columns uniquely identifies a record.
* **Non-nullable**: Each column in the composite key should not contain NULL values to maintain uniqueness.
* **Multiple Columns**: Consists of two or more columns.
* **Used When**: A single column is insufficient to uniquely identify records.

**Example**: In a `CourseRegistrations` table, both `StudentID` and `CourseID` together can uniquely identify each record, forming a composite key.

```sql
CREATE TABLE CourseRegistrations (
    StudentID INT,
    CourseID INT,
    RegistrationDate DATE,
    PRIMARY KEY (StudentID, CourseID)      -- Composite Key: (combination of StudentID, CourseID)
);
```

### 5. **Super Key**

<figure><img src=".gitbook/assets/Super Key.png" alt=""><figcaption></figcaption></figure>

A super key is a set of one or more columns that can uniquely identify a record in a table. It may include additional columns beyond what is necessary for uniqueness, meaning that a super key can be a candidate key plus some extra columns.

**Characteristics:**

* **Uniqueness**: Can uniquely identify records, but may include additional columns beyond what is necessary for uniqueness.
* **Nullable**: Can include NULL values in some cases.
* **General**: A super key is a superset of candidate keys and may not be minimal.
* **Multiple Columns**: Can consist of one or more columns.

**Example**: In a `Products` table, the combination of `ProductID` and `SerialNumber` forms a super key, even though `ProductID` alone could uniquely identify each product. This is because the combination provides more information than necessary to ensure uniqueness.

```sql
CREATE TABLE Products (
    ProductID INT PRIMARY KEY,            -- Primary Key
    ProductName VARCHAR(100),
    SerialNumber VARCHAR(100),
    UNIQUE (ProductID, SerialNumber)      -- Unique constraint (it doesn't create a Composite Key:)
);
```

### 6. **Candidate Key**

A candidate key is a column (or a set of columns) that can uniquely identify any database record without referring to any other data. A table can have multiple candidate keys, and one of these is selected as the primary key.

**Characteristics:**

* **Primary Key Selection**: One candidate key is chosen as the primary key. The primary key is the main key used to uniquely identify records in the table. Other candidate keys that are not selected as the primary key are known as alternate keys.
* **Multiple Keys**: A table can have multiple candidate keys. Each candidate key is a potential choice for the primary key.
* **Uniqueness**: Each candidate key can uniquely identify a record in the table. It ensures that no two rows have the same value for the candidate key.
* **Non-nullable**: Typically, candidate keys should not contain NULL values, although this can depend on specific database implementations.

**Example**: In the `Employees` table, `EmployeeID`, `SocialSecurityNumber`, and `Email` can each uniquely identify an employee. Thus, they are candidate keys. You might choose `EmployeeID` as the primary key, while `SocialSecurityNumber` and `Email` remain as candidate keys.

```sql
CREATE TABLE Employees (
    EmployeeID INT,
    SocialSecurityNumber VARCHAR(11),
    Email VARCHAR(100),
    PRIMARY KEY (EmployeeID),           -- Candidate Key: EmployeeID (chosen as primary key)
    UNIQUE (SocialSecurityNumber),      -- Candidate Key: SocialSecurityNumber (unique but not chosen as primary key)
    UNIQUE (Email)                      -- Candidate Key: Email (unique but not chosen as primary key)
);
```

### 7. **Alternate Key**

An alternate key is any candidate key that is not chosen to be the primary key of the table. When a table has multiple candidate keys, one is selected as the primary key, and the others are considered alternate keys. These can be enforced as unique keys.

**Characteristics:**

* **Uniqueness**: Like a candidate key, it ensures uniqueness.
* **Non-nullable**: Typically should not contain NULL values.
* **Secondary**: Any candidate key that is not chosen as the primary key.
* **Multiple Keys**: A table can have multiple alternate keys, depending on the number of candidate keys.

**Example**: In the `Employees` table, if `EmployeeID` is chosen as the primary key, then `SocialSecurityNumber` and `Email` becomes an alternate key.

```sql
CREATE TABLE Employees (
    EmployeeID INT PRIMARY KEY,                  -- Primary Key
    SocialSecurityNumber VARCHAR(11) UNIQUE,     -- Alternate Key
    Email VARCHAR(100) UNIQUE,                   -- Alternate Key
    Department VARCHAR(50)
);
```

### 8. **Surrogate Key**

A surrogate key is an artificially created key that uniquely identifies each record in a table. It is typically an auto-incremented number or a system-generated value, and it has no business meaning. Surrogate keys are used when there is no natural key available or when using a natural key is not practical. They simplify database design by providing a simple, unique identifier for each record.

**Characteristics:**

* **Uniqueness**: Provides a unique identifier for a record, typically auto-generated.
* **Non-nullable**: Cannot contain NULL values.
* **Immutable**: Should remain constant once assigned.
* **System-generated**: Typically has no business meaning and is generated by the system (e.g., auto-incremented numbers).

**Example**: In a `Products` table, a `ProductID` column can serve as a surrogate key, with no real-world meaning but providing a unique identifier for each product.

```sql
CREATE TABLE Products (
    ProductID INT AUTO_INCREMENT PRIMARY KEY,      -- Surrogate key
    ProductName VARCHAR(100),
    SerialNumber VARCHAR(100)
);
```

### 9. **Natural Key**

A natural key is a type of primary key that is derived from the data itself. It has a business meaning and is used to uniquely identify a record based on natural attributes.

**Characteristics:**

* **Uniqueness**: Derived from the data itself, ensures uniqueness based on natural attributes.
* **Nullable**: Can contain NULL values depending on the business requirements.
* **Business Meaning**: Has inherent meaning in the business context (e.g., Social Security Number, Email).
* **Immutable**: Ideally should not change, although it might change in practice.

**Example**: In a `Customers` table, using `Email` as a primary key could be considered a natural key since it is a meaningful attribute that uniquely identifies a customer.

```sql
CREATE TABLE Customers (
    CT_Name VARCHAR(20),
    CT_Email VARCHAR(50) PRIMARY KEY,      -- Natural key
    CT_Password VARCHAR(50),
    CT_DOB Date
);
```

### 10. **Simple Key**

A simple key is a single column in a table that is used to uniquely identify each record. It ensures that each value in this column is unique and not duplicated. Simple keys are straightforward and easy to manage because they involve only one column. They are often used when a single attribute which can uniquely identify a record.

**Characteristics:**

* **Uniqueness**: Ensures that a single column uniquely identifies a record.
* **Non-nullable**: Typically should not contain NULL values.
* **Single-column**: Consists of only one column.
* **Primary Key**: Often used as a primary key due to its simplicity. A `UNIQUE` constraint can also be used to create a simple key.

**Example**: In the `Customers` table, the `CustomerID` column can be a simple key if it uniquely identifies each customer.

```sql
CREATE TABLE Customers (
    CustomerID INT PRIMARY KEY,      -- Simple key
    FirstName VARCHAR(50),
    LastName VARCHAR(50)
);
```

***

## **Key Comparisons**

### 1. **Primary Key vs. Unique Key**

**Primary Key:**

* Ensures that each value is unique and non-null.
* Only one primary key can be defined per table.
* Used to uniquely identify each record in the table.
* Typically chosen from the candidate keys.

**Unique Key:**

* Ensures that all values in the unique key column(s) are unique.
* Can include NULL values (depending on SQL implementation).
* A table can have multiple unique keys.
* Used to enforce uniqueness in a column or set of columns but does not serve as the primary identifier.

**Example:** In a `Customers` table, `CustomerID` might be the primary key, while `Email` could be a unique key ensuring no duplicate email addresses.

### 2. **Composite Key vs. Simple Key**

**Composite Key:**

* Consists of two or more columns.
* Used when a single column is not sufficient to uniquely identify a record.
* More complex to manage as it involves multiple attributes.

**Simple Key:**

* Consists of a single column.
* Used when one attribute can uniquely identify a record.
* Easier to manage and query.

**Example:** In a `CourseRegistrations` table, a combination of `StudentID` and `CourseID` could be a composite key, while a single `CustomerID` in a `Customers` table could be a simple key.

### 3. **Super Key vs. Candidate Key**

**Super Key:**

* A set of one or more columns that can uniquely identify records.
* Includes candidate keys as well as additional columns.
* Can be more complex and include unnecessary attributes.

**Candidate Key:**

* A minimal super key, meaning it has no unnecessary columns.
* Each candidate key can uniquely identify records in a table.
* One candidate key is chosen as the primary key, and others are considered alternate keys.

**Example:** In an `Employees` table, `EmployeeID`, `SocialSecurityNumber`, and `Email` could be super keys. However, `EmployeeID`, `SocialSecurityNumber`, and `Email` can each be candidate keys.

### 4. **Surrogate Key vs. Natural Key**

**Surrogate Key:**

* An artificially created key with no business meaning.
* Typically an auto-incremented number.
* Does not change over time.
* Used when there is no suitable natural key or when a stable, unique identifier is needed.

**Natural Key:**

* Derived from real-world data attributes.
* Has business meaning and is often unique by nature.
* Can change over time if the underlying data changes.
* Used when an existing, meaningful unique identifier is present.

**Example:** In a `Students` table, `StudentID` could be a surrogate key (an auto-incremented number) or a natural key (a government-issued student number).

## 2.) Domain Constraints

Domain Constraints are rules applied to columns to restrict the type, format, and range of data that can be entered. They ensure that the data stored in the column meets specific criteria and fits defined standards.

### Type of Domain Constraints:

### 1. **Not Null Constraint**

The Not Null constraint ensures that a column cannot contain `NULL` values. This constraint is used when we want to make sure that every record in the table has a valid value for a particular column.

**Characteristics:**

* **Mandatory Values**: Requires that all entries in the column have a value. `NULL` values are not allowed.
* **Data Integrity**: Ensures that the data is always present in the column, avoiding gaps or missing values.
* **Column-Specific**: Applied to individual columns within a table.

**Example**: In an `Employees` table, we may want to ensure that every employee has a `Name` recorded. By applying a `Not Null` constraint to the `Name` column, we ensure that no record can have a missing Name.

```sql
CREATE TABLE Employees (
    EmployeeID INT PRIMARY KEY,          
    Name VARCHAR(100) NOT NULL,      -- Not Null: Ensures Name cannot be NULL or leave as blank
    Salary DECIMAL(10, 2)
);
```

### 2. **Default Constraint**

The Default constraint automatically assigns a pre-defined value to a column if no value is provided during an insert operation. This constraint is useful for ensuring consistency and reducing the need for manual input.

**Characteristics:**

* **Automatic Assignment**: Automatically fills the column with the default value if no explicit value is provided.
* **Consistency**: Helps maintain uniformity in the data by ensuring that a default value is always used when necessary.
* **Customizable**: The default value can be defined based on the specific requirements of the database.

**Example**: In an `Employees` table, we might want to automatically assign the current date to the `hire_date` column when a new record is inserted, ensuring that every employee's hire date is recorded without manual entry.

```sql
CREATE TABLE Employees (
    EmployeeID INT PRIMARY KEY,             		 
    Name VARCHAR(100),                      	      -- Regular column for employee names
    HireDate TIMESTAMP DEFAULT CURRENT_TIMESTAMP      -- Default: Automatically sets hire date to the current date
);
```

### 3. **Check Constraint**

The Check constraint enforces a specific condition that each row in the table must satisfy. It is used to limit the values that can be placed in a column, ensuring that the data meets certain criteria.

**Characteristics:**

* **Conditional Enforcement**: Ensures that the data in the column meets a specified condition.
* **Data Validation**: Acts as a form of data validation at the database level, preventing invalid data from being entered.
* **Flexible**: The condition can be customized to match the specific needs of the application.

**Example**: In a `Persons` table, we may want to ensure that the `age` of each person is at least 18 years. By applying a `Check` constraint, we can enforce this rule.

```sql
CREATE TABLE Persons (
    PersonID INT PRIMARY KEY,               
    Name VARCHAR(100),             -- Regular column for person names
    Age INT CHECK (Age >= 18)      -- Check: Ensures age is at least 18
);
```
