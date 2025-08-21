# Playbook: Pod CrashLoopBackOff

## Detection
- Alert: Restart rate > threshold.

## Triage
- Describe pod / view events.
- Inspect logs of previous container.
- Check readiness / liveness probes.

## Mitigation
- Fix misconfiguration (env vars, secrets).
- Increase resource limits if OOMKilled.
- Handle dependency timeouts / backoff.

## Prevention
- Add startup probes.
- Defensive coding (retry with jitter).

> TODO: Add kubectl command examples.
