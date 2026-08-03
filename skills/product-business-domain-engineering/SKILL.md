---
name: product-business-domain-engineering
description: Converts product goals into measurable requirements, domain models, workflows, and viable business mechanics. Use during DEFINE and PLAN.
stage: define
command: /spec
category: product
inputs:
  - product idea
  - target users
  - business constraints
outputs:
  - product requirements
  - domain model
  - success metrics
  - pricing and growth assumptions
quality_checks:
  - requirements are testable
  - domain language is consistent
  - metrics connect to user value
---

# Product, Business, and Domain Engineering

## Process
1. Identify users, jobs-to-be-done, pains, alternatives, buyer, operator, administrator, and affected stakeholders.
2. Define the value proposition, primary workflow, non-goals, assumptions, constraints, and measurable outcomes.
3. Build a domain glossary and model entities, states, invariants, permissions, events, and lifecycle transitions.
4. Write prioritized capabilities and acceptance criteria using observable behavior.
5. Define activation, retention, conversion, reliability, and operational metrics.
6. Model plans, entitlements, trials, billing events, limits, onboarding, notifications, analytics, and support needs when relevant.
7. For regulated or specialized products, record domain-specific terminology, record-retention rules, audit requirements, and human approval points.
8. Separate prototype, MVP, and production scope explicitly.

## Industry Template Checklist
Evaluate whether the product needs known patterns from CRM, marketplace, LMS, healthcare, legal, finance, inventory, real estate, construction, manufacturing, or professional services. Reuse domain conventions only after confirming they match the product.

## Red Flags
- Features without a user or business outcome.
- Generic CRUD presented as a domain model.
- Undefined state transitions or permissions.
- Success measured only by shipping.
- Pricing or entitlements added after architecture is fixed.

## Verification Requirements
- Every prioritized capability has an owner, user, outcome, and acceptance test.
- Domain states reject invalid transitions.
- Metrics can be collected by the proposed architecture.
- Prototype and production claims are not conflated.

## Exit Criteria
The approved specification contains product outcomes, domain language, user journeys, business rules, prioritized scope, metrics, and explicit assumptions.
