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
