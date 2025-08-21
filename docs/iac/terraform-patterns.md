# Terraform Patterns

> Scalable design approaches.

## Module Composition
- Small focused modules (network, compute, db)
- Layer composition via root modules
- Avoid deep module nesting

## Versioning
- Pin provider & module versions
- Semantic version for shared modules

## Workspaces vs Directories
| Aspect | Workspaces | Dirs |
|--------|-----------|------|
| Drift Isolation | Lower | Higher |
| State Blast Radius | Larger | Smaller |
| Simplicity | Higher | Lower |

## Testing
- `terraform validate` & `tflint`
- `terraform plan -out plan.bin` in CI
- Infracost for cost diffs

## Performance
- Parallelism tuning
- Targeted applies only when needed (avoid drift)

---
**Next:** Module testing & quality → [Terraform Modules & Testing](terraform-modules-testing.md)
