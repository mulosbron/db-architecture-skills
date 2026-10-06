---
name: nosql-expert
description: "DynamoDB, Cassandra/ScyllaDB and MongoDB data modeling: access-pattern-first design, partition keys, single-table design. Read when designing or auditing a NoSQL schema, or when deciding whether NoSQL fits at all."
---

# NoSQL Modeling

## Before designing: is NoSQL the right call?

Choose DynamoDB or Cassandra only when the access patterns are known up front and stable, write volume is very high, and the data does not need ad-hoc joins or transactions across entities. Otherwise PostgreSQL is simpler and the model will push back on a NoSQL request that does not meet these conditions.

## Design order

1. Write down every query the application will run, with its filter and sort. This list is the schema.
2. For each query, pick the partition key that answers it in one request, and the sort/clustering key for ordering and range.
3. Duplicate data freely so each query hits one partition. Updates to duplicated data are the price; make that explicit.
4. DynamoDB: default to single-table design with generic `PK` / `SK` and GSIs for secondary patterns. Cassandra: one table per query.

## Audit checklist

- Every access pattern maps to a specific table, GSI or materialized view. No pattern relies on a scan.
- Partition key cardinality is high enough to spread traffic. Date-only or status-only keys create hot partitions.
- No single partition grows without bound. Shard with a suffix (`USER#123#2024-01`) past about 10 GB or many millions of items.
- Eventual consistency is acceptable for each read path that uses a GSI or a non-quorum read.
- Items under the size limit (400 KB DynamoDB); lists inside items are bounded.
- MongoDB: embedded documents for data read together and bounded in size; references for unbounded or shared data; indexes on every filter field.

## Anti-patterns

- Scatter-gather scans to find one item.
- Modeling `Author` and `Book` as separate tables and joining in application code.
- Using a NoSQL store for data that needs multi-entity transactions or reporting queries.
