# Transactions

A database transaction groups operations so they behave as one logical unit. If a transaction succeeds, its changes are committed; if it fails, the database can roll them back so partial work is not left behind.

## The ACID properties

Transactions are often described by four properties:

- **Atomicity:** the grouped changes happen as a unit or are rolled back.
- **Consistency:** a transaction preserves rules the database is required to enforce.
- **Isolation:** concurrent transactions have defined visibility and interaction rules.
- **Durability:** committed changes are preserved according to the database's guarantees.

The exact isolation levels and durability guarantees depend on the database and configuration.

## Example: transferring money

A transfer might subtract money from one account and add it to another. If the subtraction succeeds but the addition fails, the data would be wrong unless the operations are grouped in a transaction. The application should also check that the transfer follows business rules, such as having sufficient funds.

## Transactions have boundaries

Transactions do not make bad application logic correct, and they usually should not be held open longer than needed. Long transactions can hold locks or resources and interfere with other work. Applications must understand how their database handles concurrent changes, retries, and failures.
