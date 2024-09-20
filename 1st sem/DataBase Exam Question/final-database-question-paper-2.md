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

### a) Draw the complete entity-relationship (ER) diagram by showing the type of relationships between entities and cardinality constraints for the scenario above.



