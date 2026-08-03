---
name: anti-pattern-and-code-health-engineering
description: Detects structural debt and prevents common architecture, data, UI, testing, and operational anti-patterns. Use during PLAN, BUILD, REVIEW, and migration work.
stage: review
command: /review
category: code-health
inputs:
  - codebase or blueprint
  - change diff and quality goals
outputs:
  - prioritized smell report
  - behavior-preserving remediation plan
  - prevention checks
quality_checks:
  - findings cite concrete evidence
  - remediation preserves behavior
  - prevention is automated where practical
---

# Anti-Pattern and Code Health Engineering

## Scan Order
1. God modules, long functions, mixed abstraction levels, deep nesting, hidden side effects, duplicated policy, and dead code.
2. Cycles, inappropriate dependencies, leaky boundaries, feature envy, shotgun surgery, and shared mutable state.
3. N+1 queries, unbounded reads, unsafe migrations, missing constraints, and cross-tenant exposure.
4. React effect misuse, unstable dependencies, state duplication, prop drilling, and server/client boundary confusion.
5. Brittle tests, over-mocking, flaky timing, snapshot dependence, and missing negative paths.
6. Secret leakage, raw external errors, permissive tools, missing rate limits, and unaudited actions.
7. Manual deployment steps, noisy alerts, missing rollback, and undocumented operational ownership.

## Process
- Rank each smell by blast radius, likelihood, change frequency, and remediation risk.
- Separate correctness defects from maintainability concerns.
- Apply characterization tests before high-risk extraction.
- Prefer naming, pure-policy extraction, cohesive modules, explicit contracts, and shallow control flow.
- Record intentional debt with owner, trigger, and expiration condition.
- Add architecture tests, lint rules, complexity budgets, or CI checks to prevent recurrence.

## Rationalizations to Reject
- “It works, so structure does not matter.”
- “We will test it later.”
- “This abstraction may be useful someday.”
- “The framework requires this coupling.”
- “A comment explains the confusing code.”

## Verification Requirements
- A junior developer can explain the changed flow without oral history.
- Public behavior and data contracts are protected by tests.
- Complexity and duplication decrease measurably.
- No new warnings, unsafe casts, or hidden global dependencies are introduced.

## Exit Criteria
High-risk smells are fixed or explicitly accepted, and automated guardrails protect the improved structure.
