---
name: apex-design-patterns
description: Apply Apex design patterns for scalable and bulk-safe code. Use when implementing or reviewing triggers, services, selectors, and integration classes.
---

# Apex Design Patterns Skill

## When to use

- Building new Apex business logic.
- Reviewing trigger quality and maintainability.
- Refactoring code with governor-limit or testability problems.
- Adding integration or domain orchestration flows.

## Instructions

1. Enforce trigger discipline:
   - One trigger per object.
   - Keep trigger thin and delegate to a handler.
2. Apply bulk-safe collection patterns:
   - Build `Set<Id>` / `Map<Id, SObject>` first.
   - Query once, process in-memory, DML once per operation type.
3. Separate concerns:
   - Handler: entry orchestration and event branching.
   - Service/Domain: business rules.
   - Selector/Repository: query composition.
   - DTO/Mapper: integration payload mapping.
4. Use transaction-safe patterns:
   - Guard against recursion explicitly.
   - Prefer idempotent updates where feasible.
   - Use savepoints cautiously for partial-failure recovery.
5. Design for testability:
   - Use interfaces and injectable dependencies.
   - Keep side effects in a small number of seams.
6. Design for security:
   - Use `with sharing` unless a stronger reason exists.
   - Enforce object/field permissions where data is read or written.
   - Sanitize outbound responses with `Security.stripInaccessible` when needed.

## Code review checklist

- No SOQL/DML/callouts inside loops.
- No mixed responsibilities in trigger classes.
- Clear failure handling and user-safe error messages.
- Meaningful logging and traceability for support teams.
