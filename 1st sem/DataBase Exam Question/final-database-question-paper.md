# Final - Database Question Paper

### **Question 1**

**SP Bumi Transport** has decided to build a database to help manage its operations. It is interested in keeping track of Its buses, The terminals to which buses stop, Passengers and the trips they have taken, Its employees, and data about the Maintenance of its buses.

#### Q.1.a.)

1.  a.) Using this introductory description of (and hints about) the SP Bumi Transport, make a list of the \*\*SEVEN (7) things in the company's environment about which the company would want to maintain data.                                                                                                                                   **(7 MARKS)**



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

#### Q.1.b.)

1.  b.) Suggest THREE (3) reports that SP Bumi Transport could use to improve its operations and gain a competitive advantage?                                                                                                                   **(6 MARKS)**



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

#### Q.1.c.)

1.  c.) Describe the **THREE(3)** main characteristics of the database approach and contrast it with the file-based approach.



    **Answer:-**

    Three main characteristics of the database approach and contrast with the file-based approach:



    | **Characteristic**         | **Database Approach (DBMS)**                                                                                       | **File-Based Approach**                                                                                           |
    | -------------------------- | ------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------- |
    | **1. Data Centralization** | Data is stored in a centralized system, allowing multiple users and applications to access the same data easily.   | Data is stored in separate files across different locations, making access and management more difficult.         |
    | **2. Data Integrity**      | Ensures high data integrity with rules and constraints to keep the data accurate and consistent across the system. | Maintaining data accuracy is difficult due to the risk of data duplication and inconsistency between files.       |
    | **3. Data Independence**   | Physical storage and data access are separate, meaning changes in data structure don’t affect applications.        | File structures are closely tied to applications, so changes can break the way programs access and use the data.  |
    | **4. Security**            | Offers strong security with built-in access control, user authentication, and data protection features.            | Security is weak and usually relies on each application, making it harder to protect data effectively.            |
    | **5. Data Redundancy**     | Reduces data duplication because data is stored centrally and managed consistently.                                | High data redundancy due to duplication of data across multiple files, leading to inconsistency and wasted space. |



#### Q.1.d.)

1.  d) Explain the differences of **Data Definition Language (DDL)** and **Data Manipulation Language (DML)**.                                                                                                                                                 **(6 MARKS)**



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

### **Question 2** <a href="#question-1" id="question-1"></a>

#### Q.2.a.)

2.  a.) Read the following description carefully. State appropriate assumptions and devise the corresponding EAR model:&#x20;

    The Selangor Stage Coach Co. provides services to the greater Selangor municipal, including various towns around the state capital.&#x20;

    It owns a substantial number of buses. Each bus is allocated to a particular route, although some routes may have several buses. Each bus has a unique bus number. It Is Important to store information about the seating capacity and the make/type of all buses.&#x20;

    Each route, distinguish by a route number, passes through a number of towns. Several routes may serve the same town. Information Is available on the average number of passengers carried per day for each route.&#x20;

    Due to long travelling time, one or more drivers are assigned to each stage of a route, which corresponds to a journey through a town on a route. Drivers have an employee number, name, address and sometimes a telephone number.\


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

#### Q.2.b.)

2.  b.) Devise a relational database schema to demonstrate how you will map your EAR model in (a) onto tables in a relational database. Identify the primary keys / foreign keys in each entity.



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



