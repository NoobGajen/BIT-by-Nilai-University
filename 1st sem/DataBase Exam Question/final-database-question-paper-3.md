# Final - Database Question Paper - 3

## QUESTION 1&#x20;

### a.) Contrast define and construct in database management systems functionality.

#### Define

To define involves specifying the structure, rules, and constraints of the database and its components.

* **Functionality**:
  * Involves creating schemas, tables, and data types.
  * Specifies relationships between entities and constraints like primary keys, foreign keys, and unique constraints.
  * Often uses Data Definition Language (DDL) commands like `CREATE`, `ALTER`, and `DROP`.
* **Example**: Defining a table for storing student information with attributes like `StudentID`, `Name`, and `Email`.

#### Construct

To construct involves creating and populating actual data structures based on the definitions provided.

* **Functionality**:
  * Focuses on implementing the database using the defined schema.
  * Includes inserting, updating, and deleting data within the defined structures.
  * Typically uses Data Manipulation Language (DML) commands like `INSERT`, `UPDATE`, and `DELETE`.
* **Example**: Constructing the database by adding records of students into the previously defined student table.

#### Summary

* **Define** is about creating the framework and rules of the database, while **construct** is about filling that framework with actual data and managing it.

### b.) Explain the following advantages of database.

#### i. Enforcing Integrity Constraints on the Database.

Integrity constraints are rules that ensure the accuracy and consistency of data within the database.

* **Advantages**:
  * **Data Accuracy**: Constraints such as primary keys, foreign keys, and unique constraints prevent invalid data entry, ensuring that each record is unique and related appropriately.
  * **Consistency**: They maintain data consistency across related tables by enforcing rules that govern how data can be entered and modified (e.g., a student must exist before enrolling in a course).
  * **Automatic Validation**: Integrity constraints automatically check data validity during transactions, reducing the chances of human error.

#### ii. Restricting Unauthorized Access to Data.

This refers to the measures taken to prevent unauthorized users from accessing sensitive information in the database.

* **Advantages**:
  * **Data Security**: By implementing user roles and permissions, databases restrict access to sensitive data, ensuring that only authorized personnel can view or modify specific information.
  * **Confidentiality**: Protecting sensitive data helps maintain confidentiality and compliance with regulations (e.g., GDPR, HIPAA).
  * **Audit Trails**: Most databases log access attempts, allowing for monitoring and auditing of who accessed what data, enhancing accountability.

#### iii. Representing Complex Relationships Among Data.

Databases can model complex interconnections between different data entities through relationships.

* **Advantages**:
  * **Rich Data Representation**: By using foreign keys and join operations, databases can represent complex relationships such as one-to-many, many-to-many, and hierarchical structures.
  * **Efficient Data Retrieval**: Complex relationships enable sophisticated queries that can retrieve related data in a single operation, reducing the need for repetitive data handling.
  * **Flexibility**: Databases can easily adapt to changing business requirements by modifying relationships without significant restructuring, allowing for more dynamic data management.

### c.) Clean Carpet is opening the 3' branch, and has come to you for consultation. Upon the investigation, you found that Clean Carpet Is keeping track of their sales and service records manually by multiple staffs in each branch, which potentially lead to errors in their records. Would you recommend Clean Carpet to use database management system? Discuss THREE (3) reasons.

I would recommend that Clean Carpet adopt a Database Management System (DBMS) for the following reasons:

**1. Improved Data Accuracy**

A DBMS minimizes human error by automating data entry and validation processes.

* **Benefit**: This leads to more accurate sales and service records, reducing discrepancies that can occur with manual tracking.

**2. Centralized Data Management**

A DBMS provides a single platform for storing and managing data from all branches.

* **Benefit**: This centralization allows for easier access, updates, and management of information, ensuring that all staff have access to the same, up-to-date records.

**3. Enhanced Reporting and Analytics**

A DBMS can generate reports and perform complex queries to analyze sales and service data.

* **Benefit**: Clean Carpet can gain insights into sales trends, customer preferences, and service performance, which can inform business decisions and strategies.

**4. Data Security and Access Control**

A DBMS includes features for securing sensitive data and controlling user access.

* **Benefit**: This ensures that only authorized personnel can view or modify records, protecting confidential customer information and sales data.

**5. Scalability and Flexibility**

As Clean Carpet expands, a DBMS can easily accommodate growing data needs without a significant redesign.

* **Benefit**: This scalability allows the business to adapt to increased transaction volumes and new service offerings without compromising performance or requiring a complete overhaul of the data management system.

### d.) Contrast between database schema and database state, with a diagram for each.

**Database Schema**:

* A database schema is the structure of a database, like a map.
* It defines how tables are organized, what columns (attributes) each table has, the data types (like numbers or text), and the relationships between tables.
* The schema is usually fixed and doesn’t change unless modified by a database administrator.
* It acts as a blueprint for how data is stored and helps ensure that the data is organized correctly.

<figure><img src=".gitbook/assets/Diagram of a database schema.png" alt=""><figcaption><p>Diagram of a database schema</p></figcaption></figure>

**Database State**:

* A database state is the actual data that exists in the database at any given time.
* This state changes when data is added, updated, or deleted.
* It reflects the current content of the database and can be queried to retrieve real information.
* Each time we make changes, we affect the database state, which is essential for accurate data management.

<figure><img src=".gitbook/assets/Diagram of a database state.png" alt=""><figcaption><p>Diagram of a database state</p></figcaption></figure>

## QUESTION 2&#x20;

### a.) Explain the following diagram.

<figure><img src=".gitbook/assets/Final database question paper 3 Question 2.a.png" alt=""><figcaption></figcaption></figure>

#### Answer:-

**1. Emergency Contact (One to Many) – Provides – (One) Participant**

* An emergency contact can be linked to one to many participants.
* Each participant must have exactly one emergency contact.

**2. Participant (Zero, One, or Many) – Accommodates – (One) Cabin**

* A participant can stay in zero, one, or many cabins.
* Each cabin must have at least one participant.

**3. Cabin (One to Many) – In Charge of – (One) Cabin Host**

* Each cabin can have one to many cabin hosts.
* Each cabin host is responsible for one cabin.

**4. Participant (One to Many) – Follows – (One to Many) Instructor**

* A participant can follow one to many instructors.
* An instructor can guide one to many participants.

**5. Instructor (One) – Guides – (One to Many) Activities**

* An instructor can guide one to many activities.
* Each activity must have at least one instructor.

### b) Draw an entity relationship diagram for the following statement, complete with the entities, key attributes with the primary keys underlined, relationships, and cardinalities.&#x20;

In order to make a dinner reservation at the Aurore's (a well-known restaurant), a customer Is required to at least provide his/her name. The customer may reserve one or more tables, depending on the number of party. The customer may order one or more of the same or different meals.

#### Answer:-

#### Entities and Key Attributes

1. **Customer**
   * **CustomerID** (Primary Key)
   * Name
2. **Table**
   * **TableID** (Primary Key)
   * Number (Table number)
3. **Reservation**
   * **ReservationID** (Primary Key)
   * CustomerID (Foreign Key)
   * TableID (Foreign Key)
   * PartySize
   * ReservationDate
4. **Meal**
   * **MealID** (Primary Key)
   * Name
   * Price
5. **CustomerMeal** (Junction Table for Many-to-Many relationship)
   * **CustomerMealID** (Primary Key)
   * CustomerID (Foreign Key)
   * MealID (Foreign Key)

#### Relationships and Cardinalities

1. **Customer - Reservation**: One-to-Many
   * A customer can make multiple reservations (1 to Many).
   * A reservation is made by one customer (Many to 1).
2. **Reservation - Table**: Many-to-One
   * A reservation can include one table (Many to 1).
   * A table can be associated with multiple reservations (1 to Many).
3. **Customer - Meal**: Many-to-Many
   * A customer can order multiple meals (Many to Many).
   * A meal can be ordered by multiple customers (Many to Many).

<figure><img src=".gitbook/assets/Final database question paper 3 Question 2.b.png" alt=""><figcaption><p>ER diagram by using Crow's Foot Notation</p></figcaption></figure>

## QUESTION 3

The Tablet below is provided as a reference for the following questions.

| CustomerName | HouseAddress     | Contact      | Item        | Price | Seller  | Extension |
| ------------ | ---------------- | ------------ | ----------- | ----- | ------- | --------- |
| Britney      | 15 Lilly Dr.     | 012 555 5555 | La Liberta  | $36   | Brandon | 0121      |
| Justin       | 191 Madison St.  | 016 333 3333 | Case Valker | $58   | Molly   | 0122      |
| Justin       | 201 Florida Ave. | 016 333 3333 | Case Valker | $58   | Molly   | 0122      |
| Nick         | 201 Florida Ave. | 019 777 7777 | La Liberta  | $36   | Brandon | 0121      |

### a.) Apply first normalization form (I NF) to Table 1.

#### Answer:-

**Original Unnormalized Table (UNF)**

| CustomerName  | HouseAddress     | Contact      | Item                | Price | Seller  | Extension |
| ------------- | ---------------- | ------------ | ------------------- | ----- | ------- | --------- |
| Britney House | 15 Lilly Dr.     | 012 555 5555 | La Liberta Luggage  | $36   | Brandon | 0121      |
| Justin Dear   | 191 Madison St.  | 016 333 3333 | Case Valker Luggage | $58   | Molly   | 0122      |
| Nick Hammer   | 201 Florida Ave. | 019 777 7777 | La Liberta Luggage  | $58   | Molly   | 0122      |
| Nick Hammer   | 201 Florida Ave. | 019 777 7777 | La Liberta Luggage  | $36   | Brandon | 0121      |

**Applying First Normal Form (1NF)**

1. **Atomic Values**: Each field contains only one value, with no repeating groups.
2. **Uniform Data Types**: Each column has values of the same type.
3. **Unique Attribute Names**: Each column has a unique name.
4. **No Duplicates**: While there are repeated customer entries, they represent different items.

**Resulting Table in 1NF**

The table is already in 1NF and remains unchanged:

| CustomerName  | HouseAddress     | Contact      | Item                | Price | Seller  | Extension |
| ------------- | ---------------- | ------------ | ------------------- | ----- | ------- | --------- |
| Britney House | 15 Lilly Dr.     | 012 555 5555 | La Liberta Luggage  | $36   | Brandon | 0121      |
| Justin Dear   | 191 Madison St.  | 016 333 3333 | Case Valker Luggage | $58   | Molly   | 0122      |
| Nick Hammer   | 201 Florida Ave. | 019 777 7777 | La Liberta Luggage  | $58   | Molly   | 0122      |
| Nick Hammer   | 201 Florida Ave. | 019 777 7777 | La Liberta Luggage  | $36   | Brandon | 0121      |

### b.) Apply the second normalization form (2NF) to your answer for Question 3a. Treat this question as an independent separate question, and provide the full answer. Construct all/full table(s), regardless whether there is no change to the table(s) from your answer for Question 3a.

#### Answer:-

To achieve Second Normal Form (2NF), we need to ensure that the table is already in First Normal Form (1NF) and that all non-key attributes are fully functionally dependent on the primary key. This means there should be no partial dependencies of any column on a composite primary key.

**Original Table in 1NF**

| CustomerName  | HouseAddress     | Contact      | Item                | Price | Seller  | Extension |
| ------------- | ---------------- | ------------ | ------------------- | ----- | ------- | --------- |
| Britney House | 15 Lilly Dr.     | 012 555 5555 | La Liberta Luggage  | $36   | Brandon | 0121      |
| Justin Dear   | 191 Madison St.  | 016 333 3333 | Case Valker Luggage | $58   | Molly   | 0122      |
| Nick Hammer   | 201 Florida Ave. | 019 777 7777 | La Liberta Luggage  | $58   | Molly   | 0122      |
| Nick Hammer   | 201 Florida Ave. | 019 777 7777 | La Liberta Luggage  | $36   | Brandon | 0121      |

**Step 1: Identify the Primary Key**

In this scenario, the primary key could be a combination of `CustomerName`, `Item`, and `Seller` since these together uniquely identify each record. However, to simplify, we can use a unique `OrderID` for each entry.

**Step 2: Identify Partial Dependencies**

1. **Non-key attributes**:
   * `HouseAddress`, `Contact`, and `Extension` depend only on `CustomerName`.
   * `Price` depends on `Item` and `Seller`.

**Step 3: Decompose the Table into 2NF**

We will create separate tables to eliminate partial dependencies:

1. **Customer Table** (Stores customer details)
   * **Primary Key**: CustomerName
   * **Attributes**: HouseAddress, Contact, Extension
2. **Item Table** (Stores item details)
   * **Primary Key**: Item (can be the name itself)
   * **Attributes**: Price, Seller
3. **Order Table** (Stores order details)
   * **Primary Key**: OrderID (new unique identifier)
   * **Attributes**: CustomerName (Foreign Key), Item (Foreign Key)

**Resulting Tables in 2NF**

**1. Customer Table**

| CustomerName  | Address          | Contact      |
| ------------- | ---------------- | ------------ |
| Britney House | 15 Lilly Dr.     | 012 555 5555 |
| Justin Dear   | 191 Madison St.  | 016 333 3333 |
| Nick Hammer   | 201 Florida Ave. | 019 777 7777 |

**2. Order Table**

| CustomerName  | Item                | Price | Seller  | Extension |
| ------------- | ------------------- | ----- | ------- | --------- |
| Britney House | La Liberta Luggage  | $36   | Brandon | 0121      |
| Justin Dear   | Case Valker Luggage | $58   | Molly   | 0122      |
| Nick Hammer   | La Liberta Luggage  | $58   | Molly   | 0122      |
| Nick Hammer   | La Liberta Luggage  | $36   | Brandon | 0121      |

### c.) Apply the third normalization form (3NF) to your answer for Question 3b. Treat this question as an Independent separate question, and provide the full answer. Construct all/full table(s), regardless whether there is no change to the table(s) from your answer for Question 3b.

#### Answer:-

To achieve Third Normal Form (3NF), we must ensure that:

1. The table is already in Second Normal Form (2NF).
2. There are no transitive dependencies, meaning non-key attributes do not depend on other non-key attributes.

#### Step 1: Identify Transitive Dependencies

In the current tables:

* The **Customers** table has no transitive dependencies; all attributes are directly related to the primary key (`CustomerName`).
* The **Items** table also has no transitive dependencies; all attributes are directly tied to the primary key (`Item`).
* The **Sellers** table has attributes that are solely dependent on the `SellerID`, and the **Orders** table only holds foreign keys that relate to the primary keys of the other tables.

#### Step 2: Decompose Tables to Remove Transitive Dependencies

1.  **Customers Table**: This table remains unchanged as it is already in 3NF.



    | CustomerName  | Address          | Contact      |
    | ------------- | ---------------- | ------------ |
    | Britney House | 15 Lilly Dr.     | 012 555 5555 |
    | Justin Dear   | 191 Madison St.  | 016 333 3333 |
    | Nick Hammer   | 201 Florida Ave. | 019 777 7777 |
2.  **Items Table**: We will modify this table to include a `SellerID`, creating a foreign key relationship.



    | Item                | Price | SellerID |
    | ------------------- | ----- | -------- |
    | La Liberta Luggage  | $36   | 1        |
    | Case Valker Luggage | $58   | 2        |
3.  **Sellers Table**: This new table will store seller details and maintain the `SellerID` as the primary key.

    | SellerID | Seller  | Extension |
    | -------- | ------- | --------- |
    | 1        | Brandon | 0121      |
    | 2        | Molly   | 0122      |
4.  **Orders Table**: This table remains unchanged, now using `SellerID` as a reference to the seller and holding a foreign key for the `CustomerName`.

    | OrderID | CustomerName  | Item                |
    | ------- | ------------- | ------------------- |
    | 1       | Britney House | La Liberta Luggage  |
    | 2       | Justin Dear   | Case Valker Luggage |
    | 3       | Nick Hammer   | La Liberta Luggage  |
    | 4       | Nick Hammer   | La Liberta Luggage  |

#### Resulting Tables in 3NF

* **Customers Table**: No changes, already in 3NF.
* **Items Table**: Updated to include `SellerID`.
* **Sellers Table**: Newly created to maintain seller information, eliminating any transitive dependencies.
* **Orders Table**: No changes, maintains integrity with foreign keys.

## QUESTION 4

The Table 2 below is provided as a reference for the following questions. Answers are expected to be in Structured Query Language (SQL).

**Table 2: Student Table Definition**

| Field Name            | Data Type                 | Primary Key |
| --------------------- | ------------------------- | ----------- |
| Patron ID             | Number                    | Yes         |
| Patron Name           | Text - 255 characters max | No          |
| Patron Contact Number | Text - 10 characters max  | No          |

### a.) Construct a patron table using SQL with the appropriate field names and properties.

To create the `Patron` table using SQL, we will define the field names, data types, and primary key as specified in the table definition. Here’s the SQL query:

```sql
CREATE TABLE Patron (
    PatronID INT PRIMARY KEY,
    PatronName VARCHAR(255),
    PatronContactNumber VARCHAR(10)
);
```

### b.) Insert the following data into the table using SQL

| Patron ID | Patron Name | Patron Contact Number |
| --------- | ----------- | --------------------- |
| 45660     | Damien Tan  | 0123456789            |

To insert the specified data into the `Patron` table, we will use the following SQL query:

```sql
INSERT INTO Patron (PatronID, PatronName, PatronContactNumber) 
VALUES (45660, 'Damien Tan', '0123456789');
```

### c.) Assume the participant table has the following data.

| Patron ID | Patron Name | Patron Contact Number |
| --------- | ----------- | --------------------- |
| 45660     | Damien Tan  | 0123456789            |
| 21089     | Larry Smith | 0124463840            |
| 19876     | Sarah Tan   | 0127896789            |
| 75832     | Sandra Chow | 0128787878            |

#### **i.) Create an SQL query to display only the Patron Name and the Patron Contact Number.**

```sql
SELECT PatronName, PatronContactNumber FROM Patron;
```

#### **ii.) Create an SQL query to display the Patron Name and the Patron Contact Number where the Patron ID is 45660..**

```sql
SELECT PatronName, PatronContactNumber FROM Patron WHERE PatronID = 45660;
```

#### **iii.) Create an SQL query to display the Patron ID, Patron Name, and Patron Contact Number for all participants with the last name Tan.**

```sql
SELECT PatronID, PatronName, PatronContactNumber FROM Patron WHERE PatronName LIKE '%Tan';
```

#### **iv.) Create an SQL query to display the Patron Name, where the Patron ID is either 19876 or 21089.**

```sql
SELECT PatronName FROM Patron WHERE PatronID IN (19876, 21089);
```













