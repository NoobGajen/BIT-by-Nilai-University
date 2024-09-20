# Final - Database Question Paper - 1

## **Question 1**

**SP Bumi Transport** has decided to build a database to help manage its operations. It is interested in keeping track of Its buses, The terminals to which buses stop, Passengers and the trips they have taken, Its employees, and data about the Maintenance of its buses.

### a.) Using this introductory description of (and hints about) the SP Bumi Transport, make a list of the \*\*SEVEN (7) things in the company's environment about which the company would want to maintain data.                                                                                                    **(7 MARKS)**



**Answer:-**

The list of the seven things in SP Bumi Transport's environment about which the company would want to maintain data are:

1. **Buses**\
   SP Bumi Transport would need to track all its buses. This includes information like:
   * Bus number or ID
   * Bus model and capacity
   * Date of purchase, service, or maintenance
2. **Terminals**\
   The company needs to track the terminals where its buses stop. This could include:
   * Terminal names
   * Locations (addresses)
   * Available services at each terminal (like ticket counters, waiting areas, etc.)
3. **Trips**\
   Each bus makes multiple trips. SP Bumi would need to store details about these trips, such as:
   * Trip ID
   * Start and end locations (from which terminal to which)
   * Date and time of the trip
4. **Passengers**\
   The company would want to keep records of its passengers who travel on the buses. Important details would be:
   * Passenger name and contact information
   * Ticket information (ticket number, price, seat)
   * The trip they took (linking to the "Trips" entity)
5. **Employees**\
   SP Bumi will have employees like drivers, ticket sellers, maintenance staff, etc. They need to maintain data on these employees, such as:
   * Employee ID
   * Name and contact details
   * Job role (driver, cleaner, etc.)
   * Employment start date
6. **Bus Maintenance**\
   Buses need regular maintenance to stay safe and reliable. SP Bumi would store details like:
   * Maintenance ID
   * Maintenance date
   * Maintenance type (e.g., engine check, tire change)
   * Mechanic involved
7. **Ticket Sales**\
   For managing revenue and operations, tracking ticket sales is important. This includes:
   * Ticket ID
   * Price of the ticket
   * Date of purchase
   * Payment method (cash, card, etc.)



### b.) Suggest THREE (3) reports that SP Bumi Transport could use to improve its operations and gain a competitive advantage?                                                                                                     (**6 MARKS)**

**Answer:-**

Three reports that SP Bumi Transport could use to improve its operations and gain a competitive advantage are:

1. **Bus Performance and Maintenance Report**\
   This report tracks the performance of each bus, including fuel consumption, breakdowns, and maintenance history.
   * **Benefit**: By regularly monitoring the performance, SP Bumi can ensure their buses are reliable, reducing downtime and repair costs. It will also help them schedule preventive maintenance, keeping the buses in good condition.
2. **Passenger Trip Report**\
   This report contains details about passengers, such as how frequently they travel, which routes they prefer, and their feedback (if available).
   * **Benefit**: With this report, SP Bumi can analyze passenger travel patterns and preferences, allowing them to offer better services, adjust routes, or launch promotions. This improves customer satisfaction and retention.
3. **Revenue and Ticket Sales Report**\
   This report focuses on ticket sales, covering total revenue, ticket types (e.g., one-way, round-trip), and payment methods used (cash, card, etc.).
   * **Benefit**: By tracking ticket sales and revenue, SP Bumi can identify which routes are most profitable and adjust pricing or services accordingly. It will also help in financial planning and identifying areas to increase revenue.



### c.) Describe the **THREE(3)** main characteristics of the database approach and contrast it with the file-based approach.                                                                                                    **(6 MARKS)**

**Answer:-**

Three main characteristics of the database approach and contrast with the file-based approach:



| **Characteristic**         | **Database Approach (DBMS)**                                                                                       | **File-Based Approach**                                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------- |
| **1. Data Centralization** | Data is stored in a centralized system, allowing multiple users and applications to access the same data easily.   | Data is stored in separate files across different locations, making access and management more difficult.         |
| **2. Data Integrity**      | Ensures high data integrity with rules and constraints to keep the data accurate and consistent across the system. | Maintaining data accuracy is difficult due to the risk of data duplication and inconsistency between files.       |
| **3. Data Independence**   | Physical storage and data access are separate, meaning changes in data structure don’t affect applications.        | File structures are closely tied to applications, so changes can break the way programs access and use the data.  |
| **4. Security**            | Offers strong security with built-in access control, user authentication, and data protection features.            | Security is weak and usually relies on each application, making it harder to protect data effectively.            |
| **5. Data Redundancy**     | Reduces data duplication because data is stored centrally and managed consistently.                                | High data redundancy due to duplication of data across multiple files, leading to inconsistency and wasted space. |





### d.) Explain the differences of **Data Definition Language (DDL)** and **Data Manipulation Language (DML)**.                                                                                                    **(6 MARKS)**



**Answer:-**

The differences between **Data Definition Language (DDL)** and **Data Manipulation Language (DML) are:**



| **Feature**                | **Data Definition Language (DDL)**                                               | **Data Manipulation Language (DML)**                                          |
| -------------------------- | -------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| **1. Definition**          | A set of SQL commands used to create, modify, and delete database structures.    | A set of SQL commands used to manage and modify data within a database.       |
| **2. Purpose**             | To define and manage the schema of the database (structure).                     | To manipulate and manage the actual data stored in the database.              |
| **3. Examples**            | - **CREATE**: Creates new database objects.                                      | - **INSERT**: Adds new rows of data into a table.                             |
|                            | - **ALTER**: Modifies existing database objects.                                 | - **UPDATE**: Modifies existing data within a table.                          |
|                            | - **DROP**: Deletes existing database objects.                                   | - **DELETE**: Removes rows from a table based on specified conditions.        |
| **4. Transaction Control** | DDL statements are usually auto-committed and cannot be rolled back.             | DML statements can be rolled back or committed, allowing transaction control. |
| **5. Usage**               | Typically used by database administrators or applications, not by regular users. | Commonly used by both users and applications to interact with data.           |

## **Question 2** <a href="#question-1" id="question-1"></a>

### a.) Read the following description carefully. State appropriate assumptions and devise the corresponding EAR model:                                                                                                     **(15 MARKS)**

The Selangor Stage Coach Co. provides services to the greater Selangor municipal, including various towns around the state capital.&#x20;

It owns a substantial number of buses. Each bus is allocated to a particular route, although some routes may have several buses. Each bus has a unique bus number. It Is Important to store information about the seating capacity and the make/type of all buses.&#x20;

Each route, distinguish by a route number, passes through a number of towns. Several routes may serve the same town. Information Is available on the average number of passengers carried per day for each route.&#x20;

Due to long travelling time, one or more drivers are assigned to each stage of a route, which corresponds to a journey through a town on a route. Drivers have an employee number, name, address and sometimes a telephone number.

**Answer:-**

**Assumptions for Entity-Relationship (ER) model**

1. Each bus can only be assigned to one route at a time, but multiple buses can operate on the same route.
   1. Each route can serve multiple towns.
   2. Each town can be served by multiple routes.
   3. A driver can be assigned to multiple journeys but can work on one stage at a time.
   4. Average daily passengers for each route are based on historical data.



**Entities for Entity-Relationship (ER) model**

1. **Bus**
   * Entities:
     * Bus Number (Primary Key)
     * Seating Capacity
     * Make/Type
2. **Route**
   * Entities:
     * Route Number (Primary Key)
     * Average Passengers Carried Per Day
3. **Town**
   * Entities:
     * Town Name (Primary Key)
     * Location (Optional)
4. **Driver**
   * Entities:
     * Employee Number (Primary Key)
     * Name
     * Address
     * Telephone Number (Optional)
5. **Journey** (to represent the stages of a route through towns)
   *   Entities:

       * Journey ID (Primary Key)
       * Route Number (Foreign Key)
       * Town Name (Foreign Key)



**Relationships for Entity-Relationship (ER) model**

1. **Bus to Route**:
   * One-to-Many (One route can have multiple buses; each bus belongs to one route)
2. **Route to Town**:
   * Many-to-Many (A route passes through multiple towns, and towns can be served by multiple routes)
3. **Driver to Journey**:
   * One-to-Many (One driver can be assigned to multiple journeys, but each journey has specific drivers for that segment)



### b.) Devise a relational database schema to demonstrate how you will map your EAR model in (a) onto tables in a relational database. Identify the primary keys / foreign keys in each entity.                                                                                                    **(10 MARKS)**



**Answer:-**

1. **Bus Table**
   * **Primary Key**: Bus\_Number
   * **Attributes**:
     * Seating\_Capacity
     * Make\_Type
2. **Route Table**
   1. **Primary Key**: Route\_Number
   2. **Attributes**:
      * Average\_Passengers
3. **Town Table**
   1. **Primary Key**: Town\_Name
   2. **Attributes**:
      * Location
4. **Driver Table**
   1. **Primary Key**: Employee\_Number
   2. **Attributes**:
      * Name
        * Address
        * Telephone\_Number
5. **Journey Table**
   1. **Primary Key**: Journey\_ID
   2. **Foreign Keys**:
      * Route\_Number references Route(Route\_Number)
      * Town\_Name references Town(Town\_Name)
      * Driver\_Employee\_Number references Driver(Employee\_Number)



## Question 3&#x20;

Table 1 shows list of dentist / patient appointment data. A patient Is given an appointment at a specific time and date with a dentist located at a particular surgery. On each day of patient's appointments, a dentist is allocated to a specific surgery for that day.



| Staff\_No | Dentist\_Name | Pat\_No | Pat\_Name | Appointment\_date\_time | Surgery\_No |
| --------- | ------------- | ------- | --------- | ----------------------- | ----------- |
| S1011     | Zara          | P100    | Roiana    | 12-Sep-17 10:00         | S15         |
| S1011     | Zara          | P105    | Tiagu     | 12-Sep-17 12:00         | S15         |
| S1024     | Aruna         | P108    | Andrew    | 12-Sep-17 10:00         | S10         |
| S1024     | Aruna         | P105    | Andrew    | 14-Sep-17 12:00         | S10         |
| S1032     | Robin         | P105    | Wong      | 14-Sep-17 10:00         | S15         |



### a.) The shown Table is susceptible to update anomalies. Provide **ONE (1)** example of insertion, deletion and update anomalies.                                                                                                    **(6 MARKS)**

**Answer:-**

Here are examples of insertion, deletion, and update anomalies based on the provided dentist-patient appointment table:

1.  **Insertion Anomaly** If a new dentist is hired (e.g., Dr. Smith) but has not yet seen any patients, we cannot add their information to the table without also adding a dummy appointment for them. This leads to redundant data or inaccurate entries in the appointment records.

    **Example:**

    * Attempting to insert Dr. Smith's details:
      * Staff\_No: S1040
      * Dentist\_Name: Smith
      * Pat\_No: (no patient assigned yet)
      * Pat\_Name: (no patient assigned yet)
      * Appointment\_Date\_Time: (needs a dummy date/time)
      * Surgery\_No: S20
    *   **Deletion Anomaly** If we delete a patient's appointment (e.g., Roiana's appointment with Dr. Zara), we might unintentionally lose the information about the dentist (Dr. Zara) if that was the only appointment recorded for them.

        **Example:**

        * Deleting Roiana's appointment:
          * Row: (S1011, Zara, P100, Roiana, 12-Sep-17 10:00, S15)
          * Result: If this is the only record for Dr. Zara, we lose all information about Dr. Zara.
    *   **Update Anomaly**&#x20;

        If a dentist's information (e.g., their name or surgery number) changes, we must update every record where that dentist appears. If we forget to update some records, it leads to inconsistencies in the data.

        **Example:**

        * Updating Dr. Zara's surgery number from S15 to S25:
          * We must update all entries with Dr. Zara’s information. If we miss one:
            * Staff\_No: S1011, Dentist\_Name: Zara, Surgery\_No: S15 (old information)
            * Staff\_No: S1011, Dentist\_Name: Zara, Surgery\_No: S25 (updated information)



### b.) Illustrate the process of normalizing Table 1 to 3NF relations. Identify the primary key, alternate and foreign keys in your 3NF relations.                                                                                                    **(14 MARKS)**

**Answer:-**

**Normalization Process from 1NF to 3NF**

1. **First Normal Form (1NF)**:
   * **Atomic Values**: Each column must contain atomic (indivisible) values, meaning that each value is a single piece of data.
   * **No Repeating Groups**: There should be no columns that contain multiple values or arrays. If any row includes several values for the same attribute, we need to restructure the table.
   * **Unique Rows**: Each row must be uniquely identifiable. This often involves creating a primary key to ensure that no two rows are identical.
2. **Second Normal Form (2NF)**:
   * **Full Dependency**: All non-key attributes must be fully dependent on the entire primary key. This prevents partial dependency, where a non-key attribute depends on only part of a composite primary key.
   * **Elimination of Redundancy**: By separating out non-key attributes that are only partially dependent on the primary key, we reduce redundancy, ensuring that changes to data only need to be made in one place.
   * **Separate Tables for Related Data**: If a non-key attribute is related to a subset of the primary key, it should be moved to a new table that captures that relationship.
3.  **Third Normal Form (3NF)**:

    * **No Transitive Dependencies**: Non-key attributes must not depend on other non-key attributes. Each non-key attribute should depend only on the primary key, ensuring a clearer structure.
    * **Streamlined Data Integrity**: By eliminating transitive dependencies, we enhance data integrity, meaning that the accuracy and consistency of data are maintained across the database.
    * **Improved Query Performance**: With well-structured tables that adhere to 3NF, database queries become more efficient, as each table contains relevant and directly related data.



**Normalization Table from 1NF to 3NF**

**Step 1: 1NF (First Normal Form)** 1NF requires that all attributes are atomic (indivisible). Our table already meets this requirement. So, No changes are needed here.

| Staff\_No | Dentist\_Name | Pat\_No | Pat\_Name | Appointment\_Date\_Time | Surgery\_No |
| --------- | ------------- | ------- | --------- | ----------------------- | ----------- |
| S1011     | Zara          | P100    | Roiana    | 12-Sep-17 10:00         | S15         |
| S1011     | Zara          | P105    | Tiagu     | 12-Sep-17 12:00         | S15         |
| S1024     | Aruna         | P108    | Andrew    | 12-Sep-17 10:00         | S10         |
| S1024     | Aruna         | P105    | Andrew    | 14-Sep-17 12:00         | S10         |
| S1032     | Robin         | P105    | Wong      | 14-Sep-17 10:00         | S15         |

**Step 2: 2NF (Second Normal Form)** 2NF requires that all non-key attributes are fully functionally dependent on the primary key. In this case, we need to identify partial dependencies.

To achieve 2NF, we need to create separate tables:

**Tables in 2NF**

1. **Dentist\_Info Table**
   * **Primary Key:** Staff\_No
     * **Attributes:** Dentist\_Name, Surgery\_No

| Staff\_No | Dentist\_Name | Surgery\_No |
| --------- | ------------- | ----------- |
| S1011     | Zara          | S15         |
| S1024     | Aruna         | S10         |
| S1032     | Robin         | S15         |

2. **Patient\_Appointments Table**
   * **Primary Key:** (Pat\_No, Appointment\_Date\_Time) (Composite Key)
   * **Attributes:** Pat\_Name

| Pat\_No | Pat\_Name | Appointment\_Date\_Time |
| ------- | --------- | ----------------------- |
| P100    | Roiana    | 12-Sep-17 10:00         |
| P105    | Tiagu     | 12-Sep-17 12:00         |
| P108    | Andrew    | 12-Sep-17 10:00         |
| P105    | Andrew    | 14-Sep-17 12:00         |
| P105    | Wong      | 14-Sep-17 10:00         |

**Step 3: 3NF (Third Normal Form)** 3NF requires that there are no transitive dependencies, meaning non-key attributes must depend only on the primary key.

**Tables in 3NF**

1. **Dentist\_Info Table** (remains the same)
   * **Primary Key:** Staff\_No
   * **Attributes:** Dentist\_Name, Surgery\_No

| Staff\_No | Dentist\_Name | Surgery\_No |
| --------- | ------------- | ----------- |
| S1011     | Zara          | S15         |
| S1024     | Aruna         | S10         |
| S1032     | Robin         | S15         |

2. **Patient\_Appointments Table** (we'll adjust to include Staff\_No)
   * **Primary Key:** (Pat\_No, Appointment\_Date\_Time) (Composite Key)
   * **Attributes:** Pat\_Name, Staff\_No (added to link with Dentist)

| Pat\_No | Pat\_Name | Appointment\_Date\_Time | Staff\_No |
| ------- | --------- | ----------------------- | --------- |
| P100    | Roiana    | 12-Sep-17 10:00         | S1011     |
| P105    | Tiagu     | 12-Sep-17 12:00         | S1011     |
| P108    | Andrew    | 12-Sep-17 10:00         | S1024     |
| P105    | Andrew    | 14-Sep-17 12:00         | S1024     |
| P105    | Wong      | 14-Sep-17 10:00         | S1032     |

3. **Surgery\_Info Table**
   * **Primary Key:** Surgery\_No
   * **Foreign Key:** Staff\_No (references Dentist\_Info)
   * **Attributes:** Staff\_No

| Surgery\_No | Staff\_No |
| ----------- | --------- |
| S15         | S1011     |
| S10         | S1024     |

### c.) Define Boyce Codd Normal Form (BCNF) and identify the relation you normalized in (b) is in BCNF already or not .                                                                                                    **(3 MARKS)**



**Answer:-**

Boyce-Codd Normal Form (BCNF) is an extension of the Third Normal Form (3NF). A relation is in BCNF if, for every one of its non-trivial functional dependencies (X → Y), X is a superkey. This means that the left side of every non-trivial functional dependency must be a candidate key. BCNF addresses certain anomalies that can occur in 3NF by ensuring that there are no overlapping candidate keys that could lead to redundancy.



To determine if the normalized relations from part (b) are in BCNF, we need to analyze each relation and their functional dependencies:

1. **Dentist\_Info (Staff\_No, Dentist\_Name, Surgery\_No)**
   * Functional Dependencies:
     * Staff\_No → Dentist\_Name, Surgery\_No
   * Since Staff\_No is a primary key (and thus a superkey), this relation is in BCNF.
2. **Patient\_Appointments (Pat\_No, Pat\_Name, Appointment\_Date\_Time)**
   * Functional Dependencies:
     * Pat\_No → Pat\_Name
   * Here, Pat\_No is a primary key and a superkey. Therefore, this relation is also in BCNF.
3. **Surgery\_Info (Surgery\_No, Staff\_No)**
   * Functional Dependencies:
     * Surgery\_No → Staff\_No
   * Surgery\_No is not a superkey since it does not uniquely identify all the attributes in this relation. Hence, this relation violates the BCNF condition.

### d) What Is the purpose of normalization?                                                                                                    **(2 MARKS)**



Normalization is a process in database design aimed at organizing data to reduce redundancy and improve data integrity. The key purposes of normalization are:

1. **Eliminating Redundancy**:
   * By organizing data into separate tables, normalization minimizes duplicate data, which saves storage space and reduces inconsistency.
2. **Ensuring Data Integrity**:
   * Normalization helps maintain accuracy and consistency of data. By structuring data properly, updates, inserts, and deletions are managed more effectively, preventing anomalies.
3. **Facilitating Data Maintenance**:
   * A well-normalized database is easier to maintain and update. Changes in data structures require fewer adjustments, making database management more efficient.
4. **Improving Query Performance**:
   * Normalization can lead to more efficient query execution by streamlining the data organization, making it easier for the database engine to retrieve relevant data.
5. **Establishing Clear Relationships**:
   * By defining relationships between tables through foreign keys, normalization helps clarify how different data entities interact, aiding in data retrieval and analysis.
6. **Supporting Scalability**:
   * A normalized database structure is typically more flexible and can adapt better to changes in data requirements or application needs, supporting future growth.

## Question 4

Consider the following relational database for Nepal Airlines.

Nepal Airlines has to keep track of its flight and airplane history. A flight is uniquely identified by the combination of a flight number and a date. Every passenger who has flown on Nepal Airlines has a unique passenger number. For a particular passenger who has taken a particular flight, the company wants to keep track of the fare that she paid for it and the date that she made the reservation for it. Clearly, a passenger may have taken many flights (he must have taken at least one to be in the database) and every flight has had many passengers on it.

A pilot is identified by a unique pilot (or employee) number. A flight on aparticular date has exactly one pilot. Each pilot has typically flown many flightsbut a pilot may be new to the company, is in training, and has not flown anyflights, yet. Each airplane has a unique serial number. A flight on a particulardate used one airplane. Each airplane has flown on many flights and dates, buta new airplane may not have been used at all, yet.

<figure><img src=".gitbook/assets/Final database question paper 1 Question 4 .png" alt=""><figcaption></figcaption></figure>

### Write SQL SELECT commands to answer the following queries.&#x20;

#### 4.a) Find the records for the airplanes manufactured by Boeing.

```sql
SELECT *
FROM AIRPLANE
WHERE MANUF = 'Boeing';
```

#### 4.b) How many reservations are there for flight 278 on February 21, 2017?

```sql
SELECT COUNT(*)
FROM RESERVATION
WHERE FLIGHTNUM = 278 AND DATE = '2017-02-21';
```

#### 4.c) List the flights on March 7, 2017, that are scheduled to depart between 10 and 11 AM or that are scheduled to arrive after 3 PM on that date.

```sql
SELECT *
FROM FLIGHT
WHERE DATE = '2017-03-07' AND (DEPTIME BETWEEN '10:00' AND '11:00' OR ARRTIME > '15:00');
```

#### 4.d) How many Boeing 737s does Grand Travel have?

```sql
SELECT COUNT(*)
FROM AIRPLANE
WHERE MANUF = 'Boeing' AND MODEL = '737';
```

#### 4.e) How many of each model of Boeing aircraft does Grand Travel have?

```sql
SELECT MODEL, COUNT(*) AS COUNT
FROM AIRPLANE
WHERE MANUF = 'Boeing'
GROUP BY MODEL;
```

#### 4.f) List the names and dates of hire of the pilots who flew Airbus A320 aircraft in March 2017.

```sql
SELECT P.PILOTNAME, P.HIREDATE
FROM PILOT P
JOIN FLIGHT F ON P.PILOTNUM = F.PILOTNUM
JOIN AIRPLANE A ON F.PLANENUM = A.PLANENUM
WHERE A.MODEL = 'A320' AND F.DATE BETWEEN '2017-03-01' AND '2017-03-31';
```

#### 4.g) List the names, addresses, and telephone numbers of the passengers who have reservations on Flight 562 on January 15, 2017.

```sql
SELECT PA.PASSNAME, PA.ADDRESS, PA.PHONE
FROM PASSENGER PA
JOIN RESERVATION R ON PA.PASSNUM = R.PASSNUM
WHERE R.FLIGHTNUM = 562 AND R.DATE = '2017-01-15';
```

#### 4.h) What was the total fare paid for each flight scheduled to depart between 9 and 10 AM on December 23, 2003? Only include those flights for which the total fare was at least 55,000.

```sql
SELECT R.FLIGHTNUM, SUM(R.FARE) AS TOTAL_FARE
FROM RESERVATION R
JOIN FLIGHT F ON R.FLIGHTNUM = F.FLIGHTNUM
WHERE F.DEPTIME BETWEEN '09:00' AND '10:00' AND F.DATE = '2003-12-23'
GROUP BY R.FLIGHTNUM
HAVING SUM(R.FARE) >= 55000;
```

#### 4.i) List the smallest (in terms of passenger capacity) Boeing 737s.

```sql
SELECT *
FROM AIRPLANE
WHERE MANUF = 'Boeing' AND MODEL = '737'
ORDER BY CAPACITY ASC
LIMIT 1;
```

