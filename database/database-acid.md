# ACID Principles

ACID is an acronym representing the core principles that guarantee the reliability and validity of database transactions. These principles are the foundation of Relational Database Management Systems (RDBMS) like SQL databases. A transaction is any logical unit of work, such as an `INSERT`, `UPDATE`, or `DELETE` operation.

## 1. Atomicity
Atomicity ensures that a transaction is treated as a single, indivisible logical unit. 
*   **The "All or Nothing" Rule**: All operations within a transaction must be successfully completed. If any part of the transaction fails, the entire transaction is rolled back (aborted), and the database state is left completely unchanged.
*   **Example**: When withdrawing money from an ATM, two operations occur: 1) Deducting the amount from your account balance (`UPDATE`), and 2) Recording the transaction details (`INSERT`). Both must succeed together. If the machine loses power after the deduction but before the recording, the deduction is rolled back.

## 2. Consistency
Consistency guarantees that a transaction transitions the database from one valid state to another, maintaining all predefined rules (like constraints, cascades, and triggers).
*   **Data Validity**: During an ongoing transaction, the affected data must display its previous valid state to other users. Only after the transaction is fully completed (committed) do all users across the system see the new, updated state. 
*   **Example**: It prevents scenarios where a transfer of funds creates money out of thin air or loses it.

## 3. Isolation
Isolation ensures that concurrently executing transactions do not interfere with or affect one another.
*   **Concurrency Control**: Each transaction must execute as if it were the only one running in the database.
*   **Locking Mechanism**: If two users attempt to update the exact same record simultaneously, the database places a lock on the record for the first user. The second user's transaction must wait until the first one is finished (committed) before it can proceed, preventing data corruption.

## 4. Durability
Durability guarantees that once a transaction has been successfully committed, it will remain permanently recorded in the database, even in the event of a system failure (such as a power outage or server crash).
*   **System Recovery**: The database must be capable of recovering its state from backups, logs, or disk storage upon restarting, ensuring no committed data is ever lost.

---
