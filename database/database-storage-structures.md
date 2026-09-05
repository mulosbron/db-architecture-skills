# Database Storage Structures and Concepts

Understanding how data is physically and logically stored is crucial when working with both Relational Database Management Systems (RDBMS) and NoSQL databases. The fundamental concepts differ depending on the database model being used.

## 1. NoSQL Databases (Document Model)
NoSQL databases are designed to handle unstructured or semi-structured data. They use a flexible, document-oriented model rather than strict tables.

### Collection
A **Collection** is the fundamental data storage structure in a NoSQL database (such as MongoDB). 
*   **Purpose**: It is the equivalent of a table in a relational database.
*   **Flexibility**: Unlike relational tables, collections do not have a predefined format or schema.
*   **Documents**: Collections store data as documents. These documents are typically stored in **JSON** (JavaScript Object Notation) or BSON format.
*   **Structure**: Documents can contain key-value pairs, arrays, or even nested documents, allowing for a highly flexible and hierarchical data representation.

## 2. SQL Databases (Relational Model)
Relational databases (SQL) enforce a strict structure where data must adhere to a predefined schema. 

### Table
A **Table** is the core storage structure in an RDBMS.
*   **Purpose**: It is the equivalent of a collection in a NoSQL database.
*   **Structure**: Tables are composed of columns and rows. When a table is created, its structure (the columns and their data types) must be defined in advance.

### Column
A **Column** represents a specific attribute or property of the data within a table (e.g., Customer ID, Name, Surname, Phone).
*   **Data Types**: Every column must have a predefined data type (e.g., integer, string, date). 
*   **Validation**: The database strictly enforces these data types. For example, if a "Customer ID" column is defined as a number, character strings cannot be inserted into it.

### Row
A **Row** represents a single, complete record within a table. 
*   If a table is a list of customers, each row represents one specific customer and contains the data for all the columns associated with that customer.

### Cell / Data Field
A **Cell** or **Data Field** is the intersection of a specific row and a specific column.
*   It is the actual space where a single, specific piece of data is entered and stored (e.g., the value "Mehmet" entered in the Name column for a specific row).

## 3. RDBMS vs. NoSQL Concept Mapping
When transitioning between Relational (SQL) and Document-based (NoSQL) databases, it is helpful to understand how the terminology translates between the two models.

| RDBMS (Relational Model) | NoSQL (e.g., MongoDB Document Model) |
| :--- | :--- |
| **Table** | **Collection** |
| **Row** | **Document** |
| **Column** | **Field** |

---
