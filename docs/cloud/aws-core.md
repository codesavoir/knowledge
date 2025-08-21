# AWS Core Services

> Foundational AWS components for platform engineering.

## Identity & Access
- Organizations with SCP guardrails
- IAM Access Analyzer, least privilege policies
- SSO + Attribute-based access control (ABAC)

## Networking
- Multi-account VPC architecture
- Centralized egress (NAT Gateway cost awareness)
- PrivateLink for internal services
- VPC Lattice / App Mesh for service connectivity (evaluate)

## Compute
| Need | Service |
|------|---------|
| General workloads | EC2 ASG / EKS |
| Containers | ECS Fargate / EKS |
| Serverless events | Lambda |
| Batch / ML | Batch / SageMaker |

## Storage
| Type | Service | Use |
|------|---------|-----|
| Object | S3 + lifecycle policies | Data lake, artifacts |
| Block | EBS gp3 | Stateful workloads |
| File | EFS / FSx | Shared POSIX |
| Managed DB | RDS / Aurora | Relational |
| NoSQL | DynamoDB | Key-value / high scale |

## Observability
- CloudWatch metrics + embedded metric format
- X-Ray or OTel collector for tracing
- Structured logging to CloudWatch Logs → central sink

## Security
- GuardDuty, Security Hub, Config
- KMS CMKs for encryption (S3, EBS, RDS)
- WAF + Shield for edge protection

## Cost Levers
- Right-size instances (Compute Optimizer)
- Savings Plans vs Reserved Instances
- S3 intelligent-tiering + lifecycle

---
**Next:** GCP fundamentals → [GCP Core Services](gcp-core.md)
