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

**Original Unnormalized Table (UNF)**

| CustomerName | HouseAddress     | Contact      | Item        | Price | Seller  | Extension |
| ------------ | ---------------- | ------------ | ----------- | ----- | ------- | --------- |
| Britney      | 15 Lilly Dr.     | 012 555 5555 | La Liberta  | $36   | Brandon | 0121      |
| Justin       | 191 Madison St.  | 016 333 3333 | Case Valker | $58   | Molly   | 0122      |
| Justin       | 201 Florida Ave. | 016 333 3333 | Case Valker | $58   | Molly   | 0122      |
| Nick         | 201 Florida Ave. | 019 777 7777 | La Liberta  | $36   | Brandon | 0121      |

**Applying First Normal Form (1NF)**

1. **Atomic Values**: Each field contains only one value, with no repeating groups.
2. **Uniform Data Types**: Each column has values of the same type.
3. **Unique Attribute Names**: Each column has a unique name.
4. **No Duplicates**: While there are repeated customer entries, they represent different items.

**Resulting Table in 1NF**

The table is already in 1NF and remains unchanged:

| CustomerName | HouseAddress     | Contact      | Item        | Price | Seller  | Extension |
| ------------ | ---------------- | ------------ | ----------- | ----- | ------- | --------- |
| Britney      | 15 Lilly Dr.     | 012 555 5555 | La Liberta  | $36   | Brandon | 0121      |
| Justin       | 191 Madison St.  | 016 333 3333 | Case Valker | $58   | Molly   | 0122      |
| Justin       | 201 Florida Ave. | 016 333 3333 | Case Valker | $58   | Molly   | 0122      |
| Nick         | 201 Florida Ave. | 019 777 7777 | La Liberta  | $36   | Brandon | 0121      |

