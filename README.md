# Awesome interviews

This is repository with the most popular questions of programming interviews(mainly for developer using JVM languages).
All questions have been taken from my personal experience.

## Table of Contents
- [Databases Common](#databases-common)
- [PostgreSQL](#postgresql)
- [Structures](#structures) // TODO: add b-tree


## Databases Common

- **CAP-theorem** <br/>
The CAP theorem applies a similar type of logic to distributed systems—namely, that a distributed system can deliver only two of three desired characteristics: consistency, availability, and partition tolerance <br/>
**Consistency** - all clients see the same data at the same time, no matter which node they connect to (not cassandra) <br/>
**Availability** - any client making a request for data gets a response, even if one or more nodes are down (not mongo) <br/>
**Partition tolerance** - the cluster must continue to work despite any number of communication breakdowns between nodes in the system (not sql)


- **ACID** <br/>
ACID refers to the four key properties of a transaction: atomicity, consistency, isolation, and durability <br/> All SQL and Mongo support ACID <br/>
**Atomicity** - all changes to data are performed as if they are a single operation <br/>
**Consistency** - data is in a consistent state when a transaction starts and when it ends. <br/>
**Isolation** - the intermediate state of a transaction is invisible to other transactions <br/>
**Durability** -  ensures that changes to your data made by successfully executed transactions will be saved, even in the event of system failure


- **Transaction Isolation Levels** <br/>
Isolation determines how transaction integrity is visible to other users and systems <br/>
Isolation levels solve problems: <br/>
*Dirty Read* - a transaction reads a data that has not yet been committed <br/>
*Non-Repeatable read* - a transaction reads same row twice, and get a different value each time <br/>
*Phantom Read* - two identical queries in transaction are executed, and the collection of rows returned by the second query is different from the first. <br/>
Isolation levels: <br/>
*Read Uncommitted* - one transaction may read not yet committed changes made by other transaction <br/>
*Read Committed* - guarantees that any data read is committed at the moment it is read (default for SQL) <br/>
*Repeatable Read* - holds read locks on all rows it references and writes locks on all rows it inserts, updates, or deletes <br/>
*Serializable* - it creates the effect that transactions are running in serial order


- **Scalability methods** <br/>
*Replication* - copying an entire table or database onto multiple servers <br/>
*Partitioning* - splitting up a large monolithic database into multiple smaller databases based on data cohesion (users, sales, accounts...) <br/>
*Clustering* - using multiple application servers to access the same database <br/>
*Sharding* - splitting up a large table of data horizontally(row-wise) <br/>


## PostgreSQL

- **Type of indices (PRO)** <br/>
*B-tree(TODO: add link) (default)* - suitable for data that can be sorted. "Greater", "less" and "equal" operators must be defined for the data type. <br/>
*Hash* - only handle simple equality comparisons. Based on simple hash table <br/>
*GiST* - like b-tree, but also suitable for complex structures like geodata, pictures... <br/>
*GIN* - inverted indexes which can handle values that contain more than one key(arrays). Store all values of elements in list(or b-tree if many elements) with references which rows contain them


- **Ways to optimize queries**


