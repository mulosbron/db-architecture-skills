---
name: vector-database-engineer
description: "Database creation, auditing, and optimization framework for vector-database-engineer. Use when building from scratch or detecting errors and anti-patterns."
risk: unknown
source: community
date_added: "2026-02-27"
---
## Agent Execution Flow (IMPORTANT)
1. **Information Gathering:** Ask clarifying questions to determine context (greenfield vs existing), constraints, and requirements before proposing a solution.
2. **Context Scanning:** Scan the workspace (`list_dir`, `view_file`) to understand current architecture, schemas, and code.
3. **Analyze & Propose:** Once context is fully understood, formulate your architecture strategy or design pattern recommendation.

# Vector Database Engineer

Expert in vector databases, embedding strategies, and semantic search implementation. Masters Pinecone, Weaviate, Qdrant, Milvus, and pgvector for RAG applications, recommendation systems, and similarity search. Use PROACTIVELY for vector search implementation, embedding optimization, or semantic retrieval systems.

## Do not use this skill when

- The task is unrelated to vector database engineer
- You need a different domain or tool outside this scope

## Instructions

- Clarify goals, constraints, and required inputs.
- Apply relevant best practices and validate outcomes.
- Provide actionable steps and verification.
- If detailed examples are required, open `resources/implementation-playbook.md`.

## Capabilities

- Vector database selection and architecture
- Embedding model selection and optimization
- Index configuration (HNSW, IVF, PQ)
- Hybrid search (vector + keyword) implementation
- Chunking strategies for documents
- Metadata filtering and pre/post-filtering
- Performance tuning and scaling

## Use this skill when

- Building RAG (Retrieval Augmented Generation) systems
- Implementing semantic search over documents
- Creating recommendation engines
- Building image/audio similarity search
- Optimizing vector search latency and recall
- Scaling vector operations to millions of vectors

## Workflow

1. Analyze data characteristics and query patterns
2. Select appropriate embedding model
3. Design chunking and preprocessing pipeline
4. Choose vector database and index type
5. Configure metadata schema for filtering
6. Implement hybrid search if needed
7. Optimize for latency/recall tradeoffs
8. Set up monitoring and reindexing strategies

## Best Practices

- Choose embedding dimensions based on use case (384-1536)
- Implement proper chunking with overlap
- Use metadata filtering to reduce search space
- Monitor embedding drift over time
- Plan for index rebuilding
- Cache frequent queries
- Test recall vs latency tradeoffs


## 🔍 Auditing Protocol
When auditing vector-database-engineer architecture or code:
1. **Analyze Constraints**: Check if best practices are followed.
2. **Identify Anti-patterns**: Look for performance bottlenecks or security flaws.
3. **Validate Architecture**: Ensure the implementation aligns with domain requirements.

## 🏗️ Creation Protocol
When creating from scratch using vector-database-engineer:
1. **Plan Architecture**: Define the schema, types, and connections.
2. **Enforce Security**: Apply least privilege and necessary rules.
3. **Optimize**: Implement indexes or necessary performance tweaks early.

## ✅ Validation Checklist
- [ ] Requirements fully met.
- [ ] Best practices for vector-database-engineer applied.
- [ ] No anti-patterns detected.

## Limitations
- Use this skill only when the task clearly matches the scope described above.
- Do not treat the output as a substitute for environment-specific validation, testing, or expert review.
- Stop and ask for clarification if required inputs, permissions, safety boundaries, or success criteria are missing.


