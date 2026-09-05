---
name: database-design
description: "Database creation, auditing, and optimization framework for database-design. Use when building from scratch or detecting errors and anti-patterns."
risk: safe
source: community
date_added: "2026-02-27"
---
## Agent Execution Flow (IMPORTANT)
1. **Information Gathering:** Ask clarifying questions to determine context (greenfield vs existing), constraints, and requirements before proposing a solution.
2. **Context Scanning:** Scan the workspace (`list_dir`, `view_file`) to understand current architecture, schemas, and code.
3. **Analyze & Propose:** Once context is fully understood, formulate your architecture strategy or design pattern recommendation.

# Database Design

> **Learn to THINK, not copy SQL patterns.**

## 🎯 Selective Reading Rule

**Read ONLY files relevant to the request!** Check the content map, find what you need.

| File | Description | When to Read |
|------|-------------|--------------|
| `database-selection.md` | PostgreSQL vs Neon vs Turso vs SQLite | Choosing database |
| `orm-selection.md` | Drizzle vs Prisma vs Kysely | Choosing ORM |
| `schema-design.md` | Normalization, PKs, relationships | Designing schema |
| `indexing.md` | Index types, composite indexes | Performance tuning |
| `optimization.md` | N+1, EXPLAIN ANALYZE | Query optimization |
| `migrations.md` | Safe migrations, serverless DBs | Schema changes |

---

## ⚠️ Core Principle

- ASK user for database preferences when unclear
- Choose database/ORM based on CONTEXT
- Don't default to PostgreSQL for everything

---

## Decision Checklist

Before designing schema:

- [ ] Asked user about database preference?
- [ ] Chosen database for THIS context?
- [ ] Considered deployment environment?
- [ ] Planned index strategy?
- [ ] Defined relationship types?

---

## Anti-Patterns

❌ Default to PostgreSQL for simple apps (SQLite may suffice)
❌ Skip indexing
❌ Use SELECT * in production
❌ Store JSON when structured data is better
❌ Ignore N+1 queries

## When to Use
This skill is applicable to execute the workflow or actions described in the overview.


## 🔍 Auditing Protocol
When auditing database-design architecture or code:
1. **Analyze Constraints**: Check if best practices are followed.
2. **Identify Anti-patterns**: Look for performance bottlenecks or security flaws.
3. **Validate Architecture**: Ensure the implementation aligns with domain requirements.

## 🏗️ Creation Protocol
When creating from scratch using database-design:
1. **Plan Architecture**: Define the schema, types, and connections.
2. **Enforce Security**: Apply least privilege and necessary rules.
3. **Optimize**: Implement indexes or necessary performance tweaks early.

## ✅ Validation Checklist
- [ ] Requirements fully met.
- [ ] Best practices for database-design applied.
- [ ] No anti-patterns detected.

## Limitations
- Use this skill only when the task clearly matches the scope described above.
- Do not treat the output as a substitute for environment-specific validation, testing, or expert review.
- Stop and ask for clarification if required inputs, permissions, safety boundaries, or success criteria are missing.


