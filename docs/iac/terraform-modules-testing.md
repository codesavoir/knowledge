# Terraform Modules & Testing

> Ensuring reliability of infrastructure code.

## Quality Gates
- Format, validate, lint
- Static security scan (tfsec)
- Policy checks (OPA/Sentinel)

## Test Types
| Type | Tool | Goal |
|------|------|-----|
| Unit (logic) | terraform-config-inspect | Structure |
| Plan assertion | infracost + custom scripts | Expected changes |
| Integration | Terratest | Provision & verify |
| Policy | Conftest | Compliance |

## Terratest Skeleton (Go)
```go
package test
import (
  "testing"
  "github.com/gruntwork-io/terratest/modules/terraform"
)
func TestModule(t *testing.T) {
  tf := terraform.Options{ TerraformDir: "../examples/simple" }
  defer terraform.Destroy(t, &tf)
  terraform.InitAndApply(t, &tf)
}
```

## Module Publishing
- CHANGELOG + version tags
- Example usage folders
- Semantic version bump on interface change

---
**Next:** Policy as Code concepts → [Policy as Code (OPA)](policy-as-code.md)
