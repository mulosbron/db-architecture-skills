# Database Normalization & Design Stages

Database design encompasses the entire process of defining data structures, storing data, and managing updates. A well-designed database acts as the foundation of an application; without it, the system will eventually collapse under data anomalies and performance issues.

## 🏗️ The 4 Stages of Database Design

The process of designing a relational database typically follows four sequential stages:

1. **Requirement Analysis (İhtiyaç Analizi):** 
   - Meetings with business owners and stakeholders to understand expectations.
   - Determining what data is critical, performance priorities, and the overall needs of the application.
   - *Key takeaway:* The business owners know their domain best; their feedback must constantly validate the design.

2. **Conceptual Design (Kavramsal Tasarım):** 
   - Creation of the **Entity-Relationship (ER) Diagram**.
   - Identifying the core entities (e.g., School, Student, Instructor) and the conceptual relationships between them (e.g., one-to-many, many-to-many).

3. **Logical Design (Mantıksal Tasarım):** 
   - Translating the ER model into a relational schema.
   - Defining the specific attributes (columns), their data types, and maximum sizes (e.g., VARCHAR(50), INT).
   - Establishing how relationships will be linked (usually via ID columns).

4. **Physical Design (Fiziksel Tasarım):** 
   - The final blueprint applied to the actual RDBMS (PostgreSQL, MySQL, etc.).
   - Creating tables, defining Primary Keys, Foreign Keys, Unique constraints, and creating Indexes to optimize queries.

---

## 🔍 What is Normalization?

**Normalization** is a systematic process applied during database design to organize data in a relational database (Note: NoSQL databases generally do not support or require traditional normalization). 

### Why Normalize?
- **Prevent Data Redundancy:** Eliminate duplicated data across tables.
- **Prevent Anomalies:** Avoid data loss or inconsistencies during INSERT, UPDATE, or DELETE operations.
- **Ensure Consistency:** Keep the data structure simple and reliable.

### Core Philosophy
1. **Separate Entities:** Every distinct entity (e.g., Student, Course, Instructor) must be stored in its own separate table.
2. **Atomic Data:** Every attribute (column) must be broken down into its smallest, indivisible unit (Atomic structure).
3. **Establish Relationships:** Link the separated tables using unique identifiers (Keys).

---

## 📈 Normalization Forms (NF)

Normalization is applied in progressive stages called "Forms". Usually, reaching the 3rd Normal Form (3NF) is considered the "ideal" structure for most applications.

### 0. Denormalized Form
- Imagine throwing all data (Orders, Customers, Products, Sales Reps) into a single spreadsheet/table.
- Causes massive repetition. A single cell might contain multiple values (e.g., CPU, RAM in a single "Products" column).

### 1. First Normal Form (1NF)
- **Rule 1:** Each column must contain only a *single, atomic value*. (e.g., split the CPU, RAM cell into multiple distinct rows).
- **Rule 2:** Every row must be unique. No two rows can be completely identical.

### 2. Second Normal Form (2NF)
- **Rule 1:** Must already satisfy 1NF.
- **Rule 2:** Eliminate **partial dependencies**. All non-key attributes must depend on the *entire* primary key.
- *Action:* If a table mixes Customer data with Order data, extract the Customer data into a separate Customers table. Replace the extracted data with a Foreign Key (e.g., customer_id) to maintain the relationship.

### 3. Third Normal Form (3NF)
- **Rule 1:** Must already satisfy 2NF.
- **Rule 2:** Eliminate **transitive dependencies**. (If Column A depends on Column B, and Column B depends on Column C, they should not be in the same table).
- *Action:* For example, if an Orders table contains a sales_rep_id and also a sales_rep_name, the sales_rep_name is transitively dependent. Move it to a separate Sales_Reps table.

### Advanced Forms (BCNF, 4NF, 5NF)
- **Boyce-Codd Normal Form (BCNF) & Beyond:** Used for highly complex schemas with overlapping candidate keys or multi-valued dependencies. While theoretically important to completely eliminate every single anomaly, 3NF is practically sufficient for the vast majority of real-world software architectures.

---
