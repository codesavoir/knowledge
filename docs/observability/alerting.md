# Dashboards & Alerting

Design alerts that are actionable and low-noise.

## Principles
- Symptom not cause.
- User impact focused.
- Include runbook link.
- Page only for urgent human action.

## Alert Taxonomy
| Type | Purpose | Example |
|------|---------|---------|
| Availability | Detect outage | 5m error budget burn > 2% |
| Latency | Degradation | p95 latency > 300ms for 10m |
| Saturation | Capacity risk | Queue depth > 80% |
| Security | Threat | Unusual auth failures |

## Multi-Window Multi-Burn (MWMB)
Use short + long windows to reduce noise but stay fast.

## Anti-Patterns
- CPU > 70% generic pages.
- Alert storms (lack aggregation).

> TODO: Add Prometheus alert examples.
