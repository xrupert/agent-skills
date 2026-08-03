---
name: chief-architect-and-architecture-patterns
description: Selects and governs application architecture before implementation. Use during PLAN and before BUILD for any non-trivial application.
stage: plan
command: /plan
category: architecture
inputs:
  - approved product specification
  - quality attributes and constraints
outputs:
  - architecture decision record
  - module and dependency map
  - testing and deployment strategy
quality_checks:
  - every major choice traces to a requirement
  - module boundaries have explicit responsibilities
  - simpler architecture was considered first
---

# Chief Architect and Architecture Patterns

## Overview
Act as the governing software architect above the implementation team. Choose the smallest architecture that satisfies current requirements while preserving clear evolution paths.

## Process
1. Extract functional requirements, quality attributes, regulatory needs, traffic assumptions, team constraints, and deployment targets.
2. Compare suitable forms: modular monolith, vertical slices, clean/hexagonal architecture, event-driven design, CQRS, microservices, and serverless boundaries.
3. Prefer a modular monolith unless independent scaling, fault isolation, ownership, or deployment needs justify distribution.
4. Define domain modules, public interfaces, dependency direction, data ownership, asynchronous boundaries, failure behavior, and observability.
5. Produce ADRs for stack, architecture, persistence, authentication, integration, caching, testing, and deployment choices.
6. Define architectural fitness checks: forbidden imports, cycle detection, module size limits, API contracts, and migration rules.
7. Review the proposed repository tree before code generation.

## Red Flags
- Framework choice presented as architecture.
- Microservices without ownership or independent scaling needs.
- Shared database tables across supposedly independent services.
- Business rules inside UI, transport, or persistence code.
- No failure, rollback, or migration strategy.

## Verification Requirements
- A junior developer can explain each module's purpose and dependencies.
- Every cross-module dependency is intentional and directional.
- At least one simpler alternative and its rejection reason are recorded.
- Architecture tests or lint rules enforce the declared boundaries.

## Exit Criteria
The blueprint contains an approved architecture, repository structure, interface map, data ownership model, quality strategy, and ADR set before BUILD begins.
