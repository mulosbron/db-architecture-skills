# Database Storage and Programmability Concepts

This document covers physical storage management concepts and database programmability objects such as Functions, Procedures, Packages, and Triggers. Mastering these programmability objects is a core requirement for a Database Developer using languages like PL/SQL (Oracle), T-SQL (MSSQL), or PL/pgSQL (PostgreSQL).

## 1. Tablespace and File Group
While databases store data logically in tables, they must store data physically on disks.

*   **Tablespace**: A logical storage structure used in **Oracle, PostgreSQL, and MySQL**.
*   **File Group**: The exact equivalent of a Tablespace, but used specifically in **MS SQL Server**.
*   **How it Works**: 
    *   Tablespaces/File Groups are logical containers that group physical **Data Files**.
    *   Data Files are the actual binary files stored on the operating system's disk.
    *   When you create a table, you assign it to a specific Tablespace. Any data inserted into that table is then physically written into the OS blocks of the Data Files belonging to that Tablespace.

## 2. Function
A **Function** is a programmable database object that accepts parameters, performs an action (such as calculations or data processing), and **must return a value**.

*   **Concept**: Similar to mathematical functions ($f(x) = y$), you pass inputs (parameters) and get a specific output (return value).
*   **Key Requirement**: A function must have a `RETURN` statement. It can return a single scalar value (like an Integer or String) or a result set/array.
*   **Usage**: Ideal for calculations (e.g., calculating factorial, tax rates) or returning specific lookup values.
*   **Built-in vs. Custom**: Databases come with *built-in* functions (like `NOW()` for the current date/time or `COUNT()`), but developers can also write their own custom functions.

## 3. Stored Procedure
A **Stored Procedure** (or simply Procedure) is a database object that accepts parameters and executes a series of database operations (like `INSERT`, `UPDATE`, `DELETE`, or complex business logic).

*   **Difference from Functions**: The most significant difference is that a procedure **does not require a return value**. While procedures can return data (using OUT parameters or returning result sets), it is not a mandatory architectural requirement like it is for Functions.
*   **Usage**: Used for executing complex business logic, batch updates, or inserting data into multiple tables sequentially. In MSSQL, they are executed using the `EXEC` or `EXECUTE` command.

## 4. Package
A **Package** is a database object used to group logically related PL/SQL types, functions, and procedures.

*   **Oracle Specific**: This concept is primarily native to the **Oracle Database**.
*   **Structure**: A package consists of two parts:
    1.  **Specification (Header)**: Declares the public functions, procedures, and types.
    2.  **Body**: Contains the actual implementation code.
*   **Purpose**: Acts similar to an API or a class module in object-oriented programming. It prevents standalone functions/procedures from cluttering the database and provides better modularity and performance.

## 5. Trigger
A **Trigger** is a special type of stored procedure that automatically executes (or "fires") in the background when a specific event occurs in the database.

*   **Events that Fire Triggers**:
    *   **DML Events**: Data Manipulation Language events like `INSERT`, `UPDATE`, or `DELETE` on a specific table.
    *   **System Events**: Database-level events such as `LOGON` (user connecting) or `LOGOFF` (user disconnecting).
*   **Purpose**: 
    *   **Auditing and Logging**: E.g., Automatically recording who changed a row and at what time into a separate log table.
    *   **Data Integrity**: E.g., Automatically updating a summary table whenever a detail table is modified.
    *   **Automation**: They run entirely automatically without the application or user explicitly calling them.

---
*End of session topics.*
