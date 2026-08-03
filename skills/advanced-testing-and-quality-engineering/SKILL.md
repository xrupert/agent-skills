---
name: advanced-testing-and-quality-engineering
description: Builds risk-based unit, integration, contract, browser, accessibility, performance, and resilience test systems. Use during PLAN, VERIFY, and REVIEW.
stage: verify
command: /test
category: quality
inputs:
  - architecture and acceptance criteria
  - risk assessment
outputs:
  - test strategy
  - automated quality gates
  - evidence report
quality_checks:
  - tests target behavior and risk
  - critical flows run in realistic environments
  - failures produce actionable evidence
---

# Advanced Testing and Quality Engineering

## Process
1. Rank risks by impact, likelihood, change frequency, and observability.
2. Map each risk to the cheapest reliable proof: pure unit test, component test, integration test, database test, contract test, browser test, accessibility test, performance test, security test, or resilience experiment.
3. Use test data factories and deterministic clocks, IDs, and provider fakes.
4. Test boundaries: authentication, permissions, persistence, external APIs, queues, webhooks, migrations, and generated artifacts.
5. Add consumer/provider contracts for interfaces owned by different modules or services.
6. Run critical user journeys in a real browser and capture console, network, and visual evidence.
7. Define performance budgets, load profiles, accessibility gates, mutation targets, and flaky-test policy where appropriate.
8. Require regression tests for every confirmed defect.

## Red Flags
- Coverage percentage used as the only quality measure.
- Mocking the behavior under test.
- Snapshot tests replacing assertions about outcomes.
- E2E-only suites that are slow and difficult to diagnose.
- Tests that pass without proving data isolation or side effects.

## Verification Requirements
- Every critical requirement maps to executable evidence.
- Negative and failure paths are tested.
- CI runs deterministic tests on a clean checkout.
- Browser tests verify console and network health.
- Performance and accessibility results meet declared budgets.

## Exit Criteria
The repository contains a layered, risk-based test system and a machine-verifiable report proving the selected release mode.
