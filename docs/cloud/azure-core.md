# Azure Core Services

> Primary Azure offerings for platform & DevOps engineering.

## Identity
- Azure AD (Entra ID) tenant governance
- Conditional access & PIM (Privileged Identity Management)
- RBAC + Azure Policy for guardrails

## Networking
- Hub-spoke virtual network topology
- Azure Firewall / Firewall Policy
- Private Link + Service Endpoints
- Front Door vs Application Gateway decision

## Compute
| Need | Service |
|------|---------|
| General compute | Virtual Machine Scale Sets |
| Containers | AKS |
| Serverless | Azure Functions |
| Low-code jobs | Logic Apps |
| Batch / HPC | Batch |

## Storage & Data
| Type | Service | Scenario |
|------|---------|----------|
| Object | Blob Storage | General purpose |
| Files | Azure Files | Lift-n-shift, SMB |
| Structured | Azure SQL / PostgreSQL Flexible | Managed relational |
| NoSQL | Cosmos DB | Global distribution |
| Messaging | Service Bus / Event Hubs | Asynchronous integration |
| Data Lake | ADLS Gen2 | Analytics & ML |

## Observability
- Azure Monitor + Log Analytics workspace
- Application Insights distributed tracing
- DCR (Data Collection Rules) central management

## Security
- Defender for Cloud posture management
- Key Vault (certs, secrets, keys) + RBAC
- Managed Identities (eliminate embedded creds)

## Cost
- Advisor recommendations monthly review
- Reservations & Savings Plans
- Storage tiering (hot/cool/archive)

---
**Next:** Cost optimization approaches → [Cost Optimization](cost-optimization.md)
