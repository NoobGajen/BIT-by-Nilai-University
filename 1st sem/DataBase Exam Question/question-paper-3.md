# Question Paper - 3

### **1. Differentiate between File-Based Systems and Database Management Systems (DBMS)**

| Feature             | File-Based Systems                                                                | Database Management Systems (DBMS)                                                       |
| ------------------- | --------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| **Data Storage**    | Data is stored in individual files, often spread across different locations.      | Data is stored in a centralized database, allowing for easier management.                |
| **Data Redundancy** | High, as the same data might be duplicated across multiple files.                 | Reduced, as data is stored in a single place and managed centrally.                      |
| **Data Access**     | Each application manages its own files, making data sharing difficult.            | Multiple applications can access the same data through the DBMS, promoting data sharing. |
| **Data Integrity**  | Limited, as maintaining consistent data across multiple files can be challenging. | High, as DBMS enforces rules to ensure data consistency.                                 |
| **Security**        | Basic, as security mechanisms are usually application-specific.                   | Strong, with built-in mechanisms for access control and data protection.                 |

### **2. Explain Database Approaches.**   (padhako xaina 💀💀)

1. **Centralized Approach:**
   * All data is kept in one central place, usually on a single database server.
   * It's easier to manage and secure, but it might slow down if too many people try to access it at the same time.
2. **Distributed Approach:**
   * Data is spread out across multiple locations or servers.
   * This increases the system's availability and reliability, but it can be tricky to keep the data consistent across all locations.
3. **Client-Server Approach:**
   * The database is stored on a server, and users connect to it from their computers (clients).
   * This setup lets multiple users access the database at once while keeping management centralized.
4. **Cloud-Based Approach:**
   * Data is stored on cloud servers and accessed online.
   * It offers flexibility, easy scaling, and lower costs for physical infrastructure, but it depends on having a good internet connection.

### **3. Explain Different Roles in DBMS.**

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

### **4. Explain with Figures.**

i. **Simple Attribute:** An attribute that cannot be broken down into smaller parts.&#x20;

Example: `Employee ID` is a simple attribute because it represents a unique identifier that stands on its own without being divided further.

ii. **Multivalued Attribute:** An attribute that can have multiple values.&#x20;

Example: A `Person` can have multiple `Phone Numbers` such as Home, Work, and Mobile.

iii. **Composite Attribute:** An attribute that can be divided into smaller sub-parts.

Example: `Full Name` can be divided into `First Name` and `Last Name`.

iv. **Derived Attribute:** An attribute calculated from other attributes.&#x20;

Example: `Age` derived from `Date of Birth`. If the current date is 2024 and the Date of Birth is 2000, then Age is 24.



## Question 5

***

**Students**

| S\_ID | S\_name | S\_percentage | D\_ID |
| ----- | ------- | ------------- | ----- |
| s1    | Rihana  | 70            | d1    |
| s2    | Tom     | 30            | d1    |
| s3    | Jack    | 40            | NULL  |
| s4    | Donald  | 50            | d3    |
| s5    | Shakira | 69            | d3    |

***



**Departments**

| D\_ID | D\_name   |
| ----- | --------- |
| d1    | math      |
| d2    | physics   |
| d3    | english   |
| d4    | computer  |
| d5    | economics |

***



**Faculty**

| F\_ID | F\_name | D\_ID |
| ----- | ------- | ----- |
| f1    | Tin     | d1    |
| f2    | Jach    | d2    |
| f3    | Den     | d3    |
| f4    | Nik     | d4    |
| f5    | Tommy   | NULL  |

**Answer:**

### **A. Create above Tables.**

```sql
-- Creating Students table
CREATE TABLE Students (
    S_ID VARCHAR(3) PRIMARY KEY,    
    S_name VARCHAR(255) NOT NULL,  
    S_percentage INT,     
    D_ID VARCHAR(3)                
);

-- Creating Departments table
CREATE TABLE Departments (
    D_ID VARCHAR(3) PRIMARY KEY,    
    D_name VARCHAR(255) NOT NULL   
);

-- Creating Faculty table
CREATE TABLE Faculty (
    F_ID VARCHAR(3) PRIMARY KEY,   
    F_name VARCHAR(255),           
    D_ID VARCHAR(3)                
);
```

### **B. Insert Values into the Tables.**

```sql
-- Insert values into Students table
INSERT INTO Students (S_ID, S_name, S_percentage, D_ID) VALUES 
('s1', 'Rihana', 70, 'd1'),
('s2', 'Tom', 30, 'd1'),
('s3', 'Jack', 40, NULL),
('s4', 'Donald', 50, 'd3'),
('s5', 'Shakira', 69, 'd3');

-- Insert values into Departments table
INSERT INTO Departments (D_ID, D_name) VALUES 
('d1', 'math'),
('d2', 'physics'),
('d3', 'english'),
('d4', 'computer'),
('d5', 'economics');

-- Insert values into Faculty table
INSERT INTO Faculty (F_ID, F_name, D_ID) VALUES 
('f1', 'Tin', 'd1'),
('f2', 'Jack', 'd2'),
('f3', 'Den', 'd3'),
('f4', 'Nik', 'd4'),
('f5', 'Tommy', NULL);
```

### **C. List Student with Highest, Average and Minimum Percentage.**

```sql
-- Listing students with the highest percentage
SELECT S_name, S_percentage AS Highest_Percentage
FROM Students
WHERE S_percentage = (SELECT MAX(S_percentage) FROM Students);

-- Listing students with the average percentage
SELECT AVG(S_percentage) AS Average_Percentage
FROM Students;

-- Listing students with the minimum percentage
SELECT S_name, S_percentage AS Minimum_Percentage
FROM Students
WHERE S_percentage = (SELECT MIN(S_percentage) FROM Students);
```

<figure><img src=".gitbook/assets/Question Paper 3 5.C.png" alt=""><figcaption></figcaption></figure>

### **D. Find Students Who Are Studying in the English Department.**

```sql
-- Finding students in the English department by using subquery method.
SELECT S_name, S_percentage
FROM Students
WHERE D_ID = (SELECT D_ID FROM Departments WHERE D_name = 'english');

-- Finding students in the English department by using join method.  (padhako xaina 💀💀)
SELECT S_name, S_percentage
FROM Students
JOIN Departments ON Students.D_ID = Departments.D_ID
WHERE Departments.D_name = 'english';
```

<figure><img src=".gitbook/assets/Question Paper 3 5.D.png" alt=""><figcaption></figcaption></figure>

### **E. List Students Who Secured Between 60 and 100 Percentage.**

```sql
-- List students with percentage between 60 and 100
SELECT S_name, S_percentage
FROM Students
WHERE S_percentage BETWEEN 60 AND 100;
```

<figure><img src=".gitbook/assets/Question Paper 3 5.E.png" alt=""><figcaption></figcaption></figure>

### **F. List Number of Students Who Study in Each Department.** (padhako xaina 💀💀)

```sql
-- Counting number of students in each department
SELECT d.D_name AS Department_name, COUNT(*) AS Student_count
FROM Students AS s
JOIN Departments AS d ON s.D_ID = d.D_ID
GROUP BY d.D_name;
```

<figure><img src=".gitbook/assets/Question Paper 3 5.F.png" alt=""><figcaption></figcaption></figure>

### **G. List Student Details and Department Name.**  (padhako xaina 💀💀)

```sql
-- Finding student details and their department names using join method  (padhako xaina 💀💀)
SELECT Students.S_ID, Students.S_name, Students.S_percentage, Departments.D_name
FROM Students
LEFT JOIN Departments ON Students.D_ID = Departments.D_ID;
```

<figure><img src=".gitbook/assets/Question Paper 3 5.G.png" alt=""><figcaption></figcaption></figure>
