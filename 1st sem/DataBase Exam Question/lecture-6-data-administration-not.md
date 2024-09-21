# Lecture 6: Data Administration Note

## **1. Concurrency Control and Transactions**

### **Concurrency Control:**

When multiple users or applications access and modify a database at the same time, concurrency control makes sure that the operations happen correctly. Without concurrency control, data could become inconsistent. For example, if two people are booking the last seat on a plane, concurrency control ensures that only one person can book it. This prevents errors or data corruption.

### **Need for Atomic Transactions:**

An atomic transaction means that all parts of a transaction must happen or none of them should happen. For example, transferring money between two bank accounts involves both subtracting money from one account and adding it to another. If one part of this transaction fails, the whole transaction should roll back, meaning the money is neither subtracted nor added to avoid incorrect balances.

### **ACID Properties (Atomicity, Consistency, Isolation, Durability):**

These are the core principles behind transaction processing:

* **Atomicity:** All parts of a transaction must succeed or the entire transaction fails.
* **Consistency:** The transaction must leave the database in a valid state, adhering to integrity constraints.
* **Isolation:** Transactions must not interfere with each other.
* **Durability:** Once a transaction is committed, the changes must be permanent.

### **Isolation Levels in Transactions:**

Although you touched on concurrency control, it might help to briefly mention the four isolation levels, which help manage how transactions interact with each other:

* **Read Uncommitted:** Allows dirty reads. No protection from anomalies.
* **Read Committed:** Prevents dirty reads, but non-repeatable reads can still happen.
* **Repeatable Read:** Prevents dirty and non-repeatable reads, but phantom reads can occur.
* **Serializable:** The strictest level. Prevents all anomalies, but can lead to performance issues.

### **Different Kinds of Anomalies:**

Without proper management of transactions, anomalies can occur. Here are the main ones:

* **Lost Update:**\
  Two transactions try to update the same record at the same time. The update from one transaction gets lost because the other transaction overwrites it.\
  _Example:_ If two users are editing a document, one user's changes might disappear if both try to save the document at the same time.
* **Dirty Read:**\
  A transaction reads data that has been changed by another transaction but not yet committed. If the other transaction fails and rolls back, the first transaction has used incorrect data.\
  _Example:_ If one user updates a price in a product catalog, but the update hasn’t been finalized, another user might see the wrong price.
* **Uncommitted Dependency (Non-Repeatable Read):**\
  This happens when a transaction reads the same row twice, but the data changes between the two reads.\
  _Example:_ If a user checks the balance of a bank account twice during a transaction, the balance might be different each time due to another transaction altering the amount in between.
* **Phantom Read:**\
  A query that reads a set of rows twice during a transaction might find that some rows have been added or deleted between the two reads.\
  _Example:_ A user searches for all orders placed on a particular day. In between two searches, new orders may be added by another user, changing the results.

***

## **2. Resource Locking**

### **Resource Locking:**

When multiple users or transactions access the same data in a database, resource locking ensures that one transaction doesn't interfere with another. For example, when a user is editing a record, the database can lock the record so no one else can change it until the first user is done. This protects the integrity of the data.

* **Exclusive Lock:**\
  An exclusive lock prevents others from reading or modifying the data. Only one transaction can work with the data at a time. _Example:_ If a user is editing a record, no one else can read or edit it until the lock is released.
* **Shared Lock:**\
  A shared lock allows multiple transactions to read the data but doesn’t allow any of them to modify it.\
  _Example:_ Multiple users can view a product’s details at the same time, but none can change it while the shared lock is active.

### **Optimistic vs. Pessimistic Locking:**

* **Optimistic Locking:**\
  In optimistic locking, we assume that data conflicts are rare. So, instead of locking data right away, a transaction reads the data and checks for changes only before committing the transaction. If no one else has changed the data, the transaction is allowed to proceed. _Example:_ Many users can view a product's price, but when someone tries to change the price, the system checks if another user has already made a change before committing.
* **Pessimistic Locking:**\
  Pessimistic locking assumes that conflicts are likely, so it locks data right away to prevent others from accessing or changing it until the transaction is complete.\
  _Example:_ When editing a product’s details, the system locks the product so no one else can access or modify it until the current user is finished.

***

## **3. Serializable Transactions**

### **Serializable Transactions:**

Serializability ensures that transactions produce the same result as if they had been executed one after the other, even if they were actually processed at the same time. This is the strictest form of isolation, where transactions are controlled in such a way that they don’t overlap or affect each other. _Example:_ If two users place orders at the same time, serializability ensures that the system processes these orders one after the other, preventing any confusion or conflict in inventory.

***

## **4. Two-Phase Locking (2PL)**

### **Two-Phase Locking (2PL):**

Two-phase locking is a method used to ensure transaction isolation and prevent conflicts between transactions. It involves two phases:

* **Growing Phase:**\
  In this phase, the transaction can acquire locks as needed but cannot release any locks. This ensures that the transaction has control over the resources it needs before proceeding.
* **Shrinking Phase:**\
  In this phase, the transaction can release locks but cannot acquire any new locks. Once a transaction starts releasing locks, it signals that it is nearing completion.
* **Example of Two-Phase Locking:**\
  A user begins editing a customer’s details (growing phase: locks are acquired). Once the user starts saving or committing the changes, the locks are released (shrinking phase), allowing other users to access the data.

***

## **5. Deadlock**

### **Deadlock**

A deadlock occurs when two or more transactions are waiting for each other to release resources, but none of them can proceed because they are all holding locks on the resources that the others need. This creates a cycle where none of the transactions can complete.\
_Example:_ Transaction A locks resource X and waits for resource Y. Meanwhile, Transaction B locks resource Y and waits for resource X. Both transactions are stuck and can’t proceed.

***

## **6. Database Security, Authentication, and Authorization**

### **Database Security**

1. **Authentication**\
   Ensures that only authorized users can access the database by verifying their identity using credentials like usernames and passwords.
2. **Authorization**\
   Controls what actions authenticated users can perform within the database (e.g., view, edit, or delete records) based on their assigned permissions.
3. **Encryption**\
   Protects sensitive data by converting it into an unreadable format using encryption algorithms, ensuring data is secure both at rest (stored) and in transit.
4. **Database Auditing**\
   Tracks and records database activities such as user access, data changes, and actions performed. This helps identify unauthorized access or suspicious behavior.
5. **Backup and Recovery**\
   Regular backups and recovery procedures ensure data can be restored in case of corruption, hacking, or system failures, maintaining database integrity and availability.

### **Database Integrity Constraints**

Consider adding a section on **Integrity Constraints** to cover rules that ensure data correctness and validity

* **Primary Key Constraint:** Ensures that each record is unique.
* **Foreign Key Constraint:** Ensures referential integrity between tables.
* **Unique Constraint:** Ensures that no two records can have the same value in a specified column.
* **Check Constraint:** Ensures that the value in a column meets a specific condition.
* **Not Null Constraint:** Ensures that a column cannot have a null value.

### **Authentication and Authorization**

* **Authentication:** This is the process of verifying a user’s identity, usually through a username and password.\
  _Example:_ Logging into a system with your credentials.
* **Authorization:** Once authenticated, authorization determines what the user is allowed to do, such as viewing or editing certain data.\
  _Example:_ An admin can add or delete records, while a regular user can only view them.

***

## **7. Application-Level Security**

### **Application-Level Security**

This refers to security measures applied at the application level, which controls access to the database through the application itself. It involves assigning roles, permissions, and access controls within the application, ensuring that users can only interact with data they are allowed to access.\
_Example:_ In an e-commerce system, only the sales team might have permission to update product prices, while customers can only view them.

***

## **8. Database Backup and Recovery**

### **Database Backup and Recovery**

Backup and recovery are critical processes to ensure that the database can be restored in case of system failure, data corruption, or accidental deletion.

*   **Backup**&#x20;

    A backup is a copy of the database or specific data that is stored separately to allow for recovery in case of failure.\
    _Example:_ A daily backup of all customer orders to ensure that no orders are lost if the system crashes.
* **Recovery**\
  Recovery is the process of restoring the database to its correct state after a failure. This can involve using backups and transaction logs to bring the database back to the most recent consistent state.
  * **Rollback:** This undoes changes made by a transaction that hasn’t been committed.\
    _Example:_ If a user tries to update a record but decides to cancel, the rollback will undo the changes.
  * **Rollforward:** This re-applies changes from a transaction log to bring the database to its most recent state after a crash.\
    _Example:_ After restoring a database from backup, a rollforward can apply all changes made since the backup was taken.
  * **Undo and Redo Transactions:**
    * **Undo:** Reverses uncommitted changes, ensuring that incomplete transactions are rolled back.\
      _Example:_ Cancelling a money transfer in progress would undo any changes made during the transaction.
    * **Redo:** Reapplies changes from committed transactions to recover the database after a crash.\
      _Example:_ After a system failure, redo logs ensure that committed transactions are applied, so no data is lost.
