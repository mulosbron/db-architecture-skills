# Database Architect Skills

Skills for two jobs: **auditing an existing database** or **designing one from scratch**. Pick the skills that match the stack in front of you; the rest stay unread.

## Skills

| Skill | Read when |
|---|---|
| `database-architect/SKILL.md` | Choosing a database or ORM, deciding on scaling, sharding, caching. Entry point for greenfield work. |
| `database-design/SKILL.md` | Modeling a schema or reviewing one for normalization, constraints, indexes. |
| `postgresql/SKILL.md` | Writing or reviewing any PostgreSQL schema. Contains PG-specific traps the model tends to miss. |
| `postgres-best-practices/SKILL.md` | Postgres query performance, connection pooling, RLS, locking. Routes to 30 rule files. |
| `database-migration/SKILL.md` | Changing a live schema without downtime. |
| `database-admin/SKILL.md` | Backups, roles, privileges, destructive operations. |
| `nosql-expert/SKILL.md` | DynamoDB, Cassandra, MongoDB modeling. |
| `prisma-expert/SKILL.md` | Project uses Prisma. |
| `drizzle-orm-expert/SKILL.md` | Project uses Drizzle. |
| `using-neon/SKILL.md` | Project runs on Neon. |

## How to work

**Do not produce a full schema or architecture on the first reply.**

1. **Ask first.** Greenfield or existing database? Expected read/write volume? Strict transactional consistency needed, or is eventual consistency fine? Team preference for ORM vs raw SQL? Deployment target (serverless, edge, self-hosted)? Skip questions the user already answered or the codebase answers.
2. **Scan the workspace** for `schema.prisma`, `drizzle.config.ts`, `*.sql`, migration folders, `.env` database URLs. Read them before proposing anything.
3. **Then propose.** For an audit: list concrete findings with the file and line, ordered by impact, each with a fix. For greenfield: give the technology choice with one reason, then the schema, then the first migration.

## Boundaries

- Recommend changes; do not edit schema or migration files unless asked.
- Never suggest running a destructive command (DROP, TRUNCATE, `migrate reset`, deleting a role) against a database that might be production without an explicit confirmation step.
- Draw an ERD only when asked.
- Do not default to PostgreSQL. SQLite or Turso may be the right answer for small or edge apps.
