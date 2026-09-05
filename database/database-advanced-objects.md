# Advanced Database Objects and Concepts

Beyond basic tables and columns, databases utilize several advanced objects to improve security, performance, data integrity, and developer experience.

## 1. View
A **View** is essentially a virtual table. 
*   **Concept**: It is a saved, predefined SQL query (or aggregation pipeline in NoSQL) that can be queried just like a regular table.
*   **Storage**: Views do not store physical data themselves. They only store the query definition in the data dictionary.
*   **Purpose**: 
    *   **Simplification**: To encapsulate complex queries (like multi-table joins) into a single, easy-to-query virtual table.
    *   **Reusability**: Write a complex query once, save it as a view, and reuse it anywhere.
*   **Usage**: In relational databases, created via `CREATE VIEW ... AS SELECT ...`. In MongoDB, created via `createView` using an aggregation pipeline.

## 2. Synonym
A **Synonym** is an alias or alternative name for a database object (such as a Table, View, Sequence, Function, or Procedure).
*   **Purpose**:
    *   **Security & Abstraction**: Hides the actual name and owner of the underlying object.
    *   **Access Control**: Instead of granting direct access to base tables, administrators can create synonyms and grant roles/privileges specifically on the synonyms.
*   **Types**: Can be Private (accessible only to a specific user) or Public (accessible to everyone in the database).
*   **Example**: Creating a synonym `Staff` for the underlying table `hr_manager.employees_table_v2`. Users query `Staff`, unaware of the actual table name.

## 3. Sequence
A **Sequence** is a database object designed to automatically generate sequential numeric values (e.g., 1, 2, 3...).
*   **Purpose**: Primarily used to generate unique identifier values, such as Primary Keys for tables.
*   **Benefits**: Much faster and safer than writing custom application code to find the "max ID and add 1", which can cause concurrency issues and slow down performance.
*   **Alternatives**: Many modern databases now support `AUTO_INCREMENT` (MySQL) or `IDENTITY` (SQL Server, Oracle 12c+) columns directly on the table, which achieve the same goal without needing a separate Sequence object.

## 4. Index
An **Index** is a background database structure used to dramatically speed up data retrieval operations (queries).
*   **The Book Analogy**: An index works exactly like the index at the back of a 300-page book. If you want to find a specific word and there is no index, you must read the entire book from start to finish. In a database, this is called a **Full Table Scan**. If you have an index, you look up the word, find the exact page number, and jump straight to it.
*   **Trade-offs**: 
    *   **Pros**: Significantly accelerates `SELECT` queries and conditional operations (`WHERE` clauses).
    *   **Cons**: Indexes consume additional physical disk space because they create and store an ordered copy of the data. They also slightly slow down `INSERT`, `UPDATE`, and `DELETE` operations because the index must be updated alongside the table.

## 5. Key
A **Key** is a constraint defined on a table to enforce data integrity, uniqueness, and relationships.
*   **Primary Key**: Ensures that every record in a table is unique and identifiable.
*   **Foreign Key**: Enforces relational data integrity between two tables. For example, ensuring that an employee cannot be assigned to a `department_id` that does not exist in the `Departments` table.
*   **Composite Key**: A key (Primary or Foreign) that consists of more than one column to guarantee uniqueness.

---
