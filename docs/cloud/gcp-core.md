# GCP Core Services

> Key GCP primitives for building resilient platforms.

## Identity
- Cloud Identity + IAM Conditions
- Org policies to enforce constraints (e.g., CMEK)

## Networking
- Global VPC architecture
- Cloud Load Balancing (global anycast) advantages
- Private Service Connect

## Compute
| Need | Service |
|------|---------|
| Containers | GKE Autopilot / Standard |
| Serverless APIs | Cloud Run |
| Event processing | Cloud Functions / Dataflow |
| Batch | Batch / Dataproc |

## Storage & Data
| Type | Service | Notes |
|------|---------|------|
| Object | Cloud Storage | Uniform access, lifecycle |
| Relational | Cloud SQL / AlloyDB | High availability |
| NoSQL | Firestore / Bigtable | Access pattern driven |
| Analytics | BigQuery | Columnar, partition & cluster |

## Observability
- Cloud Logging + Log Sinks to BigQuery
- Cloud Monitoring (SLOs + alerting)
- Cloud Trace + Profiler

## Security
- SCC (Security Command Center)
- VPC SC for data exfiltration control
- KMS / CMEK integration
- Binary Authorization for images

## Cost
- Committed use discounts
- BigQuery slot reservations
- Object storage lifecycle

---
**Next:** Azure building blocks → [Azure Core Services](azure-core.md)
