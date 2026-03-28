# AI Workload Lifecycle

## Purpose

Describe how an AI inference service moves from development to production inside the platform.

## Lifecycle stages

### 1. Build
- package inference service
- define dependencies
- expose health and metrics endpoints

### 2. Validate
- lint and validate manifests
- ensure image tag immutability
- confirm configuration completeness

### 3. Promote
- move from `dev` to `staging` to `prod` through Git changes
- preserve overlay consistency

### 4. Operate
- observe latency, errors, resource usage
- scale based on metrics
- document rollback and restore approach

## Day 1 baseline requirements

An onboarded AI service should include:
- Deployment
- Service
- ConfigMap where useful
- readiness and liveness probes
- Prometheus metrics endpoint
- resource requests and limits
- Kustomize overlays

## Future platform evolution

Day 2 and Day 3 can add:
- HPA policies
- SBOM and image attestations
- vector database integration patterns
- backup and restore procedures
- advanced alerting and SLOs
