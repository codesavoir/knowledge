# Multi-Cloud Strategy

> Intentional approach, not accidental sprawl.

## Drivers
| Legitimate | Weak |
|------------|------|
| Avoid lock-in for critical workload | "Discounts everywhere" |
| Leverage best-of-breed managed service | Uncoordinated team choices |
| Regulatory / data residency | Fear-based decisions |
| Resilience against provider outage | Resume-driven duplication |

## Strategy Pillars
1. Clear workload placement policy
2. Abstraction where it adds net value (not everywhere)
3. Central platform capabilities (identity, observability, IaC)
4. Cost & performance feedback loops

## Control Plane Choices
| Layer | Pattern |
|-------|---------|
| Identity | Central IdP + OIDC federation |
| Network | SD-WAN / Cloud WAN + consistent CIDR mgmt |
| Secrets | Unified vault with cloud KMS roots |
| Policy | OPA/Gatekeeper / Cloud org policy |
| Observability | Aggregated metrics & traces (OTel) |

## Data Gravity Considerations
- Minimize cross-cloud chatty latency paths
- Replicate asynchronously unless strict RPO needs
- Keep analytics & ML near data lake

## Exit Cost Analysis Template
| Service | Replacement Path | Data Egress Risk | Effort |
|---------|------------------|------------------|--------|
| Managed DB | Self-host / alt managed | High | High |
| Functions | CNCF serverless (Knative) | Low | Medium |

## KPIs
- Cross-cloud network spend % of total
- Duplicate service count (target downward)
- Mean onboarding time new environment

---
**Next:** AWS core building blocks → [AWS Core Services](aws-core.md)
