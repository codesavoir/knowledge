# Service Mesh (Istio / Linkerd)

> Traffic management, security, and observability layer.

## Core Capabilities
| Domain | Features |
|--------|----------|
| Traffic | Routing, retries, deadlines, circuit breaking |
| Security | mTLS, authz policies, cert rotation |
| Observability | Metrics, distributed tracing, access logs |
| Resilience | Fault injection, outlier detection |

## Deployment Models
- Sidecar injector (per-pod proxies)
- Ambient / Sidecar-less (emerging)

## Use Cases
- Gradual rollout (header & weight-based)
- Zero-trust east-west encryption
- Policy enforcement (RBAC, rate limit)

## Overhead Considerations
- Added latency per hop
- Operational complexity (control plane)

## When NOT to Use
- Simple monolith or low traffic
- Single service without security mandates

---
**Next:** Shift to Infrastructure as Code → [IaC Strategy](../iac/strategy.md)
