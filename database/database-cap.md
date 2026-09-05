# CAP Theorem and Database Criteria

The CAP Theorem is a fundamental principle in the design and selection of distributed database systems. According to the theorem, a distributed system can simultaneously guarantee **only two of the following three** characteristics. This framework helps teams choose the right database architecture (Relational vs. NoSQL) based on application requirements.

## 1. CAP Criteria

*   **Consistency**: Every read receives the most recent write. Data is synchronized instantly across all nodes in the distributed system. When a change is made on one server, it is immediately reflected on all others, ensuring every user sees the exact same updated data. This is critical for applications like banking and finance.
*   **Availability**: Every request receives a non-error response, without the guarantee that it contains the most recent write. The system will always return data, even if it is outdated. This is prioritized in systems where uptime is more important than immediate accuracy, such as social media feeds.
*   **Partition Tolerance**: The system continues to operate despite an arbitrary number of messages being dropped (or delayed) by the network between nodes. If a network connection breaks down or a node fails, the rest of the system must remain functional.

## 2. CAP Architectures and Database Classification

Depending on your application's needs, you must prioritize two of these characteristics:

### A. CA Systems (Consistency + Availability)
*   **Focus**: Prioritizes Consistency and Availability; Partition Tolerance is sacrificed.
*   **Outcome**: If a network partition occurs, the system will block transactions (sacrificing availability temporarily) or lock down to prevent inconsistent data states.
*   **Databases**: Traditional Relational Databases (RDBMS) typically follow this architecture (e.g., Oracle, MySQL, PostgreSQL, MSSQL).

### B. CP Systems (Consistency + Partition Tolerance)
*   **Focus**: Prioritizes Consistency and Partition Tolerance; Availability is sacrificed.
*   **Outcome**: If a node gets disconnected, the system will prevent access to that specific node to maintain data consistency across the network (e.g., an ATM displaying "Out of Service").
*   **Databases**: Many NoSQL systems follow this model, such as MongoDB, HBase, Redis, and BigTable.

### C. AP Systems (Availability + Partition Tolerance)
*   **Focus**: Prioritizes Availability and Partition Tolerance; Consistency (immediate) is sacrificed.
*   **Outcome**: Even if servers lose connection to one another, the system continues to serve requests. The data returned may be stale, but the system achieves "Eventual Consistency" once the network recovers.
*   **Databases**: Distributed NoSQL systems like Cassandra, CouchDB, and DynamoDB.

*(Note: In upcoming topics regarding database approaches, we will cover ACID principles for RDBMS and BASE principles for NoSQL.)*
