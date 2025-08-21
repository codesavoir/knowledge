# Policy as Code (OPA)

> Declarative governance via machine-enforceable rules.

## Why
- Consistency
- Auditability
- Shift-left compliance

## Components
| Element | Purpose |
|---------|---------|
| Rego | Policy language |
| Input doc | JSON/YAML to evaluate |
| Decision | Allow / deny + metadata |

## Policy Lifecycle
1. Author (Git)
2. Test (unit + integration)
3. Distribute (bundles)
4. Enforce (admission / pipeline)
5. Monitor (decision logs)

## Example Rego
```rego
package cost

deny[msg] {
  input.resource.type == "aws_instance"
  input.resource.size == "m5.4xlarge"
  msg = "Oversized instance"
}
```

## Tooling
- Conftest for CLI checks
- Gatekeeper / Kyverno for K8s
- Terraform Cloud policies

---
**Next:** Detecting drift → [Drift Detection](drift-detection.md)
