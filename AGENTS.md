# Database Architect Skills — Agent Instructions

## Overview
This directory contains specialized database architecture skills derived from best practices in data modeling, schema design, database optimization, scaling, and NoSQL/Vector/SQL technology selection.

## Available Skills

### Foundation & Modeling
| Skill | Directory | Activate When |
|-------|-----------|---------------|
| **Database Fundamentals** | `database/SKILL.md` | User asks about ACID, BASE, CAP Theorem, or core RDB constraints. |
| **Database Architect** | `database-architect/SKILL.md` | User needs help selecting database technologies, scaling, or partitioning. |
| **Database Design** | `database-design/SKILL.md` | User needs schema modeling (conceptual/logical/physical) or normalization. |

### Relational & Advanced SQL
| Skill | Directory | Activate When |
|-------|-----------|---------------|
| **PostgreSQL Expert** | `postgresql/SKILL.md` | User needs advanced Postgres features (JSONB, text search, extensions). |
| **Postgres Best Practices** | `postgres-best-practices/SKILL.md` | User needs to optimize Supabase or Postgres performance. |
| **SQL Pro** | `sql-pro/SKILL.md` | User asks to write or optimize raw SQL, window functions, CTEs. |

### NoSQL & AI/Vector Data
| Skill | Directory | Activate When |
|-------|-----------|---------------|
| **NoSQL Expert** | `nosql-expert/SKILL.md` | User is using MongoDB, DynamoDB, Cassandra, or document stores. |
| **Vector DB Engineer** | `vector-database-engineer/SKILL.md` | User is implementing semantic search (Pinecone, Qdrant, Milvus, pgvector). |

### Operations, Cloud & Migrations
| Skill | Directory | Activate When |
|-------|-----------|---------------|
| **Database Migration** | `database-migration/SKILL.md` | User is planning schema changes, migrations, or ETL processes. |
| **Database Admin** | `database-admin/SKILL.md` | User needs help with backups, security, RBAC, or maintenance operations. |
| **Using Neon** | `using-neon/SKILL.md` | User asks about serverless Postgres branching or bottomless storage. |

### ORMs & Application Integration
| Skill | Directory | Activate When |
|-------|-----------|---------------|
| **Prisma Expert** | `prisma-expert/SKILL.md` | User is working with Prisma ORM. |
| **Drizzle ORM Expert** | `drizzle-orm-expert/SKILL.md` | User is working with Drizzle ORM. |

## Agent Execution Flow (IMPORTANT)

When a user requests assistance using these database architecture skills, **DO NOT generate a complete schema or architecture immediately**. Instead, follow this step-by-step flow:

1. **Information Gathering (Ask First):** Ask the user clarifying questions. Are they starting a greenfield project or modifying an existing database? What are the expected read/write loads? Do they have strict ACID requirements or can they use BASE? What is the team's familiarity with ORMs vs raw SQL?
2. **Context Scanning:** Use your available tools (`list_dir`, `view_file`, or `grep_search`) to deeply scan the user's workspace. Look for existing `schema.prisma`, `schema.sql`, `drizzle.config.ts`, or migration files to understand the current state before proposing changes.
3. **Analyze & Propose:** Based on the gathered answers and your codebase scan, use the appropriate skills (from the directories above) to design schemas, write migrations, or recommend optimizations.

## How to Use These Skills

### Method 1: Automatic Context Loading
AI agents automatically read `AGENTS.md` in the project root. When starting a conversation about databases, the agent has immediate access to these skill definitions.

### Method 2: Auto-Activation by Topic
Agents will naturally activate the appropriate skill based on request keywords:
- "ACID", "BASE", "CAP theorem", "normalization", "1NF" → `database`
- "scale DB", "partitioning", "sharding", "choose database" → `database-architect`
- "schema design", "ERD", "data modeling" → `database-design`
- "postgres", "jsonb", "pg_stat_statements", "supabase" → `postgresql` and `postgres-best-practices`
- "raw SQL", "window function", "complex join", "CTE" → `sql-pro`
- "mongodb", "dynamodb", "nosql", "document store" → `nosql-expert`
- "vector search", "RAG", "pinecone", "pgvector", "embeddings" → `vector-database-engineer`
- "zero downtime migration", "schema evolution" → `database-migration`
- "backup", "RBAC", "grant privileges", "database security" → `database-admin`
- "serverless postgres", "neon", "database branching" → `using-neon`
- "prisma", "schema.prisma" → `prisma-expert`
- "drizzle", "drizzle-orm", "schema.ts" → `drizzle-orm-expert`

## Protocols

### 🔍 Auditing Protocol
These skills are equipped to evaluate existing database setups. When auditing, the skills will check for missing constraints, incorrect indexing, security flaws, and architectural anti-patterns.

### 🏗️ Creation Protocol
When creating databases from scratch, these skills will guide you to select the right technology, design normalized schemas, and enforce data integrity at the database layer.
