# Day 3 — Governance, Multi-Tenancy & Resilience

This diagram shows how governance and resilience are enforced across the platform.

```mermaid
flowchart TB

A[Platform Team] --> B[GitOps Repository]
B --> C[Argo CD]

C --> D[Workload Cluster]

D --> E[Namespace per Team]
E --> F[ResourceQuota / LimitRange]
E --> G[RBAC Least Privilege]

D --> H[Kyverno Policies]
H --> I[Block non-compliant workloads]

D --> J[Observability]
D --> K[Velero Backup]

K --> L[Restore Workflow]
L --> M[Recovery Validation]

J --> M