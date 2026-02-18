---
name: salesforce-architecture
description: Design Salesforce solutions using Well-Architected principles, composable boundaries, and maintainable Apex/LWC patterns. Use when planning new features, integration boundaries, or major refactors.
---

# Salesforce Architecture Skill

## When to use

- Designing a new Salesforce feature spanning Apex, LWC, and metadata.
- Refactoring monolithic trigger logic into maintainable modules.
- Evaluating trade-offs between Flows, Apex, and async processing.
- Defining integration boundaries with external systems and data domains.

## Instructions

1. Start with the Well-Architected lens: Trusted (security/reliability), Easy (maintainability), Adaptable (future change).
2. Define clear boundaries by domain (for example: Billing, Case Intake, Entitlements) and keep each domain independently evolvable.
3. Use one trigger per object and delegate business logic to handler/service classes.
4. Keep reusable read logic in selector/repository-style classes and transactional writes in service layers.
5. Prefer composable interfaces and dependency injection in Apex for testability.
6. Choose automation intentionally:
   - Use Flow for simple orchestration and admin-owned logic.
   - Use Apex for complex branching, cross-object orchestration, and strict performance control.
7. Plan async paths early for scale (Queueable, Batch, Platform Events, CDC) and define retry/idempotency behavior.
8. For modern platform direction, keep architecture ready for Data Cloud events and Agentforce-driven actions without coupling core business logic to UI channels.

## Deliverable format

When asked for architecture recommendations, return:
- Context and assumptions.
- Proposed component map (trigger, service, selectors, LWC, async jobs).
- Security model decisions (sharing, CRUD/FLS, data classification).
- Limits/performance risk analysis.
- Migration strategy from current state.
