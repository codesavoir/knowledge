# Observability Pillars

> Metrics, logs, traces as complementary signals.

## Signals
| Signal | Strength | Gap |
|--------|----------|-----|
| Metrics | Fast, aggregate | Low cardinality detail |
| Logs | Context-rich | Volume, noise |
| Traces | Causal path | Sampling bias |

## Cardinality Management
- Pre-aggregate where possible
- Bound label explosion (top N patterns)
- Redaction & PII scrubbing early

## Service Level Indicators
- Request success rate
- Latency percentiles (p50/p95/p99)
- Saturation metrics (CPU, memory, queue depth)

---
**Next:** Logging architecture → [Logging Architecture](logging.md)
