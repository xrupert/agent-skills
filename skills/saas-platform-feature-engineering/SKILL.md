---
name: saas-platform-feature-engineering
description: Implements reusable SaaS platform capabilities with correct tenancy, authorization, and lifecycle behavior. Use during PLAN and BUILD for SaaS products.
stage: build
command: /build
category: platform
inputs:
  - product requirements
  - tenancy and billing model
outputs:
  - platform capability plan
  - reusable service boundaries
  - integration tests
quality_checks:
  - authorization is server enforced
  - tenant data isolation is tested
  - lifecycle and failure states are covered
---

# SaaS Platform Feature Engineering

## Capabilities
Evaluate and implement only those required: authentication, organizations, workspaces, teams, roles, permissions, invitations, profiles, audit logs, notifications, email, subscriptions, entitlements, trials, feature flags, search, uploads, comments, activity feeds, webhooks, API keys, analytics, and administration.

## Process
1. Define tenant, user, membership, role, permission, plan, entitlement, and resource relationships.
2. Establish server-side authorization and database isolation before UI affordances.
3. Model invitation, suspension, deletion, transfer, cancellation, retry, and recovery states.
4. Separate provider adapters from domain policy for email, payments, files, search, and analytics.
5. Make webhook processing idempotent, authenticated, replay-safe, and observable.
6. Use explicit usage limits and entitlement checks; never infer access from UI state.
7. Build reusable modules with narrow contracts rather than copying feature implementations.
8. Add audit evidence for sensitive state changes.

## Red Flags
- `organization_id` accepted from the client without membership verification.
- Role names hard-coded across UI and server code.
- Payment status treated as authorization truth without entitlement policy.
- Webhooks without idempotency keys or signature verification.
- Hard deletion where retention or audit requirements apply.

## Verification Requirements
- Cross-tenant access tests fail closed.
- Permission matrices have table-driven tests.
- Provider failures and retries are covered.
- Billing and entitlement transitions are deterministic.
- Sensitive actions emit audit events.

## Exit Criteria
Required SaaS capabilities are implemented as secure, tested modules with explicit tenancy, authorization, provider boundaries, and lifecycle rules.
