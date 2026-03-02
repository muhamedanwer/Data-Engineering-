
---

## Transaction

A **transaction** is a logical unit of work that performs one or more operations (such as reads, writes, updates, or deletions) on a database. It is treated as a single, indivisible unit: either **all** of its operations are successfully applied (committed), or **none** of them are (rolled back). This ensures that the database remains in a **consistent state** both before and after the transaction, even if failures occur during its execution.

---

## ACID Properties

ACID is an acronym that stands for **Atomicity**, **Consistency**, **Isolation**, and **Durability**. These four properties guarantee that database transactions are processed reliably and help maintain data integrity, especially in environments with concurrent access or system failures.

### 1. Atomicity
- Atomicity ensures that a transaction is treated as a single, indivisible unit of work. It either executes **completely** or **not at all**.  
- **How it works:** If any part of the transaction fails (e.g., due to a constraint violation, system crash, or power loss), the entire transaction is rolled back, and the database is restored to the state it was in before the transaction began. No partial changes are ever visible.  
- **Key point:** Atomicity is about the transaction as a whole, not individual statements within it.

### 2. Consistency
- Consistency guarantees that a transaction brings the database from one valid state to another, preserving all defined rules—such as constraints, cascades, triggers, and data integrity rules (e.g., unique keys, foreign keys).  
- **How it works:** Any transaction that would violate these rules is aborted, and the database remains unchanged. Consistency ensures that only valid data is written, preventing corruption or logical errors from being introduced.  
- **Key point:** Consistency is about correctness; the database’s invariants are maintained before and after the transaction.

### 3. Isolation
- Isolation ensures that concurrently executing transactions do not interfere with each other. Each transaction should appear as if it is running alone, without seeing the intermediate (uncommitted) states of other transactions.  
- **How it works:** Databases implement isolation through locking mechanisms or multi-version concurrency control (MVCC). Different isolation levels (e.g., Read Uncommitted, Read Committed, Repeatable Read, Serializable) offer trade-offs between performance and the degree of protection against phenomena like dirty reads, non-repeatable reads, and phantom reads.  
- **Key point:** Isolation prevents concurrency anomalies and ensures that the outcome of concurrent transactions is equivalent to some serial (one‑after‑another) execution.

### 4. Durability
-  Durability guarantees that once a transaction has been committed, its changes are permanent and will survive any subsequent system failures (e.g., power outage, crash, or restart).  
- **How it works:** The database ensures that the effects of a committed transaction are recorded in non‑volatile storage (such as a disk) before acknowledging success. This often involves write‑ahead logging or other persistence mechanisms.  
- **Key point:** Durability assures users that their data is safe once the transaction is confirmed complete.

---

## Why ACID Matters

Together, the ACID properties provide a contract that ensures database transactions are:
- **Reliable:** Even in the face of errors, crashes, or power loss.
- **Correct:** Data integrity is always preserved.
- **Predictable:** Concurrent transactions behave as if they were executed serially.


