---
name: platform-limits-and-scale
description: Engineer Salesforce solutions that stay within governor limits and scale safely. Use when designing transactions, troubleshooting limit exceptions, or planning high-volume operations.
---

# Platform Limits and Scale Skill

## When to use

- Investigating `Too many SOQL queries`, CPU limit, or DML limit failures.
- Designing high-throughput data processing.
- Choosing between synchronous and asynchronous execution.
- Planning resilient retry behavior and workload partitioning.

## Instructions

1. Profile transaction shape first:
   - Records processed per transaction.
   - Number of related object lookups.
   - Expected automation fan-out.
2. Apply bulkification by default:
   - Query once, process collections, DML once per operation type.
3. Watch core synchronous limits:
   - SOQL queries.
   - DML statements.
   - CPU time.
   - Heap size.
4. Move heavy or fan-out work async:
   - Queueable for chained logic.
   - Batch for very large datasets.
   - Platform Events/CDC for decoupled processing.
5. Reduce lock contention:
   - Keep transactions short.
   - Order updates consistently for hot records.
6. Guard against repeated work:
   - Add idempotency keys/checks where retries may occur.
7. Instrument for supportability:
   - Add structured logs and correlation IDs in critical flows.

## Output expectations

When asked for optimization advice, provide:
- Root cause hypothesis tied to a specific limit.
- Refactor strategy with before/after transaction shape.
- Risk and rollback notes.
