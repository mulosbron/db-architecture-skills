# 🗄️ Database Architect Skills for AI Agents

> **Transform your LLM coding and design assistant into an expert Database Architect.**

A production-ready suite of specialized AI agent skills for designing, auditing, and optimizing database architectures. From relational database modeling and NoSQL scaling to vector search and ORM best practices, these skills turn your AI into a seasoned DBA and Data Architect.

---

## 🌟 Key Features

- 🏗️ **Greenfield Design**: Step-by-step guidance for technology selection (SQL vs NoSQL vs Vector), schema design, and normalization.
- 🔍 **Database Auditing**: Proactive scanning for missing constraints, N+1 query problems, and architectural anti-patterns.
- 🐘 **PostgreSQL Mastery**: Deep dives into advanced PostgreSQL features, performance tuning, and serverless Postgres (Neon).
- 🔄 **Migration & Evolutions**: Strategies for zero-downtime schema migrations and ETL processes.
- 🔌 **ORM & Tooling Integration**: Expert guidance for Prisma, Drizzle ORM, and raw SQL optimization.

---

## 📚 Included Skills

| Skill | Directory | Primary Use Cases |
|-------|-----------|-------------------|
| **Database Fundamentals** | database/SKILL.md | Core concepts like ACID, BASE, CAP Theorem, and RDB constraints. |
| **Database Architect** | database-architect/SKILL.md | Selecting database technologies, planning scaling, and partitioning strategies. |
| **Database Design** | database-design/SKILL.md | Conceptual, logical, and physical schema modeling and normalization. |
| **Database Migration** | database-migration/SKILL.md | Planning zero-downtime schema changes and data migrations. |
| **Database Admin (DBA)** | database-admin/SKILL.md | Backup strategies, security, role-based access, and operational maintenance. |
| **PostgreSQL Expert** | postgresql/SKILL.md | Advanced Postgres usage, JSONB, text search, and indexing. |
| **Postgres Best Practices** | postgres-best-practices/SKILL.md | Supabase and Postgres performance rules and query optimization. |
| **SQL Pro** | sql-pro/SKILL.md | Writing advanced raw SQL, window functions, and complex aggregations. |
| **NoSQL Expert** | nosql-expert/SKILL.md | Designing for MongoDB, DynamoDB, Cassandra, and document stores. |
| **Vector DB Engineer** | vector-database-engineer/SKILL.md | Semantic search architectures using Pinecone, Qdrant, Milvus, and pgvector. |
| **Prisma Expert** | prisma-expert/SKILL.md | Schema-first ORM modeling, relations, and migration generation. |
| **Drizzle ORM Expert** | drizzle-orm-expert/SKILL.md | Code-first SQL-like ORM configuration and type-safe query building. |
| **Using Neon** | using-neon/SKILL.md | Serverless Postgres branching, auto-scaling, and bottomless storage. |

---

## ⚡ Quick Start

### 1. Copy to Your Project

Clone or copy the db-architect-skills directory into your .agents or project root:

```bash
cp -r db-architect-skills/ my-project/.agents/
```

### 2. Prompt Your AI Assistant

Open your AI coding assistant in the project directory and ask directly:

```text
"Act as a Database Architect. Audit my current schema.prisma file and tell me if there are any missing indexes or normalization issues."
```

```text
"Design a highly scalable NoSQL database schema for a real-time chat application."
```

---

## 🛠️ Architecture

```text
db-architect-skills/
├── AGENTS.md                                # Universal AI agent instructions & skill router
├── README.md                                # Project documentation
├── database/                                # Fundamentals (ACID, BASE, CAP, etc.)
├── database-architect/                      # Core architect skill
├── database-design/                         # Schema modeling
├── database-migration/                      # Schema evolution
├── database-admin/                          # Operations and security
├── postgresql/                              # Postgres deep-dives
├── postgres-best-practices/                 # Postgres tuning
├── sql-pro/                                 # Raw SQL expertise
├── nosql-expert/                            # Non-relational databases
├── vector-database-engineer/                # AI and embedding databases
├── prisma-expert/                           # Prisma ORM
├── drizzle-orm-expert/                      # Drizzle ORM
└── using-neon/                              # Serverless Postgres
```

---

## 💡 Example Prompts for AI Agents

**1. Codebase Audit & Refactoring:**
> *"Scan my current repository, read my Drizzle ORM schema files, and identify any missing foreign key constraints or indexes. Propose the necessary migration script to fix them."*

**2. Greenfield Project Design (Interactive Interview):**
> *"I am starting a new multi-tenant SaaS application. Interview me to figure out whether we should use PostgreSQL with row-level security or a NoSQL database, and then help me design the initial schema."*

**3. Performance Optimization:**
> *"We are experiencing slow query times on the dashboard. Use your SQL Pro and Postgres Best Practices skills to analyze my query structure and suggest covering indexes or materialized views."*

**4. Advanced Data Storage (AI/Vector):**
> *"I need to add a semantic search feature to my app. Guide me on whether to use pgvector in my existing Postgres database or spin up a dedicated vector database like Pinecone."*
