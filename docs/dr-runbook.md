# Disaster Recovery Runbook

## Objective

Provide a repeatable recovery workflow for platform workloads deployed through GitOps.

## Recovery Scope

- application namespaces
- configuration resources
- persistent volume backups
- deployment manifests stored in Git

## Recovery Workflow

1. Identify affected namespace or cluster scope
2. Verify latest successful backup in Velero
3. Restore namespace resources
4. Reconcile manifests from GitOps source
5. Validate application health:
   - pods running
   - services reachable
   - logs available
   - metrics restored
6. Confirm recovery against RTO/RPO targets

## Example Targets

- RTO: 30 minutes
- RPO: 15 minutes

## Validation Checklist

- Namespace restored
- Deployments healthy
- ConfigMaps and Secrets available
- Persistent data recovered
- Argo CD status healthy
- Monitoring and logging active again

## Principle

A disaster recovery process is only meaningful if it is tested.# Disaster Recovery Runbook

## Objective

Provide a repeatable recovery workflow for platform workloads deployed through GitOps.

## Recovery Scope

- application namespaces
- configuration resources
- persistent volume backups
- deployment manifests stored in Git

## Recovery Workflow

1. Identify affected namespace or cluster scope
2. Verify latest successful backup in Velero
3. Restore namespace resources
4. Reconcile manifests from GitOps source
5. Validate application health:
   - pods running
   - services reachable
   - logs available
   - metrics restored
6. Confirm recovery against RTO/RPO targets

## Example Targets

- RTO: 30 minutes
- RPO: 15 minutes

## Validation Checklist

- Namespace restored
- Deployments healthy
- ConfigMaps and Secrets available
- Persistent data recovered
- Argo CD status healthy
- Monitoring and logging active again

## Principle

A disaster recovery process is only meaningful if it is tested.