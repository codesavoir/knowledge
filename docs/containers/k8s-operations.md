# K8s Operations

> Day-2 reliability & governance practices.

## Core Disciplines
- Capacity management & autoscaling
- Release & rollout strategies
- Security posture & multi-tenancy
- Disaster recovery readiness

## Health & Probes
- Liveness: restart hung pods
- Readiness: gating traffic
- Startup: long init containers

## Deployments
- Rolling update (default)
- Blue/Green (two services)
- Canary (progressive + metrics)

## Scaling
| Type | Mechanism |
|------|----------|
| Horizontal | HPA (metrics / custom) |
| Vertical | VPA (recommendation / update) |
| Cluster | Cluster Autoscaler |

## Observability
- Metrics: kube-state-metrics, cAdvisor
- Logging: sidecar vs node collector
- Tracing: OTel collector DaemonSet

## Reliability
- Pod disruption budgets
- Priority classes
- Multi-AZ node pools

## Security
- Namespace isolation + NetworkPolicies
- Image policy admission
- Secrets encryption at rest

---
**Next:** Service mesh rationale → [Service Mesh](service-mesh.md)
