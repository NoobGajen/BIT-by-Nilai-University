# Final - Database Question Paper - 2

## Question 1&#x20;

### a.) What is a database management system (DBMS)? List any FIVE (5) advantages of DBMS.

A **Database Management System (DBMS)** is software that allows users to create, manage, and interact with databases. It provides an interface for storing, retrieving, updating, and managing data efficiently. A DBMS ensures data integrity, security, and organization, and supports simultaneous access by multiple users.



#### Five (5) Advantages of DBMS:

* **Data Consistency**: Ensures that data remains consistent across different applications, reducing errors and unusual problems.
* **Data Security**: Implements security measures like encryption and access controls to protect data from unauthorized access.
* **Data Sharing**: Allows multiple users to access the database simultaneously without causing conflicts, facilitating collaboration.
* **Efficient Data Management**: Improves data storage and retrieval processes, making it easier to manage large amounts of data.
* **Backup and Recovery**: Provides automatic backup and recovery mechanisms, ensuring data is safe and can be restored in case of failures.

### b.) Differentiate between:

#### &#x20;i.) Logical and physical data independence



| **Aspect**                | **Logical Data Independence**                                                                                                                        | **Physical Data Independence**                                                                                                                                         |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Definition**            | The ability to change the structure of the database (like tables or relationships) without affecting how users or applications view or use the data. | The ability to change how data is stored (like changing storage devices or file formats) without affecting the structure of the database or how users access the data. |
| **Focus**                 | Focuses on the structure of the database, such as tables, columns, and relationships.                                                                | Focuses on how data is physically stored in files, memory, or on disk.                                                                                                 |
| **Impact of Change**      | Changes like adding or removing a column in a table won’t affect the way users or applications see or access the data.                               | Changes in how data is stored (for example, moving from one hard drive to another) won’t affect the structure or how data is accessed.                                 |
| **Example**               | Adding a new column to a table doesn’t require changing the application programs that use that table.                                                | Moving the database from an old hard drive to a new one doesn’t change how users or applications access the data.                                                      |
| **Level of Independence** | It’s at a higher level because it deals with changes in the database structure without affecting how users see the data.                             | It’s at a lower level because it deals with how data is stored without changing the structure of the database.                                                         |
| **Ease of Achieving**     | Harder to achieve because changing the database structure might affect some queries or views.                                                        | Easier to achieve because changing where or how data is stored doesn’t affect the database structure.                                                                  |



#### ii.) External and conceptual level.



| **Aspect**            | **External Level**                                                                                                    | **Conceptual Level**                                                                                                             |
| --------------------- | --------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| **Definition**        | The level focused on how individual users or applications see and interact with the data, providing customized views. | The level that represents the overall structure and organization of the entire database, abstracting away user-specific details. |
| **User Focus**        | Focuses on how individual users or applications see and interact with the data.                                       | Focuses on the overall structure and organization of the entire database.                                                        |
| **Customization**     | Allows customized views for different users, presenting only relevant data.                                           | Does not involve customization; defines the overall data model for the whole database.                                           |
| **Data Visibility**   | Users can access specific parts of the data based on permissions.                                                     | Represents the entire database structure without user-specific details.                                                          |
| **Security**          | Enforces security by restricting access to authorized data for users.                                                 | Defines security rules but implements them at the external level.                                                                |
| **Impact of Changes** | Changes at this level don’t affect the underlying structure.                                                          | Changes here can impact the external level, requiring updates to user views.                                                     |
| **Examples**          | A sales department sees only customer orders, not HR data.                                                            | Contains tables for customers, sales, and products, defining their relationships.                                                |

### c.) Identify THREE (3) roles of data administration and database administration.

Here are five key roles for both Data Administration (DA) and Database Administration (DBA):

#### Data Administration (DA) Roles:

1. **Data Governance**: Ensuring the quality, integrity, and compliance of data across the organization, establishing policies and standards for data management.
2. **Data Modeling**: Designing logical and physical data models that represent the organization’s data structures, ensuring they align with business requirements.
3. **Metadata Management**: Managing metadata to enhance data discovery and understanding, providing context about data sources, structures, and usage.
4. **Data Lifecycle Management**: Overseeing the entire lifecycle of data, from creation and storage to archiving and deletion, ensuring efficient data usage and compliance.
5. **Data Integration**: Coordinating the integration of data from various sources, ensuring that data is consistent, accessible, and usable across different systems.

#### Database Administration (DBA) Roles:

1. **Database Installation & Configuration**: Setting up and configuring database servers and software to meet specific organizational needs and requirements.
2. **Performance Monitoring and Tuning**: Continuously monitoring database performance and making necessary adjustments to optimize speed and efficiency.
3. **Backup and Recovery Management**: Developing and implementing backup strategies to protect data from loss and ensuring effective recovery procedures are in place.
4. **Security Management**: Controlling access to the database, implementing security measures to protect against unauthorized access and data breaches.
5. **Troubleshooting and Support**: Diagnosing and resolving database-related issues, providing support to users and applications that depend on the database.

### d.) Provide TWO (2) methods for securing a database.

Here are five effective methods for securing a database:

1. **Access Control**: Implement strict access controls by defining user roles and permissions. Ensure that users have only the access necessary for their roles, using the principle of least privilege.
2. **Data Encryption**: Encrypt sensitive data both at rest (stored data) and in transit (data being transmitted) to protect it from unauthorized access. Use strong encryption algorithms to secure the data.
3. **Regular Backups**: Perform regular backups of the database to ensure that data can be restored in case of loss or corruption. Store backups securely and test the restoration process periodically.
4. **Network Security**: Use firewalls, intrusion detection systems, and secure network configurations to protect the database from unauthorized access and attacks. Limit database access to trusted IP addresses and networks.
5. **Monitoring and Auditing**: Continuously monitor database activity for suspicious behavior and conduct regular audits of user access and actions. Implement logging to track changes and access to sensitive data, allowing for quick detection of potential security breaches.

## Question 2

You are working as a System Analyst at Zahra Corporation Sdn. Bhd. Your company requires to have E-Appointment Management System to manage all appointments with clients. This system will have to cater to all the necessary requirements pertaining to the scheduling of appointments.

Before the project starts, you have to collect and analyze the data requirements for the new system. Based on the interview with expected users, below are the list of data requirements.

* The data held on appointments is the appointment ID, appointment types, description, event, date, time, contact number, person to contact, staff identification number, and client identification number.
* Staff information should have data about staff identification number, staff name, user login, password, email, address, and contact number.
* The data held on clients is the client identification number, client name, address, contact number, and email.
* Staff has many roles. Clerk will manage all information about clients that have an appointment, whereas management staff will use the system for updating new appointments and to retrieve appointment information belonging to him/her.
* Management staff will have more than one appointment.
* Each appointment will have one client.

### a) Draw the complete entity-relationship (ER) diagram by showing the type of relationships between entities and cardinality constraints for the scenario above.                                        (20 MARKS)

#### **Answer:-**

In an ER diagram, entities are represented as rectangles, attributes as ovals, and relationships as diamonds. Cardinality constraints are denoted using lines and numbers to show how many instances of one entity can be associated with instances of another.

Based on the given scenario, here is the ER diagram:

<figure><img src=".gitbook/assets/Final database question paper 2 Question 2.a.1.png" alt=""><figcaption><p>ER diagram by using Crow's Foot Notation</p></figcaption></figure>













place holder for chen notation



























### b.) Explain the TWO (2) types of constraints that may apply to specialization or generalization.                                        (3 MARKS)

The two types of constraints that may apply to specialization or generalization are:

1. **Disjointness Constraint**:
   * This constraint defines whether an entity can belong to more than one subclass (specialization) or not.
   * **Disjoint Rule**: An entity can only belong to one subclass at a time. For example, if an entity belongs to the "Clerk" subclass, it cannot belong to the "Management Staff" subclass.
   * **Overlap Rule**: An entity can belong to more than one subclass at the same time. For example, a person can be both a "Clerk" and a "Management Staff" at the same time.
2. **Participation Constraint**:
   * This constraint specifies whether all entities in the superclass must be a member of at least one subclass or not.
   * **Total Participation**: Every entity in the superclass must belong to at least one subclass. For example, every staff must be either a "Clerk" or "Management Staff."
   * **Partial Participation**: Some entities in the superclass may not belong to any subclass. For example, a staff may not need to belong to either subclass.

### c.) Define derived attribute. Provide an example for derived attribute.

A derived attribute is an attribute whose value is calculated or derived from other attributes in the database, rather than being directly stored. It is not physically stored in the database but is computed whenever needed.

#### Example:

In a payroll system, **age** can be a derived attribute if we store a person's **birthdate** in the database. The value of the age can be derived by subtracting the birthdate from the current date.

**Example of a derived attribute:**

```plaintext
Age = Current Date - Birthdate
```

In this case, **Age** is derived from the **Birthdate** and does not need to be stored directly in the database.

## Question 3 - [Same as Paper - 1 Question no. 3](final-database-question-paper-1.md#question-3)

## Question 4

### a.) Define each of the following terms:

#### i) Relation Schema

A **relation schema** refers to the blueprint or structure of a table in a database. It defines the table's name, its attributes (columns), and the types of values that can be stored in each attribute. The schema does not store the data itself but provides the framework for organizing and storing data.

**Example**:\
Consider a relation schema for an `Employee` table:

```plaintext
Employee(employee_id, employee_name, birthdate, salary)
```

Here, the schema defines that the `Employee` table has four attributes: `employee_id`, `employee_name`, `birthdate`, and `salary`.

#### ii) Data Definition Language (DDL)

**Data Definition Language (DDL)** is a set of SQL commands used to define, modify, and delete database structures like tables, indexes, and views. It deals with the schema of the database, specifying how data is stored, and the relationships between data.

**Example**:\
Common DDL commands include:

* `CREATE TABLE` - creates a new table.
* `ALTER TABLE` - modifies an existing table.
* `DROP TABLE` - deletes a table.

Example of a DDL command to create a table:

```sql
CREATE TABLE Employee (
    employee_id INT PRIMARY KEY,
    employee_name VARCHAR(100),
    birthdate DATE,
    salary DECIMAL(10, 2)
);
```

#### iii) Data Manipulation Language (DML)

**Data Manipulation Language (DML)** is a set of SQL commands used to interact with and manipulate the data within a database. This includes inserting, updating, deleting, and querying data from the tables. Unlike DDL, DML does not change the schema of the database, but rather the data itself.

**Example**:\
Common DML commands include:

* `INSERT INTO` - adds new data.
* `UPDATE` - modifies existing data.
* `DELETE FROM` - removes data.
* `SELECT` - retrieves data.

Example of a DML command to insert data:

```sql
INSERT INTO Employee (employee_id, employee_name, birthdate, salary)
VALUES (1, 'Gajendra Mahato', '2000-01-10', 50000);
```

### b.) Provide THREE (3) categories of data models.

The three categories of data models are:

#### 1. **Hierarchical Data Model**

The **hierarchical data model** organizes data in a tree-like structure, where each record (or node) has a single parent, and records are linked in a parent-child relationship. This model is particularly useful when there is a clear hierarchy in the data, such as in organizational charts or file systems.

**Example**:\
In an organization, an employee might report to a manager, and the manager reports to a director. Each node in the hierarchy represents one entity, and the parent-child relationship reflects how they are connected.

#### 2. **Relational Data Model**

The **relational data model** is the most widely used data model. In this model, data is organized into tables (also called relations), where each table consists of rows (tuples) and columns (attributes). Tables can be related to each other through foreign keys. It offers a flexible way to query and manipulate data using SQL.

**Example**:\
A database might have a table for `Employees` and another for `Departments`. The `Employees` table contains employee details, while the `Departments` table contains information about departments. A foreign key in the `Employees` table links each employee to their respective department.

#### 3. **Object-Oriented Data Model**

The **object-oriented data model** integrates database concepts with object-oriented programming principles. Data is represented as objects, similar to how data and methods are encapsulated in classes in object-oriented programming. Objects can inherit properties from other objects, enabling more complex and reusable data structures.

**Example**:\
An `Employee` class can have attributes like `name` and `salary`, and methods like `calculateBonus()`. The object-oriented data model allows for modeling real-world entities and their relationships in a more natural way, especially in complex applications.

### c.) Write the SQL statements for the table illustrated below:

#### TUTOR

| TutorID | CertDate   | Status    |
| ------- | ---------- | --------- |
| 100     | 05/01/2016 | Active    |
| 101     | 05/01/2016 | Temp Stop |
| 102     | 05/01/2016 | Dropped   |
| 103     | 20/05/2016 | Active    |
| 104     | 20/05/2016 | Active    |
| 105     | 20/05/2016 | Temp Stop |

#### STUDENT

| StudentID | Read |
| --------- | ---- |
| 3000      | 2.3  |
| 3001      | 5.6  |
| 3002      | 1.3  |
| 3003      | 3.3  |
| 3004      | 2.7  |
| 3005      | 4.8  |
| 3006      | 7.8  |

#### MATCH HISTORY

| MatchID | TutorID | StudentID | StartDate  | EndDate    |
| ------- | ------- | --------- | ---------- | ---------- |
| 1       | 100     | 3000      | 10/01/2016 |            |
| 2       | 101     | 3001      | 15/01/2016 | 15/05/2016 |
| 3       | 102     | 3002      | 10/02/2016 | 01/03/2016 |
| 4       | 105     | 3003      | 28/05/2016 |            |
| 5       | 104     | 3004      | 06/01/2016 | 15/06/2016 |
| 6       | 104     | 3005      | 06/01/2016 | 28/06/2016 |
| 7       | 103     | 3006      | 06/01/2016 |            |

#### **Answer:-**

#### i.) List all the fields for the table STUDENT.

```sql
SELECT *
FROM STUDENT;
```

#### ii.) Count the number of tutors that have a status of Temp Stop. Rename the result as 'NUMTSTOP'.

```sql
SELECT COUNT(*) AS NUMTSTOP
FROM TUTOR
WHERE Status = 'Temp Stop';
```

#### iii.) Find out the tutors who are active.

```sql
SELECT *
FROM TUTOR
WHERE Status = 'Active';
```

#### iv.) List the StudentID and student's Read score in descending order.

```sql
SELECT StudentID, Read
FROM STUDENT
ORDER BY Read DESC;
```

#### v.) Count the number of students that were taking the adult literacy program in the first five months of the year.

```sql
SELECT COUNT(*) AS NumStudents
FROM MATCH_HISTORY
WHERE StartDate >= '2016-01-01' AND StartDate < '2016-06-01';
```

