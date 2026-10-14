# Databases and SQL

**Assessment priority: High evidence** — DBMS is explicitly named in a recent candidate report and appears in pseudocode/core-topic preparation outlines.

| Concept | One-line last-minute reminder |
|---|---|
| Database and DBMS | A database stores organized data; a DBMS defines, queries, updates, protects, and manages that data. |
| Relational table | A table stores records as rows and attributes as columns under a schema. |
| Primary key | A primary key uniquely identifies a row and cannot be NULL; it may be composite. |
| Candidate key | A candidate key is a minimal set of column(s) capable of uniquely identifying a row. |
| Foreign key | A foreign key enforces a relationship by referencing a key in another or the same table. |
| UNIQUE and NOT NULL | `UNIQUE` prevents duplicate constrained values; `NOT NULL` requires a value, subject to DBMS semantics. |
| Composite key | A composite key uses multiple columns together to identify a row. |
| Normalization | Normalization reduces redundancy and update anomalies by organizing attributes and dependencies. |
| First Normal Form | 1NF requires atomic column values and no repeating groups under the common relational teaching model. |
| Second Normal Form | 2NF requires 1NF and no partial dependency of a non-key attribute on part of a composite candidate key. |
| Third Normal Form | 3NF requires 2NF and removes transitive non-key dependencies under the standard teaching definition. |
| SELECT | `SELECT` specifies which columns/expressions appear in the query result. |
| WHERE | `WHERE` filters rows before grouping and aggregation. |
| ORDER BY | `ORDER BY` sorts query results; specify direction where required. |
| GROUP BY | `GROUP BY` groups rows so aggregate functions can summarize each group. |
| HAVING | `HAVING` filters grouped results, often using aggregate values. |
| INNER JOIN | `INNER JOIN` returns rows with matching join keys on both sides. |
| LEFT JOIN | `LEFT JOIN` preserves all left-side rows and supplies matching right-side values or NULLs. |
| Aggregate functions | `COUNT`, `SUM`, `AVG`, `MIN`, and `MAX` summarize values; `COUNT(column)` usually ignores NULLs. |
| NULL | NULL represents missing/unknown/not-applicable data and is tested with `IS NULL`, not `= NULL`. |
| Subquery | A subquery is a query nested within another query and can provide values or a derived result set. |
| Index | An index can speed reads/searches but consumes storage and can add write/update overhead. |
| Transaction | A transaction groups database operations into a logical unit of work. |
| ACID | Atomicity, Consistency, Isolation, and Durability describe key transaction guarantees. |
| Isolation and concurrency | Isolation controls how concurrent transactions interact; weaker levels may allow anomalies such as non-repeatable reads. |
| DDL / DML / DCL / TCL | DDL defines structures, DML queries/changes rows, DCL controls permissions, and TCL manages transactions. |
| UPDATE safety | Always verify an `UPDATE` or `DELETE` predicate and transaction/backup strategy before changing records. |
