# Playbook: High CPU

## Detection
- Alert: CPU > 90% for 5m across 3+ pods.

## Triage Steps
1. Identify impact (latency, errors?).
2. Top processes / threads.
3. Recent deploys or traffic spikes?

## Mitigation
- Scale out replica count.
- Optimize hot path (cache, reduce log verbosity).
- Rollback recent change if correlated.

## Post-Incident
- Add autoscaling tuning action items.

> TODO: Provide kubectl and top commands snippet.
