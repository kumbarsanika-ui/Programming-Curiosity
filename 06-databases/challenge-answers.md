# Databases: challenge answers

## Questions 61–70: Storing data

### 61. Why can’t we simply store everything in Python variables?

Variables are useful while a process is running, but their data usually disappears when that process exits. They are also private to that process unless explicitly shared. Databases persist data, support queries, coordinate concurrent users, and provide recovery and access-control features.

### 62. Why do applications need databases?

Applications use databases to store, retrieve, update, and organize data reliably. Database systems provide durable storage, query tools, indexing, transaction support, and mechanisms for multiple clients to work with shared data.

### 63. What happens when you click “Save”?

The application gathers and validates the input, then sends it to a server or writes it locally. A server may authorize the request, apply business rules, and issue a database command. The database changes data and may commit a transaction; the application then reports success or failure. The exact path depends on the product.

### 64. Where does the data physically go?

The database writes data to storage managed by its host or service, often using files on SSDs and logs or backups for recovery. Cloud databases still run on physical machines in data centers. Replication and backup can create additional copies in other locations.

### 65. What is a table?

In a relational database, a table is a structured collection of rows described by columns. A table commonly represents one kind of entity, such as customers or orders, though good schema design depends on relationships and use cases.

### 66. What is a row?

A row is one record in a table: a set of values for that record's columns. For example, one customer row may contain an ID, name, and email.

### 67. What is a column?

A column defines one attribute in a table, such as a customer's email address. Its type and constraints describe which values are valid. A database can enforce rules such as `NOT NULL` or uniqueness.

### 68. Why do we need primary keys?

A primary key uniquely identifies each row. It lets applications and related tables refer to a specific record without relying on a changeable attribute such as a name. A primary key must be unique and not null; it may be a generated ID or a natural key.

### 69. Why do we need indexes?

An index helps a database locate matching rows without scanning the whole table. It can speed up reads and enforce uniqueness, but it consumes storage and makes writes more expensive because the index must be maintained. Add indexes based on measured queries.

### 70. What is the difference between SQL and NoSQL?

SQL is a language used with relational databases, which model data in related tables and commonly support rich queries and transactions. NoSQL describes several non-relational models, including document, key-value, graph, and wide-column systems. The choice depends on data relationships, query patterns, consistency needs, scale, and operational trade-offs—not on a universal speed ranking.

## Follow the trail

Read [SQL](./sql.md), [NoSQL](./nosql.md), [indexes](./indexes.md), and [transactions](./transactions.md). Transactions are especially useful when a save consists of multiple changes that must succeed or fail together.
