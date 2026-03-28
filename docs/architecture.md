# Architecture Overview

## Goal

Design a secure, production-minded **Enterprise AI Platform** that separates platform concerns from workload concerns while enabling repeatable onboarding of AI services across multiple Kubernetes clusters.

## Core design principles

1. **Centralized control, decentralized workloads**
   - A management cluster hosts the GitOps control plane.
   - Workloads are deployed into regional clusters.

2. **Everything reconciled from Git**
   - Platform add-ons and application workloads are reconciled declaratively.

3. **Clear governance boundaries**
   - Platform team owns cluster-wide controls.
   - Product/ML teams own approved namespaces and application manifests.

4. **Policy-first evolution**
   - Security, resource controls, and deployment rules are expressed as code.

5. **AI readiness from Day 1**
   - Sample service structure supports inference APIs, metrics, probes, and staged promotion.

## Logical topology

- **Management Cluster**
  - Argo CD
  - platform app-of-apps
  - shared platform definitions

- **EU Workload Cluster**
  - regulated or region-specific workloads
  - namespaced team isolation

- **US Workload Cluster**
  - independent workload boundary
  - identical operating model

## Control boundaries

| Concern | Owner | Location |
|---|---|---|
| GitOps control plane | Platform Team | Management cluster |
| Cluster policies | Platform Team | Workload clusters |
| Namespaces | Platform Team + Team lead approval | Workload clusters |
| App manifests | Product/ML teams | Git repo |
| Promotion across environments | GitOps + CI | Git + clusters |

## Why this matters

Many AI demos stop at inference deployment. This design focuses on the **operating model** required to run AI workloads with governance, repeatability, and platform consistency.
