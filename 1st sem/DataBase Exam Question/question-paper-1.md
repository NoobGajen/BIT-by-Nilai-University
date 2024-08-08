# Question Paper - 1

## Question 1

**1.A)** Discuss any THREE (3) current issues on security in managing databases. (6 MARKS)

1. **Data Breaches:** Unauthorized access to sensitive data, leading to information theft or leaks.
2. **SQL Injection:** Attackers manipulate SQL queries to gain unauthorized access or make unauthorized changes to the database.
3. **Insider Threats:** Employees or users with legitimate access to the database may misuse their privileges, either intentionally or accidentally, causing harm.
4. **Weak Access Controls:** Poor management of user permissions can lead to unauthorized users accessing or modifying sensitive data.
5. **Ransomware Attacks:** Malicious software that locks the database, with attackers demand for a ransom to unlock or restore access to the data.

**1.B)** Explain THREE (3) advantages of a Database Management System (DBMS). (6 MARKS)

1. **Data Consistency:** Ensures that data remains consistent across different applications, reducing errors or unusual problems.
2. **Data Security:** Implements security measures like encryption and access controls to protect data from unauthorized access.
3. **Data Sharing:** Allows multiple users to access the database at the same time without causing conflicts, making it easier to work together.
4. **Efficient Data Management:** Improves data storage and retrieval processes, making it easier to manage large amounts of data.
5. **Backup and Recovery:** Provides automatic backup and recovery mechanisms, ensuring data is safe and can be restored in case of failures.

**1.C)** Describe THREE (3) functions of a data administrator. (6 MARKS)

1. **Database Design:** Planning the structure of the database, including tables, relationships, and data types to meet user requirements.
2. **Backup and Recovery:** Regularly backing up the database and implementing recovery plans to restore data in case of corruption or failures.
3. **User Access Control:** Managing user permissions and roles to ensure that only authorized users can access or modify certain data.
4. **Data Integrity Management:** Ensuring that the data stored in the database is accurate, consistent, and free from errors.
5. **Performance Monitoring:** Continuously monitoring the database's performance and optimizing queries to ensure it runs efficiently.

***

## Question 2

**2.A) Describe the activities performed during the following phases of the database design and development process:**\
i. **Requirement Analysis:**

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

**2.b) Draw an example for the following attributes:**\
i. **Derived attribute:**

* An attribute calculated from other attributes.\
  \- Example: `Age` derived from `Date of Birth`. If the current date is 2024 and the Date of Birth is 2000, then Age is 24.

ii. **Multivalued attribute:**

* An attribute that can have multiple values.
  * Example: A `Person` can have multiple `Phone Numbers` such as Home, Work, and Mobile.

iii. **Composite attribute:**

* An attribute that can be divided into smaller sub-parts.
  * Example: `Full Name` can be divided into `First Name` and `Last Name`.

**2.C) Describe the following relationships:**

\
i. **Person → Married to → Person:**

* **One-to-One Relationship:** Each person is married to one other person, representing a one-to-one relationship.

ii. **Student → Relationship → Course:**

* **Many-to-Many Relationship:** A student can enroll in many courses, and a course can have many students. This is typically represented using an intermediate table like "Enrollment."

iii. **Doctor → Prescribes → Medicine:**

&#x20;                                 **↓**

&#x20;                           **Patient**

* **Many-to-Many Relationship:** A doctor can prescribe many medicines to different patients, and each medicine can be prescribed by multiple doctors.
