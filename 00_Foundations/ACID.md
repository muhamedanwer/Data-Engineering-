
### Transaction:

Any operation that is treated as single, indivisible unit of work which either completed or doesn't completed at all and leave the storage system in a consistent state.

### ACID : 

Stands for Atomicity , Consistency, Isolation, Durability.
Set of properties that guarantee the reliability, integrity and correctness of database transactions, even in the event of errors, system failures, or concurrent access.

#### Atomicity :
- guarantee each statement  in a transaction treated as single unit either completed of doesn't completed at all.
- if any part of transaction fails, the system rollback the entire transaction 
- prevent data loss and corruption from occuring
#### Consistency:
- guarantee that transactions only make changes to tables in predefined, predictable ways.
- ensure that the corruption or errors in your data don't create unintended consequences.
#### Isolation
- Ensures that multiple transactions running simultaneously don't interfere each other.
#### Durability:
- ensure that changes to data made by successfully created transaction.