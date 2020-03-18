# Relational Databases


## Prerequisites
* Databases
* Disk
* Memory

## Key Terms  
### Relational Database  
A type of structured database in which data is stored following a tabular format; often supports powerful querying using SQL.  

### Non-Relational Database  
In contrast with relational database (SQL databases), a type of database that is free of imposed, tabular-like structure. Non-relational databases are often referred to as NoSQL databases.  

### SQL  
Structured Query Language. RElational databases can be used using a derivative o SQL such as PostgreSQL in the case of Postgres.  

### SQL Database  
Any database that supports SQL. This term is often used synonymously with "Relational Database", though in practice, not _every_ relational database supports SQL.  

### NoSQL Database  
Any database that is not SQL compatible is called NoSQL.  

### ACID Transaction  
A type of database transaction that has four important properties:  
* __Atomicity__: The operations that constitute the transaction will either all succeed or all fail. There is no in-between state.
* __Consistency__: The transaction cannot bring the database to an invalid state. After the transaction is committed or rolled back, the rules for each record will still apply, and all future transactions will see teh efect of the transaction. Also named __Strong Consistency__.  
* __Isolation__: The execution of multiple transactions concurrently will have the same effect as if they had been executed sequentially.
* __Durability__: Any committed transaction is written to non-volatile storage. It will not be undone by a crash, power loss, or network partition.  

### Database Index  
A special auxilary data structure that allows your database to perorm certain queries much faster. Indexes can typically only exist to reference structured data, like data stored in relational databases. In practice, you create an index on one or multiple columns in your database to greatly speed up __read__ queries that you run very often, with the downside of slightly longer __writes__ to your database, since writes have to also take place in the relevant index.  

### Strong Consistency  
Strong Consistency usually refers to the consistency of ACID transactions, as opposed to __Eventual Consistency__.

### Eventual Consistency  
A consistency model which is unlike __Strong Consistency__. In this model, reads might return a view of the system that is stale. An eventually consistent datastore will give guarantees that the state of the database will eventually reflect writes within a time period (could be 10 seconds, or minutes).

### Postgres ☆  
A relational database that uses a dialect of SQL called PostgreSQL. Provides ACID transactions.  
Website: [https://www.postgresql.org/](https://www.postgresql.org/)