# Logging Architecture

> Structured, centralized, queryable logs.

## Principles
- Structured (JSON) logging
- Correlate with trace IDs
- Consistent schema

## Pipeline
App → Collector/Sidecar → Aggregator → Storage → Query/Alerts

## Retention Tiers
| Tier | Duration | Purpose |
|------|----------|---------|
| Hot | 7-14d | Incident response |
| Warm | 30-90d | Trend analysis |
| Cold | 180d+ | Compliance |

## Noise Reduction
- Drop debug in prod (dynamic level control)
- Sampling high-volume health checks

---
**Next:** Metrics & SLIs/SLOs → [Metrics & SLIs/SLOs](metrics-sli-slo.md)
