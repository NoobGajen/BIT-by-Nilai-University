# Question Paper - 2

## Question 1

### 1.A.) Discuss any THREE (3) current threats of modern databases. (6 MARKS)

1. **SQL Injection:** Attackers manipulate SQL queries to gain unauthorized access or make unauthorized changes to the database.
2. **Insider Threats:** Employees or users with legitimate access to the database may misuse their privileges, either intentionally or accidentally, causing harm.
3. **Ransomware Attacks:** Malicious software that locks the database, with attackers demand for a ransom to unlock or restore access to the data.
4. **Weak Access Controls:** Poor management of user permissions can lead to unauthorized users accessing or modifying sensitive data.
5. **Data Breaches:** Unauthorized access to sensitive data, leading to information theft or leaks.

### 1.B.) Explain data redundancy with an example. (6 MARKS)

**Data Redundancy:**

* Data redundancy occurs when the same piece of data is stored in multiple places within a database.
* This can lead to inconsistencies, as updating data in one place might not update it everywhere else.
* It also wastes storage space, making the database less efficient.

**Example:**

* Imagine a university database that stores student information.
* If a student's address is stored in both the "Students" table and the "Enrollment" table, that's data redundancy.
* If the student moves and only one table is updated with the new address, the database will have conflicting information, leading to errors.

### 1.C.) Describe any FOUR (4) functions of a database administrator. (8 MARKS)

The person responsible for the technical management, maintenance, day-to-day operation, and security of an organization's database management system is known as a Database Administrator (DBA).

Some functions of a Database Administrator are:

* **Database Installation & Configuration:** Setting up database servers and software by ensuring it meets the organization's needs.
* **Performance Monitoring and Tuning:** Ensuring the database runs efficiently and can handle the required workloads.
* **Backup and Recovery:** Planning and implementing backup strategies to protect data from loss and facilitate recovery in case of failure.
* **Security Management:** Controlling access to the database and protecting data from unauthorized access.
* **Troubleshooting:** Diagnosing and resolving database-related issues.

## Question 5

### 5.A.) Define the function of each clauses listed below: (5 MARKS)

#### **i. WHERE**

The `WHERE` clause is used to filter rows in a database query based on a specific condition. It only shows the rows that meet the given criteria. **Example:** `SELECT * FROM Employees WHERE Age > 30;` retrieves all employees older than 30.

#### **ii. GROUP BY**

The `GROUP BY` clause groups rows that have the same values in specified columns into summary rows, like totals or counts. It's often used with aggregate functions like `COUNT`, `SUM`, `AVG`, etc. **Example:** `SELECT Department, COUNT(*) FROM Employees GROUP BY Department;` counts the number of employees in each department.

#### **iii. HAVING**

The `HAVING` clause is used to filter the results of aggregated data that is grouped by the `GROUP BY` clause. It sets conditions on the grouped rows, similar to how `WHERE` sets conditions on individual rows. **Example:** `SELECT Department, COUNT(*) as count FROM Employees GROUP BY Department HAVING count > 10;` shows departments with more than 10 employees.

#### **iv. FULL OUTER JOIN** (padhako xaina)&#x20;

The `FULL OUTER JOIN` clause returns all records when there is a match in either the left or right table. If there is no match, it returns `NULL` for the missing data. It combines the results of both `LEFT JOIN` and `RIGHT JOIN`. **Example:** `SELECT * FROM Employees FULL OUTER JOIN Departments ON Employees.Department_ID = Departments.Department_ID;` returns all employees and all departments, including those with no matching records.

#### **v. NATURAL JOIN** (padhako xaina)&#x20;

The `NATURAL JOIN` clause automatically joins two tables based on columns with the same name in both tables. It simplifies the join process by using these common columns as the join condition. **Example:** `SELECT * FROM Employees NATURAL JOIN Departments;` joins the `Employees` and `Departments` tables using columns that have the same name in both tables, like `Department_ID`.

### 5.B.) Write SQL Statement for the following queries referring to table 2:

&#x20;                                                         **Table no. 2:** Customer

| CustomerID | CustomerName                       | ContactName        | Address                       | City        | PostalCode | Country |
| ---------- | ---------------------------------- | ------------------ | ----------------------------- | ----------- | ---------- | ------- |
| 1          | Alfreds Futierkiste                | Maria Anders       | Obere Str. 57                 | Berlin      | 12209      | Germany |
| 2          | Ana Trujillo Emparedados y Helados | Ana Trujillo       | Avda. de la Constitución 2222 | Mexico City | 05021      | Mexico  |
| 3          | Antonio Moreno Taqueria            | Antonio Moreno     | Mataderos 2312                | Mexico City | 05023      | Mexico  |
| 4          | Around the Horn                    | Thomas Hardy       | 120 Hanover Sq.               | London      | WA1 1DP    | UK      |
| 5          | Berglunds snabbkop                 | Christina Berglund | Berguvsvägen 8                | Luleå       | S-958 22   | Sweden  |

### **i. Select all customers with a `CustomerName` that has "r" in the second position.**

```sql
SELECT * 
FROM Customer 
WHERE CustomerName LIKE '_r%';
```

<figure><img src=".gitbook/assets/Question Paper 2 5.B.i.png" alt=""><figcaption></figcaption></figure>

### **ii. Select all customers from the `Customer` table, sorted ascending by the `Country` and descending by the `CustomerName` column.**

```sql
SELECT * 
FROM Customer 
ORDER BY Country ASC, CustomerName DESC;
```

<figure><img src=".gitbook/assets/Question Paper 2 5.B.ii.png" alt=""><figcaption></figcaption></figure>

### **iii. Insert a new record in the `Customer` table.**

```sql
INSERT INTO Customer (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country) 
VALUES (6, 'Diwash Bist', 'BistDiwash', 'Naxal', 'Pokhara', '12345', 'Nepal');
```

<figure><img src=".gitbook/assets/Question Paper 2 5.B.iii.png" alt=""><figcaption></figcaption></figure>

### **iv. List the number of customers in each country.**

```sql
SELECT Country, COUNT(*) AS NumberOfCustomer 
FROM Customer 
GROUP BY Country;
```

<figure><img src=".gitbook/assets/Question Paper 2 5.B.iv.png" alt=""><figcaption></figcaption></figure>

### **v. Update the first customer (`CustomerID = 1`) with a new contact person and a new city.**

```sql
UPDATE Customer 
SET ContactName = 'Gajendra Mahato', City = 'Kathmandu' 
WHERE CustomerID = 1;
```

<figure><img src=".gitbook/assets/Question Paper 2 5.B.v.png" alt=""><figcaption></figcaption></figure>

### **vi. List the number of customers in each country. Only include countries with more than 5 customers.**

```sql
SELECT Country, COUNT(*) AS NumberOfCustomers 
FROM Customer 
GROUP BY Country 
HAVING NumberOfCustomers > 5;
```
