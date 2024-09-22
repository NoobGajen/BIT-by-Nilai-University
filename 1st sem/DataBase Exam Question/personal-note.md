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
