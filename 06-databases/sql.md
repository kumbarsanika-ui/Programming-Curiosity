# SQL

SQL, commonly pronounced “sequel” or by its letters, is a language for working with relational databases. A relational database organizes information into tables with rows and columns.

## Tables and relationships

A `customers` table might have columns for `id`, `name`, and `email`. An `orders` table can have its own ID and a `customer_id` that refers to the customer who placed each order. This relationship avoids copying all customer details into every order.

## Reading and changing data

A query might look like this:

```sql
SELECT name
FROM customers
WHERE id = 7;
```

SQL can also insert, update, and delete records, define tables, and control access. Queries should use parameterized inputs rather than building SQL by joining untrusted text; this helps prevent SQL injection.

## Relational databases

Popular relational database systems include PostgreSQL, MySQL, SQLite, and SQL Server. They differ in features and deployment but share many SQL concepts. Relational databases commonly support transactions, which help group related changes reliably. See [Transactions](./transactions.md).

The SQL language is not itself the database: it is a way to communicate with a database system.
