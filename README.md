# Database Architect Skills

Skill files that turn an AI coding agent into a database architect for two jobs:

1. **Improve an existing database**: find missing constraints, wrong types, missing indexes, slow queries, unsafe migrations.
2. **Design a database from scratch**: pick the technology, model the schema, write the first migration.

Every file follows one rule: it contains only what the model cannot know on its own. Project preferences, sharp prohibitions, Postgres traps the model keeps missing, and the instruction to fetch live docs instead of guessing. No tutorials, no capability lists, no "you are a world-class DBA". The whole set is about 450 lines.

## Install

Copy the folder into your project (or your global agents directory) so the agent finds `AGENTS.md`:

```bash
cp -r db-architect-skills/ my-project/.agents/
```

Agents that read `AGENTS.md` (Claude Code, Codex, Cursor, Windsurf and others) pick up the skill table and load individual skills on demand.

## How it works

`AGENTS.md` tells the agent to **ask before building**. On a database request it first asks what it does not already know (greenfield or existing, load profile, consistency needs, ORM preference, deployment target), then scans the workspace for `schema.prisma`, `drizzle.config.ts`, `.sql` files and migrations, and only then proposes. You can skip the interview by answering those questions in your first prompt.

The agent will not edit schema or migration files unless you ask, and will not propose destructive commands against a database that might be production without a confirmation step.

## Skills

| Skill | Use it for |
|---|---|
| `database-architect/` | Technology and ORM choice, scaling, caching. Greenfield entry point. |
| `database-design/` | Schema modeling and schema audit checklist. |
| `postgresql/` | Postgres types, traps, constraints, indexes, partitioning, JSONB. |
| `postgres-best-practices/` | Supabase rule set: 30 files on query performance, pooling, RLS, locking. |
| `database-migration/` | Zero-downtime schema changes, backfills, rollbacks. |
| `database-admin/` | Backups, roles, destructive-operation safety. |
| `nosql-expert/` | DynamoDB, Cassandra, MongoDB modeling and audit. |
| `prisma-expert/` | Projects using Prisma. |
| `drizzle-orm-expert/` | Projects using Drizzle. |
| `using-neon/` | Projects on Neon serverless Postgres. |

## Example prompts

### Improving an existing database

**1. Full schema audit**

> Audit the database layer of this repo. Read the Prisma schema and migrations, then list every missing foreign key, missing index on a filtered or FK column, nullable column that should be required, and type that should change (money, timestamps). Order by impact. For each, give the migration SQL. Do not edit files.

**2. Slow query investigation**

> The orders dashboard query in `src/queries/orders.ts` takes 4 seconds on 2M rows. Here is the `EXPLAIN (ANALYZE, BUFFERS)` output: [paste]. Tell me what the plan shows, which index or query change fixes it, and what it costs on writes.

### Designing from scratch

**3. Guided greenfield design**

> I am building a multi-tenant SaaS for invoicing. Node and TypeScript, deploying to Vercel. Interview me for anything else you need, then recommend the database and ORM, design the schema with tenant isolation, and write the first migration.

**4. Known requirements, skip the interview**

> New project: event ticketing. Postgres on Neon, Drizzle, roughly 50 reads per write, bookings must never double-sell a seat. Design the schema. Use an exclusion constraint or equivalent for the seat-hold rule and explain the trade-off you chose for seat inventory under contention.

### Mixed

**5. Safe migration on live data**

> We need to rename `users.fullname` to `users.display_name` and change `orders.total` from `FLOAT` to `NUMERIC(12,2)` without downtime. The app deploys continuously. Give me the migration sequence and the application changes needed at each step.

**6. Should we leave Postgres?**

> Our activity feed table grows 20M rows a day and feed reads are slowing down. Should this move to DynamoDB, be partitioned in Postgres, or something else? Ask what you need, then recommend one option with its operational cost.

## Layout

```text
db-architect-skills/
├── AGENTS.md                  # skill table, interview rule, boundaries
├── README.md
├── SKILL-AUDIT.md             # the audit that produced this layout
├── database-architect/
├── database-design/
├── postgresql/
├── postgres-best-practices/   # SKILL.md + rules/*.md
├── database-migration/
├── database-admin/
├── nosql-expert/
├── prisma-expert/
├── drizzle-orm-expert/
└── using-neon/
```

## Adding to the set

Before adding a line, ask: can the model already do this on its own? If yes, leave it out. Add a line only for a project preference, a mistake the model keeps making, a hard boundary, or a pointer to live documentation. Keep each `SKILL.md` under 100 lines and give it a one-sentence `description` that says exactly when to read it; the description is what triggers the skill.
