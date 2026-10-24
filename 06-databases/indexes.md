# Indexes

An index is an extra data structure a database maintains to find rows more quickly. Like the index at the back of a book, it can help locate a relevant item without examining every page—or, in a database, every row.

## A simple example

If an application often looks up customers by email, an index on the `email` column may let the database find a matching row efficiently. Without an appropriate index, the database may need to scan many rows.

## Trade-offs

Indexes take storage and must be updated when data changes. Too many indexes can slow inserts and updates and consume unnecessary space. The right indexes depend on the queries the application actually runs.

Database systems can often explain how they plan to execute a query. Query plans help developers determine whether an index is used and whether a query needs improvement. An index does not guarantee a query will be fast; data size, query shape, and the chosen plan all matter.

## Practical approach

Measure slow queries, inspect their plans, and add indexes based on real access patterns. A unique index can also enforce that a value, such as a username, appears only once. Index design is part of data modeling, not a substitute for it.
