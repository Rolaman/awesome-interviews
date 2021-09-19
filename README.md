# Awesome Interviews

This is repository with the most popular questions of programming interviews(mainly for developer using JVM languages).
All questions have been taken from my personal experience.

## Table of Contents

- [Databases Common](#databases-common)
- [PostgreSQL](#postgresql)
- [Structures](#structures)
- [Patterns](#patterns)
- [Commons](#commons)
- [Java](#java)
- [Spring](#spring)
- [Algorithmic Approaches](#algorithmic-approaches)
- [Algorithm examples](#algorithm-examples)

## Databases Common

- **CAP-theorem**

  The CAP theorem applies a similar type of logic to distributed systems—namely, that a distributed system can deliver
  only two of three desired characteristics: consistency, availability, and partition tolerance

  **Consistency** - all clients see the same data at the same time, no matter which node they connect to (not
  cassandra)

  **Availability** - any client making a request for data gets a response, even if one or more nodes are down (not
  mongo)

  **Partition tolerance** - the cluster must continue to work despite any number of communication breakdowns between
  nodes in the system (not sql)


- **ACID**

  ACID refers to the four key properties of a transaction: atomicity, consistency, isolation, and durability <br/> All
  SQL and Mongo support ACID

  **Atomicity** - all changes to data are performed as if they are a single operation

  **Consistency** - data is in a consistent state when a transaction starts and when it ends.

  **Isolation** - the intermediate state of a transaction is invisible to other transactions

  **Durability** - ensures that changes to your data made by successfully executed transactions will be saved, even in
  the event of system failure


- **Transaction Isolation Levels**

  Isolation determines how transaction integrity is visible to other users and systems

  Isolation levels solve problems:

  *Dirty Read* - a transaction reads a data that has not yet been committed

  *Non-Repeatable read* - a transaction reads same row twice, and get a different value each time

  *Phantom Read* - two identical queries in transaction are executed, and the collection of rows returned by the second
  query is different from the first.

  <br/>
  Isolation levels:
  
  *Read Uncommitted* - one transaction may read not yet committed changes made by other transaction

  *Read Committed* - guarantees that any data read is committed at the moment it is read (default for SQL)

  *Repeatable Read* - holds read locks on all rows it references and writes locks on all rows it inserts, updates, or
  deletes

  *Serializable* - it creates the effect that transactions are running in serial order


- **Scalability methods**

  *Replication* - copying an entire table or database onto multiple servers

  *Partitioning* - splitting up a large monolithic database into multiple smaller databases based on data cohesion (
  users, sales, accounts...)

  *Clustering* - using multiple application servers to access the same database

  *Sharding* - splitting up a large table of data horizontally(row-wise)


## PostgreSQL

- **Indices**
  
  Disadvantages of creating any indices are that they consume space on disk 
  and make UPDATE and INSERT operation slower
  
  *B-tree(TODO: add link) (default)* - suitable for data that can be sorted. "Greater", "less" and "equal" operators
  must be defined for the data type.

  *Hash* - only handle simple equality comparisons. Based on simple hash table

  *GiST* - like b-tree, but also suitable for complex structures like geodata, pictures...

  *GIN* - inverted indexes which can handle values that contain more than one key(arrays). Store all values of elements
  in list(or b-tree if many elements) with references which rows contain them


- **How to find inefficient SQL query or if DB is slow**

  Firstly, use EXPLAIN to get plan of processing query.
  You can use EXPLAIN ANALYZE to run query and get real time of process.
  
  'Seq Scan' means that process doesn't use index and scan whole table(inefficient)


- **Ways to optimize queries**
    - Use indices on conditional fields
    - SELECT only fields you need (instead of *)
    - Avoid DISTINCT
    - Use JOIN ON instead of read two tables with WHERE
    - Use WHERE instead of HAVING
    - Use LIMIT
    - Use JOIN ON with proper condition instead of IN


- **VACUUM**

  VACUUM reclaims storage occupied by dead tuples. In normal PostgreSQL operation, tuples that are deleted or obsoleted by an update are not physically removed from their table; they remain present until a VACUUM is done. Therefore it's necessary to do VACUUM periodically, especially on frequently-updated tables.


## Structures

// TODO: b-tree, hashmap in java, red-black tree

## Patterns

- **Currying**

  Currying is a transformation of functions that translates a function from callable as f(a, b, c) into callable as f(a)(b)(c).


- **Monad**

  Monad is a generic concept which helps in doing operations between pure functions to deal with side effects.
  It is just a structure to store state with operation of flatMap and creation


- **Closure**

  A closure is the combination of a function bundled together (enclosed) with references to its surrounding state. 
  In other words, a closure gives you access to an outer function’s scope from an inner function.


- **Factory vs Factory Method vs Abstract Factory**

  *Factory* - encapsulates object creation code and produces the suitable object based on given input

  *Factory Method* - had two dedicated factories each specialised in doing just one thing

  *Abstract Factory* - an abstract class of factory which can be implemented in different ways


## Commons

- **REST**

  *Representational state transfer* - is an architectural style that was created to guide to create web application.
  The most common protocol for REST is HTTP.

  *REST Constrains:*

  - *Client–server architecture* - all workloads are between the providers of a resource or service(servers) and service requesters(clients)
  - *Statelessness* - no session information is retained by the server, every packet of information transferred can be understood in isolation
  - *Cacheability* - clients and intermediaries can cache responses
  - *Layered system* - if a proxy or load balancer is placed between the client and server, it won't affect their communications
  - *Uniform interface* - individual resources are identified in requests, each message includes enough information to describe how to process the message, having accessed an initial URI a client can use server-provided links dynamically to discover all the available resources it needs
  
  *Difference from SOAP*

  SOAP is a protocol with SOAP is a protocol whereas REST is an architectural pattern.

## Java


## Spring


## Algorithmic Approaches


## Algorithm examples
