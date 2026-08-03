---
name: data-database-and-privacy-engineering
description: Designs durable data models, migrations, access policies, privacy controls, and operational safeguards. Use during PLAN, BUILD, and REVIEW.
stage: plan
command: /plan
category: data
inputs:
  - domain model
  - access and retention requirements
outputs:
  - schema and migration plan
  - indexing and RLS policy
  - privacy and recovery plan
quality_checks:
  - constraints enforce invariants
  - migrations are reversible or recoverable
  - sensitive data has explicit handling rules
---

# Data, Database, and Privacy Engineering

## Process
1. Translate domain entities, relationships, states, invariants, ownership, and retention into a logical model.
2. Choose storage technology from access patterns, consistency, scale, query, and operational needs—not fashion.
3. Define primary keys, foreign keys, unique constraints, checks, nullability, timestamps, versioning, and audit fields.
4. Design indexes from real query paths and verify with query plans.
5. Establish tenant isolation and row-level security where applicable; test policies with adversarial identities.
6. Plan forward-compatible migrations, backfills, validation, rollback or roll-forward, and zero-downtime sequencing.
7. Classify data, minimize collection, define encryption, redaction, deletion, export, consent, and retention behavior.
8. Specify backup, restore, point-in-time recovery, reconciliation, and data-integrity monitoring.

## Red Flags
- Application code is the only place enforcing invariants.
- Indexes added without query evidence.
- Destructive migrations without backups or staged rollout.
- Sensitive values in logs, analytics, URLs, or error messages.
- RLS policies without cross-tenant tests.

## Verification Requirements
- Migration runs against representative data and a clean database.
- Constraints reject invalid states.
- Query plans meet performance expectations.
- Backup restoration is demonstrated for production claims.
- Privacy operations are testable and auditable.

## Exit Criteria
The project has an approved schema, migration path, access model, performance plan, privacy controls, and recovery evidence appropriate to its ship mode.
