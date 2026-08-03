---
name: devops-observability-and-operational-engineering
description: Designs deployment, infrastructure, observability, incident response, rollback, and operating playbooks. Use during PLAN, BUILD, VERIFY, and SHIP.
stage: ship
command: /ship
category: operations
inputs:
  - architecture and deployment target
  - reliability requirements
outputs:
  - delivery pipeline
  - observability plan
  - runbooks and rollback plan
quality_checks:
  - deployment is repeatable
  - health and failure signals are actionable
  - rollback or roll-forward is rehearsed
---

# DevOps, Observability, and Operational Engineering

## Process
1. Define environments, ownership, secrets, configuration, infrastructure, data dependencies, and release responsibilities.
2. Build reproducible CI/CD with pinned runtimes, clean installs, typecheck, tests, lint, build, security checks, and deployment gates.
3. Choose hosting and infrastructure from workload needs; document Vercel, Cloudflare, containers, managed platforms, or cloud resources explicitly.
4. Add structured logs, traces, metrics, health checks, synthetic checks, release markers, and correlation IDs.
5. Define service-level indicators and objectives for availability, latency, correctness, and freshness.
6. Design staged rollout, feature flags, database sequencing, rollback, roll-forward, and disaster recovery.
7. Create runbooks for provider failure, data corruption, elevated errors, latency, auth failure, exhausted quotas, and dependency outages.
8. Conduct a production-readiness review and capture operational ownership.

## Red Flags
- Deployments require undocumented manual steps.
- Logs contain secrets or cannot correlate a request.
- Alerts fire without a clear operator action.
- Database changes cannot be rolled forward safely.
- No restore test, incident process, or ownership.

## Verification Requirements
- A clean environment can build and deploy from documented commands.
- Alerts and dashboards are exercised with test signals.
- Rollback or roll-forward is demonstrated.
- Secrets are externalized and scoped.
- Runbooks identify detection, containment, recovery, and follow-up.

## Exit Criteria
The project is deployable, observable, recoverable, and operable by someone other than its original author.
