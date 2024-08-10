# Question Paper - 3

### **1. Differentiate between File-Based Systems and Database Management Systems (DBMS)**

| Feature             | File-Based Systems                                                                | Database Management Systems (DBMS)                                                       |
| ------------------- | --------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| **Data Storage**    | Data is stored in individual files, often spread across different locations.      | Data is stored in a centralized database, allowing for easier management.                |
| **Data Redundancy** | High, as the same data might be duplicated across multiple files.                 | Reduced, as data is stored in a single place and managed centrally.                      |
| **Data Access**     | Each application manages its own files, making data sharing difficult.            | Multiple applications can access the same data through the DBMS, promoting data sharing. |
| **Data Integrity**  | Limited, as maintaining consistent data across multiple files can be challenging. | High, as DBMS enforces rules to ensure data consistency.                                 |
| **Security**        | Basic, as security mechanisms are usually application-specific.                   | Strong, with built-in mechanisms for access control and data protection.                 |

### **2. Explain Database Approaches**

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

### **3. Explain Different Roles in DBMS**

1. **Data Administrator (DA):**
   * The person who is responsible for the overall management and strategic use of data of an organization, ensuring its quality, consistency, and accessibility across the entire organization.
   * They are also responsible for developing data policies, data planning, data quality management, metadata management, and data security.
2. **Database Administrator (DBA):**
   * The person who is responsible for the technical management, maintenance, day-to-day operations, and security of an organization's database management system (DBMS).
   * They manage the overall database environment and are responsible for tasks such as backups and recovery, security, performance tuning, and ensuring the database runs smoothly.
3. **Logical Database Designer:**
   * The person who is responsible for designing the conceptual or logical representation of the database structure, focusing on the organization of data without considering physical implementation details like file storage, indexing, or performance optimization.
   * They handle data modeling, schema design, normalization, and user requirements analysis.
4. **Physical Database Designer:**
   * The person who is responsible for implementing the logical database design into a physical structure, determining how data will be stored and accessed in the actual database management system (DBMS).
   * They are responsible for physical schema design, storage management, performance optimization, and implementation.
5. **Application Developer:**
   * The person who is responsible for developing software applications that interact with the database, implementing business logic and user interfaces for data manipulation and retrieval.
   * They are also responsible for requirements analysis, database interaction, application design, testing and debugging, and integration.
6. **End Users:**
   * The individuals or groups who interact with the database through applications or interfaces to perform their job functions or access information.
   * They perform tasks such as data entry, data retrieval, updates, and providing feedback.

