---
name: loop-engineering
description: Designs bounded iterative improvement loops for agents, code generation, repair, evaluation, and operations. Use whenever a workflow observes results and decides whether to retry, revise, escalate, or stop.
stage: build
command: /build
category: agent-systems
inputs:
  - goal and measurable evaluator
  - candidate action set
  - budgets and escalation policy
outputs:
  - explicit loop state machine
  - termination and recovery rules
  - loop telemetry
quality_checks:
  - progress is measurable
  - termination is guaranteed by policy
  - repeated side effects are safe
---

# Loop Engineering

## Core Model
Every loop must explicitly define: state, observation, evaluator, action selection, mutation, checkpoint, budget, stop condition, and escalation path.

## Process
1. State the objective as measurable invariants or a scored evaluator—not “make it better.”
2. Define the smallest loop state needed to resume safely, including attempt number, artifacts, evidence, and side-effect ledger.
3. Separate observation from judgment and judgment from action.
4. Choose bounded actions: regenerate one chunk, repair one defect class, ask for clarification, invoke a tool, roll back, or escalate.
5. Require each iteration to produce new evidence or terminate as stalled.
6. Cap attempts, elapsed time, tokens, cost, changed files, and repeated identical failures.
7. Detect oscillation, regression, evaluator gaming, local optima, and no-progress states.
8. Checkpoint accepted progress and make retries idempotent.
9. Escalate uncertainty or irreversible decisions to a human or higher-authority policy.
10. Emit a final loop report explaining attempts, deltas, unresolved issues, and exit reason.

## Loop Types
- Generate → validate → repair.
- Plan → execute → observe → replan.
- Test → localize → fix → guard.
- Retrieve → grade → refine query.
- Deploy → observe → promote or rollback.

## Red Flags
- `while true` with confidence-based stopping.
- Retrying the same prompt without changing evidence or strategy.
- A model grades its own output without independent checks.
- Successful partial work is discarded on every retry.
- External side effects occur before validation.

## Verification Requirements
- Tests cover success, recoverable failure, repeated failure, oscillation, cancellation, budget exhaustion, and resume.
- Loop telemetry shows state transitions and progress deltas.
- Identical idempotency keys cannot duplicate side effects.
- The loop always reaches a declared terminal state.

## Exit Criteria
The iterative workflow is a tested bounded state machine with observable progress, safe checkpoints, explicit budgets, and honest escalation.
