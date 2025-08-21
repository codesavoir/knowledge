# Cost Optimization

> Engineering discipline to sustain efficiency.

## Principles
- Cost is a feature (observable & owned)
- FinOps partnership (visibility → optimization → governance)
- Optimize after measuring (avoid premature spend cuts)

## Feedback Loop
1. Collect (CUR, billing exports, usage metrics)
2. Allocate (tagging, account hierarchy, chargeback/showback)
3. Analyze (unit economics: cost per request/user)
4. Optimize (rightsizing, reservations, waste elimination)
5. Govern (budgets, alerts, policy enforcement)

## Quick Wins
| Domain | Action |
|--------|--------|
| Compute | Rightsize + autoscale |
| Storage | Lifecycle + compression + infrequent tiers |
| Network | Reduce cross-region chatter |
| Databases | Turn off idle / serverless tier |
| CI/CD | Cache dependencies, prune old artifacts |

## Metrics
- Cost per customer / request
- % Idle spend
- Reservation coverage & utilization
- Waste recovered (monthly)

## Tooling
- Native: AWS Cost Explorer, GCP Billing, Azure Cost Management
- Open: OpenCost / Kubecost, Infracost, Cloud Custodian

## Governance
- Tag compliance score
- Budget alerts (threshold ladder 50/75/90/100%)
- Policy: prohibit unapproved instance types

---
**Next:** Containers introduction → [Docker Fundamentals](../containers/docker-fundamentals.md)
