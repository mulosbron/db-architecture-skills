# Database Constraints

Constraints are rules applied to tables and columns in relational databases to enforce data integrity and consistency. By implementing these rules, data validation is shifted from the application developers to the database management system.

## 1. NOT NULL
Specifies that a column cannot accept an empty (`NULL`) value. When this constraint is defined, a value must always be provided during data entry (`INSERT` operations).

## 2. UNIQUE KEY
Ensures that all values inserted into a column are distinct (no duplicates).
*   Multiple `UNIQUE KEY` constraints can be defined on a single table.
*   **Example**: An `email` column is defined as UNIQUE because email addresses are specific to individuals. The system will throw an error if an attempt is made to enter an existing email address a second time.
*   UNIQUE columns generally allow a single `NULL` value to be entered (depending on the specific database engine).

## 3. PRIMARY KEY
A key that uniquely identifies each row (record) in a table.
*   It is a combination of `NOT NULL` and `UNIQUE` constraints; the value cannot be empty and must be unique.
*   A table can have **only one** PRIMARY KEY. However, this key can be formed by combining multiple columns (a Composite Primary Key).
*   **Example**: An employee's identification number (`employee_id`).

## 4. FOREIGN KEY
Establishes a *Parent-Child* relationship between tables.
*   It enforces referential integrity by ensuring that a value in one table matches a value in another (or the same) table.
*   The referenced column in the parent table must be a `PRIMARY KEY` or a `UNIQUE KEY`.
*   **Example**: The `department_id` in an `Employees` table must reference an existing ID in the `Departments` table to maintain data integrity. A table can also reference itself (e.g., a `manager_id` referencing an `employee_id` in the same table).

## 5. CHECK
Enforces that values entered into a column must satisfy a specific condition or format.
*   **Examples**:
    *   Restricting a `gender` column to only accept 'F' (Female) or 'M' (Male).
    *   Enforcing a rule that a passport number must be exactly 11 characters long (e.g., `LENGTH(passport_no) = 11`).

## 6. DEFAULT
Defines a fallback value that is automatically inserted into a column if no explicit value is provided during an `INSERT` operation.
*   **Example**: If no value is provided for a `country` column, the database can automatically insert "United States" as the default.

---
