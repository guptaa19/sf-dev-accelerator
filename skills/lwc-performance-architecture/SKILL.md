---
name: lwc-performance-architecture
description: Build performant and maintainable Lightning Web Components with correct data access, rendering, and lifecycle patterns. Use when creating or optimizing LWC features.
---

# LWC Performance and Architecture Skill

## When to use

- Building net-new LWC screens and flows.
- Diagnosing slow page loads or UI lag.
- Refactoring component composition and data fetching.
- Reviewing event handling and re-render behavior.

## Instructions

1. Prefer standard platform data layers first:
   - Lightning Data Service and UI API where possible.
   - Apex only when server-side custom logic is required.
2. Minimize server round trips:
   - Reuse fetched data via shared service modules where appropriate.
   - Cache aggressively when data staleness tolerance allows.
3. Design component boundaries intentionally:
   - Keep components focused and small.
   - Avoid deeply nested dynamic trees unless necessary.
4. Optimize lists:
   - Use `for:each`/`iterator` with stable unique `key` values.
   - Paginate or virtualize large datasets.
5. Manage event lifecycles safely:
   - Use event delegation when possible.
   - Remove external listeners in `disconnectedCallback`.
6. Reduce rendering churn:
   - Avoid unnecessary reactive state mutations.
   - Compute expensive values once per state change.
7. Maintain UX quality:
   - Include loading, empty, and error states.
   - Preserve accessibility semantics and keyboard navigation.

## Review checklist

- Data source choice justified (LDS/UI API/Apex).
- No unnecessary duplicate fetches.
- Stable keys in all repeated templates.
- Listener cleanup present for window/document integrations.
