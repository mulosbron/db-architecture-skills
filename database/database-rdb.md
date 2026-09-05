# Relational Databases (RDB)

Relational Databases (RDB) are a database architecture that stores data in related tables and provides access to that data. They are commonly referred to as Relational Databases, SQL Databases, or RDBMS (Relational Database Management Systems).

## 1. Core Structure
*   **Tables**: Data is stored in tabular structures consisting of rows and columns.
*   **Rows (Records)**: Each row in a table represents a single record. When keys are defined, each record has a unique identifier.
*   **Columns (Attributes)**: The columns of a table hold the attributes of the data. Every record contains values corresponding to these attributes.

## 2. Table Relationships (ER Diagrams)
In a relational database, tables are expected to be related to one another (often visualized using Entity-Relationship Diagrams). No table should exist in isolation or disconnected from the rest of the schema.

*   **Parent-Child Relationships**: This defines a dependency between data across tables. For example, in a relationship between an `Employees` table and a `Departments` table, an employee must be assigned to an existing department.
*   **Importance of Relationships**: While defining these relationships is not strictly mandatory, failing to do so defeats the purpose of using a "relational" database. Over time, unrelated data becomes complex and unmanageable.
*   **Database-Level Control**: By establishing relationships (and constraints), data integrity validation is offloaded from the application (code) layer to the database itself. This prevents invalid data entry and ensures a robust, consistent infrastructure.

---
