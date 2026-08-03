---
name: ai-agent-systems-engineering
description: Designs reliable AI features, tool-using agents, retrieval systems, memory, evaluations, and guardrails. Use during PLAN, BUILD, VERIFY, and REVIEW.
stage: build
command: /build
category: ai
inputs:
  - AI use cases and risk tolerance
  - available models tools and data
outputs:
  - AI system design
  - evaluation suite
  - safety and cost controls
quality_checks:
  - deterministic software handles deterministic work
  - model behavior has measurable evaluations
  - tools and data access follow least privilege
---

# AI and Agent Systems Engineering

## Process
1. Define the exact task, user value, unacceptable outcomes, latency, cost, privacy, and human-approval requirements.
2. Decide whether the task needs rules, search, retrieval, classification, generation, tool use, workflow orchestration, or an autonomous agent.
3. Define structured inputs and outputs with schemas; reject malformed model output.
4. Ground responses with approved sources, retrieval filters, provenance, and freshness rules when factuality matters.
5. Design tools with narrow permissions, idempotency, timeouts, retries, budgets, and auditable side effects.
6. Treat memory as typed data with scope, retention, deletion, and contamination controls.
7. Build offline and online evaluations covering correctness, refusal, grounding, tool choice, safety, latency, and cost.
8. Add fallbacks, confidence thresholds, human review, circuit breakers, and observability.

## Red Flags
- Using an agent where a deterministic function suffices.
- Unbounded tool loops or recursive delegation.
- Prompts as the only enforcement boundary.
- Retrieval without authorization filtering.
- No evaluation dataset or production feedback signal.

## Verification Requirements
- Representative golden cases and adversarial cases pass defined thresholds.
- Tool calls are schema validated and least privileged.
- Costs, latency, failures, and model versions are observable.
- Sensitive content is not retained or exposed unexpectedly.
- Human approval gates protect irreversible actions.

## Exit Criteria
The AI feature has an explicit architecture, evaluation evidence, tool boundary, fallback behavior, safety controls, and operational budget.
