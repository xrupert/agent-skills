---
name: harness-engineering
description: Builds controlled execution environments that make agents, generators, integrations, and workflows reproducible, observable, bounded, and testable. Use during PLAN, BUILD, VERIFY, and operations.
stage: build
command: /build
category: agent-systems
inputs:
  - workflow or agent contract
  - tools models data and environment constraints
outputs:
  - execution harness
  - fixtures and replay artifacts
  - safety and resource limits
quality_checks:
  - runs are reproducible and traceable
  - side effects are isolated
  - budgets and termination conditions are enforced
---

# Harness Engineering

A harness is the controlled shell around uncertain or external behavior. It turns prompts, tools, models, browsers, APIs, databases, and generated code into an executable experiment with evidence.

## Process
1. Define the run contract: typed inputs, expected outputs, allowed side effects, environment, model/tool versions, seed data, and acceptance criteria.
2. Isolate execution with temporary workspaces, sandboxed processes, scoped credentials, network allowlists, and disposable data.
3. Provide deterministic fixtures for time, IDs, randomness, external APIs, repositories, and database state.
4. Capture prompts, responses, tool calls, files changed, stdout, stderr, network traces, metrics, costs, timings, and exit reasons.
5. Enforce token, cost, time, retry, file-size, process, memory, network, and recursion budgets.
6. Add checkpoint, resume, replay, dry-run, cancellation, and cleanup behavior.
7. Compare outputs against schemas, golden artifacts, invariants, tests, and policy gates.
8. Store a run manifest with provenance so failures can be reproduced.

## Harness Layers
- Input harness: validation, normalization, fixtures.
- Execution harness: sandbox, tool permissions, resource budgets.
- Observation harness: logs, traces, artifacts, costs.
- Evaluation harness: assertions, graders, differential comparison.
- Recovery harness: retries, resume, rollback, cleanup.

## Red Flags
- Agent or generator runs directly against production resources.
- Failures cannot be replayed.
- Retries duplicate irreversible side effects.
- Success is inferred from a model statement.
- Temporary files, credentials, or processes survive cancellation.

## Verification Requirements
- Identical fixtures produce explainably comparable runs.
- Every side effect has an idempotency or rollback strategy.
- Budget exhaustion terminates safely.
- Run artifacts identify exact versions and inputs.
- At least one failure is reproduced from captured evidence.

## Exit Criteria
The workflow operates inside a bounded, observable, replayable harness whose evidence—not agent confidence—determines success.
