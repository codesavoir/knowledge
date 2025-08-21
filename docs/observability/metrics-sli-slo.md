# Metrics, SLIs & SLOs

Intro to metrics taxonomy: counters, gauges, histograms, summaries.

## Core Concepts
- Service Level Indicator (SLI): quantitative measure of service performance.
- Service Level Objective (SLO): agreed target / threshold for an SLI.
- Error Budget: 1 - SLO (room for innovation vs reliability).

## Designing SLIs
| Layer | Example SLI | Notes |
|-------|-------------|-------|
| User | Request success rate | Perceived correctness |
| Availability | 99.9% 2xx/3xx | Exclude client aborts |
| Latency | p95 < 250ms | Separate read vs write |
| Saturation | CPU < 70% | Headroom for bursts |

## SLO Best Practices
- Align to user journey.
- Use realistic burn rates.
- Start conservative; iterate.
- Automate alerting based on error budget burn (multi-window multi-burn).

## Tooling Patterns
- Prometheus recording rules.
- RED (Rate, Errors, Duration) & USE (Utilization, Saturation, Errors) methods.

## Next Steps
Add concrete PromQL examples.

> TODO: Add error budget policy template.
