---
name: graph-engineering
description: Models and analyzes dependencies, workflows, provenance, knowledge, permissions, and blast radius as graphs. Use during PLAN, BUILD, REVIEW, and agent orchestration.
stage: plan
command: /plan
category: agent-systems
inputs:
  - entities relationships and questions
  - repository or workflow structure
outputs:
  - typed graph model
  - graph queries and invariants
  - impact and traversal strategy
quality_checks:
  - nodes and edges have explicit semantics
  - traversal is bounded and authorized
  - graph results are validated against source truth
---

# Graph Engineering

## Process
1. Define the question the graph must answer before choosing a graph technology.
2. Specify node types, edge types, direction, identity, ownership, temporal meaning, confidence, provenance, and lifecycle.
3. Decide whether the graph is authoritative, derived, cached, or analytical; define synchronization and reconciliation.
4. Model repository dependencies, agent-skill assignments, lifecycle flows, data lineage, permissions, knowledge citations, incidents, or service topology as separate typed subgraphs when semantics differ.
5. Define bounded traversals, cycle rules, depth limits, filters, authorization checks, and cost controls.
6. Add algorithms only when justified: reachability, topological order, strongly connected components, shortest path, centrality, community detection, or dependency impact.
7. Preserve source locations and evidence on graph elements so results remain explainable.
8. Use graph-derived blast radius to target reviews and tests, but confirm high-risk conclusions against code and runtime evidence.
9. Version graph schemas and support rebuilds from source data.

## Factory Applications
- Agent-to-skill-to-deliverable assignment graph.
- Requirement-to-blueprint-to-file-to-test traceability graph.
- Module dependency and change blast-radius graph.
- Workflow state and handoff graph.
- Knowledge provenance and citation graph.
- Permission and tenant-access graph.

## Red Flags
- Untyped generic edges such as “related_to.”
- Unbounded recursive queries.
- Graph data treated as current without reconciliation.
- Centrality scores treated as architectural truth.
- Sensitive relationships traversed without authorization.

## Verification Requirements
- Graph invariants reject orphaned, contradictory, or invalid relationships.
- Traversal tests cover cycles, depth limits, authorization, and stale nodes.
- Sample graph answers match manually verified source cases.
- Rebuild and reconciliation are deterministic.

## Exit Criteria
The graph has explicit semantics, provenance, bounded queries, tested invariants, and a documented role in decision-making rather than decorative visualization.
