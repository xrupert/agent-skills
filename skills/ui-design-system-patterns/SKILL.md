---
name: ui-design-system-patterns
description: Designs coherent accessible product interfaces from reusable interaction and visual patterns. Use during PLAN and BUILD for user-facing applications.
stage: build
command: /build
category: design
inputs:
  - user journeys
  - brand and accessibility constraints
outputs:
  - design tokens
  - page and component patterns
  - responsive and accessibility rules
quality_checks:
  - WCAG AA behavior is specified
  - repeated interactions share components
  - loading empty error and permission states exist
---

# UI and Design System Patterns

## Process
1. Map core journeys and information hierarchy before selecting components.
2. Choose proven patterns for dashboards, navigation, CRUD, tables, search, filters, forms, onboarding, settings, billing, Kanban, calendars, messaging, admin, and analytics.
3. Define tokens for typography, spacing, radii, elevation, color roles, motion, breakpoints, density, and focus states.
4. Specify component contracts, variants, composition rules, and ownership of server/client state.
5. Design loading, skeleton, empty, partial, error, offline, unauthorized, destructive, and success states.
6. Verify keyboard navigation, semantic structure, labels, contrast, focus order, reduced motion, and screen-reader announcements.
7. Prefer progressive disclosure and task-oriented screens over feature-dense dashboards.
8. Reuse the design system; do not create isolated visual languages per page.

## Red Flags
- Components chosen before journeys are understood.
- Color used as the only status signal.
- Tables on small screens without an adaptation strategy.
- Form validation that appears only after submission.
- Decorative abstraction that hides simple HTML semantics.

## Verification Requirements
- Critical flows are usable with keyboard only.
- All states have explicit designs.
- Tokens replace arbitrary repeated values.
- Components have accessible names and predictable behavior.
- Responsive checks cover phone, tablet, and desktop widths.

## Exit Criteria
The blueprint and generated repository share one documented design language with accessible reusable patterns and complete interaction states.
