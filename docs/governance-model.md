# Governance Model

## Objective

Establish safe onboarding boundaries for AI and application teams without sacrificing delivery speed.

## Governance controls

### 1. Namespace ownership
Each team receives one or more namespaces with approved quotas, labels, and access policies.

### 2. RBAC least privilege
Application teams should not receive cluster-admin style permissions. Access must be scoped to team namespaces and required operations only.

### 3. Resource governance
Requests, limits, quotas, and default policies reduce noisy-neighbor risk and force explicit sizing decisions.

### 4. Deployment guardrails
Policies should eventually enforce:
- no `:latest` tags
- required resource requests/limits
- mandatory labels
- approved registries
- non-root containers where applicable

### 5. Promotion discipline
All environment changes should move through Git pull requests and CI checks rather than direct kubectl mutations.

## Team model

### Platform Team
Owns:
- Argo CD
- cluster bootstrap
- platform add-ons
- policy pack
- tenant standards

### Product / ML Team
Owns:
- application code
- service manifests within approved templates
- environment-specific config
- operational runbooks for owned services

## Success criteria

A new service can be onboarded using approved templates, deployed through GitOps, and operated without violating baseline platform controls.
