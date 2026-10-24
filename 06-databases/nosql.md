# NoSQL

NoSQL is a broad label for database systems that do not rely only on the traditional relational-table model. It includes several different designs, each suited to particular data and access patterns.

## Common families

- Document databases store records as document-like values, often JSON-shaped.
- Key-value stores retrieve a value by a key, often for fast lookups or caching.
- Graph databases model entities and the relationships between them.
- Wide-column databases organize data for large-scale distributed workloads.

These labels are broad: products can combine features, and individual systems vary considerably.

## Choosing a data model

Start with the information the application needs to store and the queries it must support. A document model may suit data that is naturally grouped together; a relational model can be a good fit when structured relationships and flexible queries matter. Operational needs such as consistency, scale, reliability, and team familiarity also matter.

NoSQL does not mean “no structure” or “automatically faster.” Every database has a data model and trade-offs. Some NoSQL systems support transactions, while the availability and behavior of features differ.

## The key idea

Choose a database because its model and operational properties suit the application, not because a category is fashionable. Compare with [SQL](./sql.md) and consider [Indexes](./indexes.md) and [Transactions](./transactions.md).
