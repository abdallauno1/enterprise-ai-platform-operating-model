# Operating Model

## Day 1 outcome

By the end of Day 1, the organization should have:
- a single source of truth in Git
- a management cluster pattern
- a standard application structure
- environment overlays for promotion
- a portal entry point for developer experience evolution

## Delivery path

1. Developer updates code or manifests.
2. CI validates structure and manifest quality.
3. Change merges to main.
4. Argo CD reconciles desired state.
5. Regional clusters receive approved changes.

## Responsibilities

### Platform Team workflow
- curates base templates
- manages shared policies
- maintains GitOps root applications
- evolves platform roadmap

### Application Team workflow
- builds service image
- updates values/manifests in allowed areas
- promotes changes via PRs
- relies on platform standards instead of bespoke cluster setup

## Why GitOps here

GitOps is not used only for deployment convenience. It creates:
- auditable change history
- reproducible promotion
- drift visibility
- cleaner separation of platform and workload ownership
