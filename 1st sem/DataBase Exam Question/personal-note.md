# Personal Note

### **Database Approach (DBMS)** vs **File-Based Approach** (Ordered by Importance)

1. **Data Integrity**
   * **DBMS**: Ensures high data integrity with rules and constraints to keep the data accurate and consistent across the system.
   * **File-Based**: Maintaining data accuracy is difficult due to the risk of data duplication and inconsistency between files.
2. **Security**
   * **DBMS**: Offers strong security with built-in access control, user authentication, and data protection features.
   * **File-Based**: Security is weak and usually relies on each application, making it harder to protect data effectively.
3. **Data Redundancy**
   * **DBMS**: Reduces data duplication because data is stored centrally and managed consistently.
   * **File-Based**: High data redundancy due to duplication of data across multiple files, leading to inconsistency and wasted space.
4. **Data Sharing**
   * **DBMS**: Supports efficient data sharing among multiple users and applications. Different users can access and manipulate data concurrently without issues.
   * **File-Based**: Limited data sharing. If multiple users try to access or modify the same file, it can lead to issues like data corruption or loss.
5. **Data Centralization**
   * **DBMS**: Data is stored in a centralized system, allowing multiple users and applications to access the same data easily.
   * **File-Based**: Data is stored in separate files across different locations, making access and management more difficult.

### Database Administrator (DBA) vs Data Administrator (DA)

#### Database Administrator (DBA)

The person responsible for the technical management, maintenance, day-to-day operation, and security of an organization's database management system is known as a Database Administrator (DBA).

Some functions of a Database Administrator are:

* **Database Installation & Configuration:** Setting up database servers and software by ensuring it meets the organization's needs.
* **Performance Monitoring and Tuning:** Ensuring the database runs efficiently and can handle the required workloads.
* **Backup and Recovery:** Planning and implementing backup strategies to protect data from loss and facilitate recovery in case of failure.
* **Security Management:** Controlling access to the database and protecting data from unauthorized access.
* **Troubleshooting:** Diagnosing and resolving database-related issues.

#### Data Administrator (DA)

The person responsible for managing data governance, policies, data quality, and ensuring that data is properly maintained and used within an organization is known as a **Data Administrator (DA)**.

Some functions of a Data Administrator are:

* **Data Governance & Policy Development**: Establishing and enforcing rules, standards, and policies for how data is created, stored, and accessed within the organization.
* **Data Integrity & Quality Control**: Ensuring the accuracy, consistency, and reliability of data across all systems by implementing validation rules and maintaining high data quality standards.
* **Data Access Management**: Controlling who has access to data and ensuring that sensitive data is protected from unauthorized access, while allowing the right people to access the right information.
* **Data Lifecycle Management**: Overseeing the entire lifecycle of data, from creation and storage to archiving and deletion, ensuring that data is managed in compliance with legal and organizational requirements.
* **Ensuring Data Consistency**: Implementing strategies to prevent data duplication or inconsistency across different systems, ensuring that all data used by the organization is up-to-date and reliable.

### [**Explain Different Roles in DBMS.**](semi-question-paper-3.md#id-3.-explain-different-roles-in-dbms)

1. **Data Administrator (DA).**
   * The person who is responsible for the overall management and strategic use of data of an organization, ensuring its quality, consistency, and accessibility across the entire organization.
   * They are also responsible for developing data policies, data planning, data quality management, metadata management, and data security.
2. **Database Administrator (DBA).**
   * The person who is responsible for the technical management, maintenance, day-to-day operations, and security of an organization's database management system (DBMS).
   * They manage the overall database environment and are responsible for tasks such as backups and recovery, security, performance tuning, and ensuring the database runs smoothly.
3. **Logical Database Designer.**
   * The person who is responsible for designing the conceptual or logical representation of the database structure, focusing on the organization of data without considering physical implementation details like file storage, indexing, or performance optimization.
   * They handle data modeling, schema design, normalization, and user requirements analysis.
4. **Physical Database Designer:**
   * The person who is responsible for implementing the logical database design into a physical structure, determining how data will be stored and accessed in the actual database management system (DBMS).
   * They are responsible for physical schema design, storage management, performance optimization, and implementation.
5. **Application Developer.**
   * The person who is responsible for developing software applications that interact with the database, implementing business logic and user interfaces for data manipulation and retrieval.
   * They are also responsible for requirements analysis, database interaction, application design, testing and debugging, and integration.
6. **End Users.**
   * The individuals or groups who interact with the database through applications or interfaces to perform their job functions or access information.
   * They perform tasks such as data entry, data retrieval, updates, and providing feedback.

### Data Anomalies

**Example Table: Student\_Course\_Instructor**

| Student\_ID | Student\_Name | Course\_ID | Course\_Name    | Instructor\_ID | Instructor\_Name |
| ----------- | ------------- | ---------- | --------------- | -------------- | ---------------- |
| 1           | Gajendra      | C101       | Math            | 10             | Rupesh Bhandari  |
| 2           | Diwash        | C101       | Networking      | 10             | Rupesh Bhandari  |
| 3           | Sandesh       | C102       | Science         | 11             | Kreepa Sharma    |
| 4           | Gajendra      | C103       | IT Fundamentals | 12             | Kreepa Sharma    |
| 5           | Diwash        | C104       | Database        | 13             | Rupesh Bhandari  |
| 6           | Sandesh       | C105       | Public Speaking | 14             | Bijay Gautam     |

**1. Insertion Anomaly**

An insertion anomaly occurs when we cannot add new data without including unrelated information.

**Example**: Suppose **Bijay Gautam** is hired to teach a new course called **Advanced Public Speaking**. If no students are enrolled in this course yet, we cannot add Bijay to the table without also needing to add a student record, which is unnecessary at that time.

**Illustration**:

* To add **Bijay Gautam** as an instructor for **C106** (Advanced Public Speaking), we would have to create an entry like this:

| Student\_ID | Student\_Name | Course\_ID | Course\_Name             | Instructor\_ID | Instructor\_Name |
| ----------- | ------------- | ---------- | ------------------------ | -------------- | ---------------- |
| NULL        | NULL          | C106       | Advanced Public Speaking | 15             | Bijay Gautam     |

**2. Deletion Anomaly**

A deletion anomaly occurs when removing one piece of data also removes other important information.

**Example**: If we delete the record for **Gajendra** because he drops **Math**, we also lose information about the **Math** instructor, **Rupesh Bhandari**.

**Illustration**:

* If we delete Gajendra’s record, this row will be removed:

| Student\_ID | Student\_Name | Course\_ID | Course\_Name | Instructor\_ID | Instructor\_Name |
| ----------- | ------------- | ---------- | ------------ | -------------- | ---------------- |
| 1           | Gajendra      | C101       | Math         | 10             | Rupesh Bhandari  |

* Since Rupesh is the only instructor listed for Math, we would lose this information completely.

**3. Update Anomaly**

An update anomaly happens when we need to change information in multiple places, and if we miss one, it can create confusion.

**Example**: If **Rupesh Bhandari** decides to change his title to **Dr. Rupesh Bhandari**, we need to update this in every record where he is listed. If we forget to update it in some places, it can lead to inconsistencies.

**Illustration**:

* If we change Rupesh’s title in one record but forget to change it in another, the table could look like this:

| Student\_ID | Student\_Name | Course\_ID | Course\_Name | Instructor\_ID | Instructor\_Name    |
| ----------- | ------------- | ---------- | ------------ | -------------- | ------------------- |
| 1           | Gajendra      | C101       | Math         | 10             | Dr. Rupesh Bhandari |
| 2           | Diwash        | C101       | Networking   | 10             | Rupesh Bhandari     |

**Summary**

* **Insertion Anomaly**: We struggle to add new instructors without needing unrelated student data (e.g., adding Bijay for a course without students).
* **Deletion Anomaly**: Removing one student can also remove important instructor information (e.g., deleting Gajendra removes Rupesh’s info).
* **Update Anomaly**: If we need to change a title in multiple places but forget some, we create inconsistencies (e.g., different titles for Rupesh).
