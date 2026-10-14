# DBMS and SQL

## Concepts to learn

- **Database / DBMS:** A database stores organized data; a DBMS provides tools for defining, querying, updating, and controlling that data.
- **Table, row, column:** A relational table contains rows (records) and columns (attributes), with a defined schema.
- **Primary key:** Uniquely identifies a row and cannot be null. A table has one primary-key constraint, which may contain multiple columns.
- **Foreign key:** Enforces a relationship by referring to a candidate/primary key in another table (or the same table).
- **Normalization:** Organizes relational data to reduce unwanted duplication and update anomalies; understand the intent of 1NF, 2NF, and 3NF.
- **SQL command groups:** `SELECT` queries data; `INSERT`, `UPDATE`, `DELETE` change rows; `CREATE` defines objects. Exact taxonomy of DDL/DML can vary slightly by text.
- **Filtering and sorting:** `WHERE` filters rows; `ORDER BY` sorts results. `GROUP BY` forms groups; `HAVING` filters groups after aggregation.
- **Joins:** `INNER JOIN` returns matching rows; `LEFT JOIN` keeps every left-side row and includes matching right-side values when present.
- **Aggregates:** `COUNT`, `SUM`, `AVG`, `MIN`, `MAX`; `COUNT(*)` counts result rows, while `COUNT(column)` generally ignores NULL values.
- **Transactions and ACID:** Atomicity, Consistency, Isolation, Durability describe key transaction properties.

## Original practice MCQs

Use this schema:

```text
Employee(emp_id, name, dept_id, salary)
Department(dept_id, dept_name)
```

### Questions

1. Which constraint uniquely identifies each `Employee` row?
   A) Primary key  B) Sort key only  C) View  D) Wildcard

2. Which clause filters individual rows before grouping?
   A) WHERE  B) HAVING  C) ORDER BY  D) INTO

3. Which clause filters groups after `GROUP BY`?
   A) WHERE  B) HAVING  C) SELECT  D) VALUES

4. What does a `LEFT JOIN` preserve?
   A) All rows from the left table, with matching right rows where available
   B) Only matching rows from the right table
   C) Only rows with NULL keys
   D) No rows from either table

5. Which query returns the number of employees per department?
   A) `SELECT dept_id, COUNT(*) FROM Employee GROUP BY dept_id;`
   B) `SELECT COUNT(dept_id) FROM Department ORDER BY name;`
   C) `DELETE FROM Employee GROUP BY dept_id;`
   D) `SELECT dept_id FROM Employee HAVING COUNT(*);`

6. In ACID, which property means a committed transaction survives a system failure?
   A) Durability  B) Isolation  C) Atomicity  D) Consistency

7. A foreign key is primarily used to:
   A) Enforce referential relationships between tables
   B) Encrypt a whole database
   C) Sort every query automatically
   D) Replace all primary keys

8. Which SQL command changes existing rows?
   A) UPDATE  B) CREATE  C) SELECT  D) GRANT only

### Answer key and explanations

1. **A — Primary key.** It uniquely identifies each row and is non-null.
2. **A — WHERE.** `WHERE` filters rows before grouping/aggregation.
3. **B — HAVING.** `HAVING` filters groups, often using aggregate expressions.
4. **A.** A left join retains all left-table rows; unmatched right columns are typically NULL.
5. **A.** The query groups employee rows by department and counts each group.
6. **A — Durability.** Once committed, the change should persist.
7. **A.** A foreign-key constraint helps maintain referential integrity.
8. **A — UPDATE.** `UPDATE` modifies existing records; always check the `WHERE` clause before running it.
