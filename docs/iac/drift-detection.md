# Drift Detection

> Identify and remediate config divergence.

## Causes
- Manual hotfixes
- Unmanaged resources
- Failed partial applies

## Detection Methods
| Method | Tool |
|--------|------|
| Terraform plan diff | terraform plan |
| Cloud inventory scan | driftctl |
| Event monitoring | CloudTrail / Activity Logs |

## Workflow
1. Scheduled scan
2. Classify (intentional / unintentional)
3. Remediate (apply or adjust code)
4. Postmortem root cause

## Automation
- GitHub Action nightly drift job
- Alerts on critical resource drift (IAM, security groups)

---
**Next:** Observability foundations → [Observability Pillars](../observability/pillars.md)
