# Playbook: Latency Spikes

## Detection
- p95 latency breach of SLO window.

## Triage
- Segment by endpoint / dependency.
- Check saturation (CPU, memory, IO, GC).
- Review recent deploys & feature flags.

## Mitigation
- Rollback high impact deploy.
- Increase replicas / provisioned capacity.
- Enable caching / circuit breaker.

## Analysis
- Flamegraphs & tracing for hotspot.

> TODO: Add PromQL query examples.
