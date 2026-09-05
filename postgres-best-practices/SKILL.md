---
name: postgres-best-practices
description: "Database creation, auditing, and optimization framework for postgres-best-practices. Use when building from scratch or detecting errors and anti-patterns."
risk: safe
source: community
date_added: "2026-02-27"
---
## Agent Execution Flow (IMPORTANT)
1. **Information Gathering:** Ask clarifying questions to determine context (greenfield vs existing), constraints, and requirements before proposing a solution.
2. **Context Scanning:** Scan the workspace (`list_dir`, `view_file`) to understand current architecture, schemas, and code.
3. **Analyze & Propose:** Once context is fully understood, formulate your architecture strategy or design pattern recommendation.

# Supabase Postgres Best Practices

Comprehensive performance optimization guide for Postgres, maintained by Supabase. Contains rules across 8 categories, prioritized by impact to guide automated query optimization and schema design.

## When to Use
Reference these guidelines when:
- Writing SQL queries or designing schemas
- Implementing indexes or query optimization
- Reviewing database performance issues
- Configuring connection pooling or scaling
- Optimizing for Postgres-specific features
- Working with Row-Level Security (RLS)

## Rule Categories by Priority

| Priority | Category | Impact | Prefix |
|----------|----------|--------|--------|
| 1 | Query Performance | CRITICAL | `query-` |
| 2 | Connection Management | CRITICAL | `conn-` |
| 3 | Security & RLS | CRITICAL | `security-` |
| 4 | Schema Design | HIGH | `schema-` |
| 5 | Concurrency & Locking | MEDIUM-HIGH | `lock-` |
| 6 | Data Access Patterns | MEDIUM | `data-` |
| 7 | Monitoring & Diagnostics | LOW-MEDIUM | `monitor-` |
| 8 | Advanced Features | LOW | `advanced-` |

## How to Use

Read individual rule files for detailed explanations and SQL examples:

```
rules/query-missing-indexes.md
rules/schema-partial-indexes.md
rules/_sections.md
```

Each rule file contains:
- Brief explanation of why it matters
- Incorrect SQL example with explanation
- Correct SQL example with explanation
- Optional EXPLAIN output or metrics
- Additional context and references
- Supabase-specific notes (when applicable)

## Full Compiled Document

For the complete guide with all rules expanded: `AGENTS.md`

### When to Use
This skill is applicable to execute the workflow or actions described in the overview.


## 🔍 Auditing Protocol
When auditing postgres-best-practices architecture or code:
1. **Analyze Constraints**: Check if best practices are followed.
2. **Identify Anti-patterns**: Look for performance bottlenecks or security flaws.
3. **Validate Architecture**: Ensure the implementation aligns with domain requirements.

## 🏗️ Creation Protocol
When creating from scratch using postgres-best-practices:
1. **Plan Architecture**: Define the schema, types, and connections.
2. **Enforce Security**: Apply least privilege and necessary rules.
3. **Optimize**: Implement indexes or necessary performance tweaks early.

## ✅ Validation Checklist
- [ ] Requirements fully met.
- [ ] Best practices for postgres-best-practices applied.
- [ ] No anti-patterns detected.

## Limitations
- Use this skill only when the task clearly matches the scope described above.
- Do not treat the output as a substitute for environment-specific validation, testing, or expert review.
- Stop and ask for clarification if required inputs, permissions, safety boundaries, or success criteria are missing.


