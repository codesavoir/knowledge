# IaC Strategy

> Declarative, testable, governed infrastructure delivery.

## Principles
- Single source of truth (Git)
- Idempotent & immutable provisioning
- Review + test before apply
- Drift detection & reconciliation

## Tool Selection
| Layer | Example |
|------|---------|
| Provision | Terraform, Pulumi |
| Config | Ansible, Chef |
| Platform | Crossplane, AWS CDK |
| Policy | OPA, Sentinel |

## Environments
- Promote via Git (dev → stage → prod)
- Reuse modules; no copy/paste
- Parameterize via variables & workspaces

## State Management
- Remote backend (S3+Dynamo, GCS, Azure Storage)
- State locking to prevent corruption
- Encryption at rest

## Review Checklist
- Resource naming standards
- Tags / labels applied
- Least privilege IAM
- Sensitive outputs suppressed

---
**Next:** Terraform design patterns → [Terraform Patterns](terraform-patterns.md)
