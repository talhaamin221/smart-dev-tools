# SQL Validator Online — Developer Cheatsheet

> 🛠️ **Interactive Version**: [SQL Validator Online →](https://smartformatter.com/tools/sql-validator-online)

## What is SQL Validation?
SQL validation is the process of parsing an SQL query to ensure it follows the structural and syntactical rules of a specific database dialect (e.g., MySQL, PostgreSQL, Oracle). A valid query guarantees the database engine will not reject it for syntax reasons, preventing runtime errors.

## Quick Reference: Dialect Differences
Different databases have unique keywords and functions. Here are common differences:

| Feature | MySQL | PostgreSQL | SQL Server (T-SQL) | Oracle |
|---------|-------|------------|--------------------|--------|
| **Limit Rows** | `LIMIT 10` | `LIMIT 10` | `TOP 10` | `FETCH FIRST 10 ROWS ONLY` |
| **String Concat** | `CONCAT(a, b)` | `a || b` | `a + b` | `a || b` |
| **Get Date** | `NOW()` | `CURRENT_TIMESTAMP` | `GETDATE()` | `SYSDATE` |
| **Boolean True** | `TRUE` or `1` | `TRUE` or `'t'` | `1` | `1` |

## Common SQL Mistakes
1. **Missing Semicolons**: Many parsers strictly require `;` at the end of statements, especially in scripts with multiple queries.
2. **Reserved Words as Columns**: Using keywords like `SELECT`, `ORDER`, or `GROUP` as column names without escaping them (e.g., `` `ORDER` `` in MySQL or `"ORDER"` in Postgres).
3. **Trailing Commas**: Leaving a comma after the last column in a `SELECT` or `CREATE TABLE` statement (e.g., `SELECT a, b, FROM table`).
4. **Mismatched Quotes**: Using double quotes `"` for strings instead of single quotes `'` (standard SQL requires single quotes for string literals).

## Formatting Best Practices
Consistent formatting makes complex queries readable.
* **Capitalize Keywords**: `SELECT`, `FROM`, `WHERE`, `INNER JOIN`.
* **Indent Clauses**: New line and indent for `FROM`, `WHERE`, `AND`/`OR`.
* **Use Table Aliases**: E.g., `SELECT u.name FROM users u` instead of `SELECT users.name FROM users`.

## When to Use an SQL Validator
* Before running destructive queries (`UPDATE`, `DELETE`) or large `DDL` statements.
* When migrating queries between different database dialects.
* When writing complex `JOIN`s or subqueries where syntax errors are hard to spot visually.

## Related Tools on Smart Formatter
* [GraphQL Query Formatter](https://smartformatter.com/tools/graphql-query-formatter)
* [JSON Path Finder](https://smartformatter.com/tools/json-path-finder)
