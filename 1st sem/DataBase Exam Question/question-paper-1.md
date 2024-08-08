# Question Paper - 1

## Question 1

#### **1.A)** Discuss any THREE (3) current issues on security in managing databases. (6 MARKS)

1. **Data Breaches:** Unauthorized access to sensitive data, leading to information theft or leaks.
2. **SQL Injection:** Attackers manipulate SQL queries to gain unauthorized access or make unauthorized changes to the database.
3. **Insider Threats:** Employees or users with legitimate access to the database may misuse their privileges, either intentionally or accidentally, causing harm.
4. **Weak Access Controls:** Poor management of user permissions can lead to unauthorized users accessing or modifying sensitive data.
5. **Ransomware Attacks:** Malicious software that locks the database, with attackers demand for a ransom to unlock or restore access to the data.

#### **1.B)** Explain THREE (3) advantages of a Database Management System (DBMS). (6 MARKS)

1. **Data Consistency:** Ensures that data remains consistent across different applications, reducing errors or unusual problems.
2. **Data Security:** Implements security measures like encryption and access controls to protect data from unauthorized access.
3. **Data Sharing:** Allows multiple users to access the database at the same time without causing conflicts, making it easier to work together.
4. **Efficient Data Management:** Improves data storage and retrieval processes, making it easier to manage large amounts of data.
5. **Backup and Recovery:** Provides automatic backup and recovery mechanisms, ensuring data is safe and can be restored in case of failures.

#### **1.C)** Describe THREE (3) functions of a data administrator. (6 MARKS)

1. **Database Design:** Planning the structure of the database, including tables, relationships, and data types to meet user requirements.
2. **Backup and Recovery:** Regularly backing up the database and implementing recovery plans to restore data in case of corruption or failures.
3. **User Access Control:** Managing user permissions and roles to ensure that only authorized users can access or modify certain data.
4. **Data Integrity Management:** Ensuring that the data stored in the database is accurate, consistent, and free from errors.
5. **Performance Monitoring:** Continuously monitoring the database's performance and optimizing queries to ensure it runs efficiently.

***

## Question 2

#### **2.A) Describe the activities performed during the following phases of the database design and development process: (8 MARKS)** i. **Requirement Analysis:**

* Understanding user needs and identifying the data requirements for the database.
* Gathering details on data types, volumes, and the relationships between different data entities.
* Identifying any special requirements, such as security or performance needs.
* Analyzing how data will be accessed and used by different users or applications.
* Creating a detailed document that outlines the database's objectives and requirements.

ii. **Conceptual Database Design:**

* Creating a high-level model of the database, focusing on what data will be stored rather than how it will be stored.
* Defining entities (like customers, products) and their relationships (like a customer places an order).
* Using Entity-Relationship Diagrams (ERDs) to visually represent the database structure.
* Ensuring that the design supports all user requirements identified in the analysis phase.
* Reviewing and refining the conceptual model with stakeholders to ensure it meets all needs.

#### **2.b) Draw an example for the following attributes: (6 MARKS)** i. **Derived attribute:**

* An attribute calculated from other attributes.\
  \- Example: `Age` derived from `Date of Birth`. If the current date is 2024 and the Date of Birth is 2000, then Age is 24.

ii. **Multivalued attribute:**

* An attribute that can have multiple values.
  * Example: A `Person` can have multiple `Phone Numbers` such as Home, Work, and Mobile.

iii. **Composite attribute:**

* An attribute that can be divided into smaller sub-parts.
  * Example: `Full Name` can be divided into `First Name` and `Last Name`.

#### **2.C) Describe the following relationships: (6 MARKS)**

\
i. **Person → Married to → Person:**

* **One-to-One Relationship:** Each person is married to one other person, representing a one-to-one relationship.

ii. **Student → Relationship → Course:**

* **Many-to-Many Relationship:** A student can enroll in many courses, and a course can have many students. This is typically represented using an intermediate table like "Enrollment."

iii. **Doctor → Prescribes → Medicine:**

&#x20;                                 **↓**

&#x20;                           **Patient**

* **Many-to-Many Relationship:** A doctor prescribes medicines to patients. Each prescription involves a doctor, a patient, and the medicine being prescribed. This can be seen as a relationship where one doctor can prescribe many medicines to many patients, and each patient can receive multiple prescriptions. This relationship is managed using an intermediate table that links doctors, patients, and medicines.

## Question 3

#### **3.A) Explain the following terms: (4 MARKS)**

**1. Primary Key**\
A primary key is a unique identifier for a record in a database table. It makes sure that every record is unique and can be easily found. Think of it like a unique ID card number for each person in a class.

**2. Foreign Key**\
A foreign key is a field in one table that links to the primary key in another table. It helps to establish relationships between tables. It’s sometimes called a **referencing key**. Imagine it as a reference number that connects related records in different tables.

**3. Entity Integrity**\
Entity integrity means that every table must have a primary key, and this key must uniquely identify each record. This ensures no record is missing a unique identifier. It’s like making sure every student in a class has a unique student ID.

**4. Referential Integrity**\
Referential integrity ensures that relationships between tables remain consistent. It means that any foreign key value must match an existing primary key value in another table. For example, if a student record references a course, that course must exist in the course table.

#### **3.B) Distinguish between cardinality and degree of a relation with an example: (4 MARKS)**

**Cardinality:** Cardinality refers to the number of tuples (rows) in a relation (table). Example: In the `student` table, if there are 50 rows of student records, the cardinality of the `student` relation is 50.

**Degree:** Degree refers to the number of attributes (columns) in a relation (table). Example: In the `student` table, there are 6 columns: `SN`, `Name`, `Faculty`, `Address`, `Phone_number`, and `Reg_Date`. Therefore, the degree of the `student` relation is 6.

#### **3.C)** The Selangor Stage Coach Co. provides services to the greater Selangor municipal area, including various towns around the state capital.

The company owns a substantial number of buses. Each bus is allocated to a specific route, although some routes may have several buses. Each bus has a unique bus number. It is important to store information about the seating capacity and the make/type of each bus.

Each route, identified by a route number, passes through a number of towns. Several routes may serve the same town. Information is available on the average number of passengers carried per day for each route.

Due to the long traveling time, one or more drivers are assigned to each stage of a route, which corresponds to a journey through a town on a route. Drivers have an employee number, name, address, and sometimes a telephone number.

Read the above description carefully. State appropriate assumptions and devise the corresponding ER model. (12 MARKS)

**Answer:** (padhako xaina 💀💀)



4.) Table 1 - Dentist Patient Appointment

| Dentist\_No | Dentist\_Name | Pat\_No | Pat\_Name | Appointment Date Time | Surgery\_No |
| ----------- | ------------- | ------- | --------- | --------------------- | ----------- |
| 1011        | Zara          | P100    | Aruna     | 12-Jan-17 10:00       | 515         |
| 1011        | Zara          | P105    | Roziana   | 12-Jan-17 12:00       | 515         |
| 1024        | Robin         | P108    | Andrew    | 14-Jan-17 12:00       | 510         |
| 1032        | Wong          | P105    | Aruna     | 12-Jan-17 10:00       | 515         |
| 1032        | Wong          | P108    | Tiagu     | 14-Jan-17 10:00       | 515         |
