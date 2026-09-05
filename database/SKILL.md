---
name: database
description: "Database creation, auditing, and optimization framework for database. Use when building from scratch or detecting errors and anti-patterns."
risk: safe
source: self
date_added: "2026-09-05"
---
## Agent Execution Flow (IMPORTANT)
1. **Information Gathering:** Ask clarifying questions to determine context (greenfield vs existing), constraints, and requirements before proposing a solution.
2. **Context Scanning:** Scan the workspace (`list_dir`, `view_file`) to understand current architecture, schemas, and code.
3. **Analyze & Propose:** Once context is fully understood, formulate your architecture strategy or design pattern recommendation.

# Database Creation & Auditing Framework

> "A well-architected database enforces its own integrity. Constraints prevent bad data, and the right architectural choice ensures scalability and reliability."

## 🎯 Selective Reading Rule

**Read ONLY files relevant to the request!** Check the content map, find what you need.

| File | Description | When to Read |
|------|-------------|--------------|
| `database-rdb.md` | Relational database fundamentals & ER models | Designing tables and relationships |
| `database-constraints.md` | Data integrity rules (NOT NULL, FK, etc.) | Auditing/fixing schema validation |
| `database-cap.md` | CAP theorem trade-offs | Selecting distributed database types |
| `database-acid.md` | ACID principles for RDBMS | Ensuring transaction reliability |
| `database-base.md` | BASE principles for NoSQL | Designing highly available NoSQL |
| `database-advanced-objects.md` | Views, Indexes, Synonyms, Sequences | Performance & abstraction audit |
| `database-schema-and-security.md` | Privileges, Roles, and Schemas | Access control and security audit |
| `database-programmability-and-storage.md`| Triggers, Procedures, Functions | Auditing embedded logic |
| `database-storage-structures.md` | Tablespaces and storage logic | Disk allocation planning |
| `database-users-and-roles.md` | Deep dive into user management | User hierarchy auditing |
| `database-normalization.md` | 1NF, 2NF, 3NF and Database Design Stages | Normalizing tables, preventing redundancy |

---

## 🔍 Auditing Protocol (Database Review)

When asked to audit an existing database, systematically check the following:
1. **Missing Constraints**: Are there `NOT NULL`, `UNIQUE`, or `CHECK` constraints missing? Is the data validation incorrectly handled in the application layer instead of the DB?
2. **Orphaned Data**: Are `FOREIGN KEY` constraints enforced properly between parent and child tables?
3. **Indexing Strategy**: Are indexes missing on frequently queried columns or foreign keys? Are there redundant indexes slowing down writes?
4. **Consistency Model**: Does the current DB architecture match its use case (e.g., trying to use BASE NoSQL for strict financial transactions)?
5. **Security**: Are roles and privileges applied using the principle of least privilege?

## 🏗️ Creation Protocol (Database from Scratch)

When asked to create a database from scratch:
1. **Analyze Requirements**: Understand the domain (Social Media, E-commerce, Finance).
2. **Select Architecture**: Choose SQL vs NoSQL based on CAP, ACID, and BASE principles.
3. **Design ER Diagram**: Map out tables, relationships, and data types.
4. **Enforce Integrity**: Define constraints (`PK`, `FK`, `UNIQUE`, `CHECK`) immediately.
5. **Optimize**: Plan for initial indexes and views based on expected access patterns.

---

## ✅ Validation Checklist

Before finalizing architecture or audit report:
- [ ] Requirements clearly understood and domain identified.
- [ ] Correct Database Type Selected (RDBMS vs NoSQL).
- [ ] Data integrity enforced at the DB layer via Constraints.
- [ ] Proper indexes added for performance.
- [ ] Strict relationships defined via Foreign Keys.
- [ ] Security roles mapped accurately.

## When to Use
This skill is applicable to execute the workflow or actions described in the overview.


## 🔍 Auditing Protocol
When auditing database architecture or code:
1. **Analyze Constraints**: Check if best practices are followed.
2. **Identify Anti-patterns**: Look for performance bottlenecks or security flaws.
3. **Validate Architecture**: Ensure the implementation aligns with domain requirements.

## 🏗️ Creation Protocol
When creating from scratch using database:
1. **Plan Architecture**: Define the schema, types, and connections.
2. **Enforce Security**: Apply least privilege and necessary rules.
3. **Optimize**: Implement indexes or necessary performance tweaks early.

## ✅ Validation Checklist
- [ ] Requirements fully met.
- [ ] Best practices for database applied.
- [ ] No anti-patterns detected.

## Limitations
- Use this skill only when the task clearly matches the scope described above.
- Do not treat the output as a substitute for environment-specific validation, testing, or expert review.
- Stop and ask for clarification if required inputs, permissions, safety boundaries, or success criteria are missing.



