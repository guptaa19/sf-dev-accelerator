---
name: salesforce-unit-testing
description: Build robust Apex and LWC test strategies that prioritize behavior, not only coverage. Use when writing, reviewing, or stabilizing unit and integration tests on Salesforce.
---

# Salesforce Unit Testing Skill

## When to use

- Adding tests for new Apex classes, triggers, and asynchronous jobs.
- Improving flaky or low-value tests.
- Preparing deployment gates for production.
- Verifying permission-sensitive behavior and sharing rules.

## Instructions

1. Start with behavior-driven test cases:
   - Positive path.
   - Negative path.
   - Bulk path.
   - Permission/sharing path.
2. Use a test data strategy:
   - `@testSetup` for common fixtures.
   - Test data factory methods for readability and reuse.
   - No dependency on org production data.
3. Isolate execution limits and async behavior:
   - Wrap the unit-under-test in `Test.startTest()` and `Test.stopTest()`.
4. Assert outcomes, not just coverage:
   - Validate field state, side effects, and emitted records/events.
   - Avoid tests that pass without meaningful assertions.
5. Mock external dependencies:
   - HTTP callouts use mocks.
   - Stub service interfaces for deterministic tests.
6. Include security-aware tests:
   - Use `System.runAs` for profile/permission-set scenarios.
   - Validate behavior for both authorized and unauthorized users.
7. Keep tests independent and deterministic:
   - No ordering assumptions.
   - No timestamp/race-condition brittleness.

## Deployment test posture

- Validate with focused suites during feature development.
- Use `RunLocalTests` (or stricter) before production deploy.
- Track slow tests and continuously remove unnecessary setup overhead.
