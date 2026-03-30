flowchart LR

A[Developer] --> B[Pull Request]
B --> C[CI Validation]

C --> D[kubeconform]
C --> E[Trivy Scan]
C --> F[SBOM Generation]

D --> G[Merge to main]
E --> G
F --> G

G --> H[GitOps Repository]
H --> I[Argo CD Sync]
I --> J[Kubernetes Cluster]

J --> K[Kyverno Policy Enforcement]
J --> L[Observability]