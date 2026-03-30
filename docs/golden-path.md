# Golden Path — Service Delivery

## Flow

1. Developer creates service using template
2. Code pushed via PR
3. CI pipeline validates:
   - Kubernetes manifests (kubeconform)
   - Security scan (Trivy)
   - SBOM generation (Syft)
4. Merge to main triggers GitOps sync
5. Argo CD deploys to cluster
6. Kyverno enforces policies
7. Service becomes observable (metrics/logs)

## Principles

- Shift-left security
- Policy-as-code enforcement
- Git as single source of truth
- Automated validation gates