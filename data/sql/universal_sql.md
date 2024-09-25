# Universal SQL <!-- omit from toc -->
<!-- ---------------------------------------------------------------- -->

Compendium for universal SQL keywords [T-SQL, SQLite, MySQL, PostgreSQL, ..]

___

- [1. Keywords](#1-keywords)
  - [1.1. `SELECT`](#11-select)
  - [1.2. `FROM`](#12-from)
  - [1.3. `WHERE`](#13-where)
  - [1.4. `INSERT`](#14-insert)
  - [1.5. `UPDATE`](#15-update)
  - [1.6. `DELETE`](#16-delete)
  - [1.7. `CREATE`](#17-create)
  - [1.8. `ALTER`](#18-alter)
  - [1.9. `DROP`](#19-drop)
  - [1.10. `JOIN`](#110-join)
    - [1.10.1. `INNER JOIN`](#1101-inner-join)
    - [1.10.2. `LEFT JOIN` / `LEFT OUTER JOIN`](#1102-left-join--left-outer-join)
    - [1.10.3. `RIGHT JOIN` / `RIGHT OUTER JOIN`](#1103-right-join--right-outer-join)
    - [1.10.4. `FULL JOIN` / `FULL OUTER JOIN`](#1104-full-join--full-outer-join)
  - [1.11. `GROUP BY`](#111-group-by)
  - [1.12. `ORDER BY`](#112-order-by)
  - [1.13. `HAVING`](#113-having)
  - [1.14. `DISTINCT`](#114-distinct)
  - [1.15. `UNION`](#115-union)
  - [1.16. `UNION ALL`](#116-union-all)
  - [1.17. `LIMIT` / `TOP` / `FETCH`](#117-limit--top--fetch)
    - [1.17.1. `LIMIT` (MySQL/SQLite)](#1171-limit-mysqlsqlite)
    - [1.17.2. `TOP` (T-SQL)](#1172-top-t-sql)
    - [1.17.3. `FETCH` (PostgreSQL)](#1173-fetch-postgresql)
  - [1.18. `EXISTS`](#118-exists)
  - [1.19. `IN`](#119-in)
  - [1.20. `BETWEEN`](#120-between)
  - [1.21. `LIKE`](#121-like)
  - [1.22. `IS NULL`](#122-is-null)
  - [1.23. `AND`](#123-and)
  - [1.24. `OR`](#124-or)
  - [1.25. `NOT`](#125-not)
  - [1.26. `CASE`](#126-case)
  - [1.27. `AS`](#127-as)
  - [1.28. `INDEX`](#128-index)
  - [1.29. `PRIMARY KEY`](#129-primary-key)
  - [1.30. `FOREIGN KEY`](#130-foreign-key)
  - [1.31. `DEFAULT`](#131-default)
  - [1.32. `CHECK`](#132-check)
  - [1.33. `TRUNCATE`](#133-truncate)
  - [1.34. `EXPLAIN`](#134-explain)
  - [1.35. `COMMIT`](#135-commit)
  - [1.36. `ROLLBACK`](#136-rollback)
  - [1.37. `SAVEPOINT`](#137-savepoint)

___

# 1. Keywords
<!-- ---------------------------------------------------------------- -->

## 1.1. `SELECT`


**Function** | Retrieves data from a database.
------------ | --------
**Example**  |
```sql
    SELECT <entity> FROM <table>;
```


## 1.2. `FROM`


**Function** | Specifies the table to select or delete data from.
------------ | --------
**Example**  |
```sql
    SELECT column1, column2 FROM <table_name>;
```


## 1.3. `WHERE`


**Function** | Filters records to return only those that meet a specified condition.
------------ | --------
**Example**  |
```sql
    SELECT * FROM <table_name> WHERE condition
```


## 1.4. `INSERT`


**Function** | Adds new rows of data into a table.
------------ | --------
**Example**  |
```sql
    INSERT INTO <table_name> (column1, column2) VALUES (value1, value2);
```


## 1.5. `UPDATE`


**Function** | Modifies existing records in a table.
------------ | --------
**Example**  |
```sql
    UPDATE <table_name> SET column1 = value1 WHERE condition;
```


## 1.6. `DELETE`


**Function** | Removes records from a table.
------------ | --------
**Example**  |
```sql
    DELETE FROM <table_name> WHERE condition;
```


## 1.7. `CREATE`


**Function** | Defines a new database object (like a table, view, or index).
------------ | --------
**Example**  |
```sql
    CREATE TABLE <table_name> (column1 <datatype>, column2 <datatype>);
```


## 1.8. `ALTER`


**Function** | Modifies an existing database object like a table or column.
------------ | --------
**Example**  |
```sql
    ALTER TABLE <table_name> ADD <column_name> <datatype>;
```


## 1.9. `DROP`


**Function** | Deletes a database object (like a table, index, or view).
------------ | --------
**Example**  |
```sql
    DROP TABLE <table_name>;
```


## 1.10. `JOIN`


**Function** | Combines rows from two or more tables based on a related column between them.
------------ | --------
**Example**  |
```sql
    SELECT * FROM table1 JOIN table2 ON table1.id = table2.id;
```


### 1.10.1. `INNER JOIN`


**Function** | Returns records that have matching values in both tables.
------------ | --------
**Example**  |
```sql
    SELECT * FROM table1 INNER JOIN table2 ON table1.id = table2.id;
```


### 1.10.2. `LEFT JOIN` / `LEFT OUTER JOIN`


**Function** | Returns all records from the left table, and the matched records from the right table. Unmatched rows from the right table will have NULL values.
------------ | --------
**Example**  |
```sql
    SELECT * FROM table1 LEFT JOIN table2 ON table1.id = table2.id;
```


### 1.10.3. `RIGHT JOIN` / `RIGHT OUTER JOIN`


**Function** | Returns all records from the right table, and the matched records from the left table. Unmatched rows from the left table will have NULL values.
------------ | --------
**Example**  |
```sql
    SELECT * FROM table1 RIGHT JOIN table2 ON table1.id = table2.id;
```


### 1.10.4. `FULL JOIN` / `FULL OUTER JOIN`


**Function** | Returns all records when there is a match in either left or right table.
------------ | --------
**Example**  |
```sql
    SELECT * FROM table1 FULL OUTER JOIN table2 ON table1.id = table2.id;
```


## 1.11. `GROUP BY`


**Function** | Groups rows that have the same values in specified columns into aggregated
------------ | --------
**Example**  |
```sql
    SELECT COUNT(*), <column_name> FROM <table_name> GROUP BY <column_name>;
```


## 1.12. `ORDER BY`


**Function** | Sorts the result set in ascending or descending order.
------------ | --------
**Example**  |
```sql
    SELECT * FROM <table_name> ORDER BY <column_name> ASC;
```


## 1.13. `HAVING`


**Function** | Filters the result of GROUP BY based on conditions applied to aggregate functions.
------------ | --------
**Example**  |
```sql
    SELECT <column_name>, COUNT(*) FROM <table_name> GROUP BY <column_name> HAVING COUNT(*) > 5;
```


## 1.14. `DISTINCT`


**Function** | Ensures that only unique records are returned.
------------ | --------
**Example**  |
```sql
    SELECT DISTINCT <column_name> FROM <table_name>;
```


## 1.15. `UNION`


**Function** | Combines the result sets of two or more SELECT statements, removing duplicate rows.
------------ | --------
**Example**  |
```sql
    SELECT column1 FROM table1 UNION SELECT column1 FROM table2;
```


## 1.16. `UNION ALL`


**Function** | Similar to UNION, but includes duplicate rows.
------------ | --------
**Example**  |
```sql
    SELECT column1 FROM table1 UNION ALL SELECT column1 FROM table2;
```


## 1.17. `LIMIT` / `TOP` / `FETCH`


**Function**      | Limits the number of rows returned by a query.
------------      | --------

### 1.17.1. `LIMIT` (MySQL/SQLite)


```sql
    SELECT * FROM <table_name> LIMIT 10;
```


### 1.17.2. `TOP` (T-SQL)


```sql
    SELECT TOP 10 * FROM <table_name>;
```


### 1.17.3. `FETCH` (PostgreSQL)


```sql
    SELECT * FROM <table_name> FETCH FIRST 10 ROWS ONLY;
```


## 1.18. `EXISTS`


**Function** | Checks for the existence of any records in a subquery.
------------ | --------
**Example**  |
```sql
    SELECT * FROM <table_name> WHERE EXISTS (SELECT * FROM another_table WHERE condition);
```

## 1.19. `IN`


**Function** | Checks if a value matches any value in a list or subquery.
------------ | --------
**Example**  |
```sql
    SELECT * FROM <table_name> WHERE <column_name> IN (value1, value2, value3);
```

## 1.20. `BETWEEN`


**Function** | Filters records within a specified range.
------------ | --------
**Example**  |
```sql
    SELECT * FROM <table_name> WHERE <column_name> BETWEEN value1 AND value2;
```


## 1.21. `LIKE`


**Function** | Searches for a specified pattern in a column.
------------ | --------
**Example**  |
```sql
    SELECT * FROM <table_name> WHERE <column_name> LIKE 'A%';
```

## 1.22. `IS NULL`


**Function** | Filters records where the column value is NULL.
------------ | --------
**Example**  |
```sql
    SELECT * FROM <table_name> WHERE <column_name> IS NULL;
```

## 1.23. `AND`


**Function** | Combines multiple conditions where all must be true.
------------ | --------
**Example**  |
```sql
    SELECT * FROM <table_name> WHERE condition1 AND condition2;
```

## 1.24. `OR`


**Function** | Combines multiple conditions where at least one must be true.
------------ | --------
**Example**  |
```sql
    SELECT * FROM <table_name> WHERE condition1 OR condition2;
```

## 1.25. `NOT`


**Function** | Negates a condition.
------------ | --------
**Example**  |
```sql
    SELECT * FROM <table_name> WHERE NOT condition;
```

## 1.26. `CASE`


**Function** | Creates conditional logic in queries.
------------ | --------
**Example**  |
```sql
    SELECT <column_name>,
       CASE
           WHEN condition1 THEN result1
           WHEN condition2 THEN result2
           ELSE result3
       END
    FROM <table_name>;
```

## 1.27. `AS`


**Function** |Renames a column or table using an alias.
------------ | --------
**Example**  |
```sql
    SELECT <column_name> AS new_name FROM <table_name>;
```


## 1.28. `INDEX`


**Function** | Used to speed up the retrieval of records by creating an index on one or more columns of a table.
------------ | --------
**Example**  |
```sql
    CREATE INDEX index_name ON <table_name> (<column_name>);
```

## 1.29. `PRIMARY KEY`


**Function** | Uniquely identifies each record in a table.
------------ | --------
**Example**  |
```sql
    CREATE TABLE <table_name> (<column_name> <datatype> PRIMARY KEY);
```

## 1.30. `FOREIGN KEY`


**Function** | Establishes a relationship between two tables by linking one table's column to the primary key of another.
------------ | --------
**Example**  |
```sql
    ALTER TABLE <table_name> ADD CONSTRAINT fk_name FOREIGN KEY (<column_name>) REFERENCES another_table (<column_name>);
```

## 1.31. `DEFAULT`


**Function** | Assigns a default value to a column if no value is specified.
------------ | --------
**Example**  |
```sql
    ALTER TABLE <table_name> ADD <column_name> <datatype> DEFAULT <default_value>;
```

## 1.32. `CHECK`


**Function** | Sets a constraint that limits the values that can be placed in a column.
------------ | --------
**Example**  |
```sql
    CREATE TABLE <table_name> (<column_name> <datatype> CHECK (<column_name> > 0));
```

## 1.33. `TRUNCATE`


**Function** | Removes all rows from a table but keeps the structure intact.
------------ | --------
**Example**  |
```sql
    TRUNCATE TABLE <table_name>;
```


## 1.34. `EXPLAIN`


**Function** | Provides information on how the SQL query will be executed, helping optimize query performance.
------------ | --------
**Example**  |
```sql
    EXPLAIN SELECT * FROM <table_name>;
```


## 1.35. `COMMIT`


**Function** | Saves all the changes made during the current transaction.
------------ | --------
**Example**  |
```sql
    COMMIT;
```


## 1.36. `ROLLBACK`


**Function** | Undoes all the changes made during the current transaction.
------------ | --------
**Example**  |
```sql
    ROLLBACK;
```


## 1.37. `SAVEPOINT`


**Function** |
------------ | --------
**Example**  | Sets a point within a transaction to which a ROLLBACK can revert.
```sql
    SAVEPOINT savepoint_name;
```
