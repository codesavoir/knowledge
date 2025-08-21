# Testing Strategy

> Balanced test portfolio for speed and confidence.

## Test Pyramid (Adapted)
| Layer | Scope | Frequency | Tooling |
|-------|-------|-----------|---------|
| Static | Lint, type, security scan | Every commit | flake8, mypy, bandit |
| Unit | Pure funcs/classes | Every commit | pytest, junit |
| Component | Service boundaries (in-proc deps mocked) | PR | pytest + testcontainers |
| Integration | Real external deps (DB, MQ) | PR / nightly | docker compose, testcontainers |
| Contract | Consumer/provider APIs | PR / schedule | pact |
| E2E | Critical journeys | Merge / schedule | Playwright, Cypress |
| Performance | SLIs, regressions | Scheduled / pre-release | k6, Locust |
| Chaos | Failure injection | Scheduled | chaos-mesh, gremlin |

## Shift Left Security
- SAST, SCA integrated early
- Secret scanning pre-merge
- Dependency diff alerts

## Flakiness Management
- Quarantine tag + dashboard
- Auto-rerun threshold (1x) then fail hard
- Track MTTR for flaky test fixes

## Coverage
- Focus on diff coverage (changed lines)
- Threshold by layer (unit >80%, integration >60%)
- Avoid vanity 100%

## Data Management
- Synthetic deterministic seeds
- Ephemeral DB containers per test set
- Masked prod-like fixtures for realism

## Performance Guardrails
- PR budgets (e.g., p95 latency +5% max)
- k6 tests in canary environment

---
**Next:** Artifact lifecycle → [Artifact Management](artifacts.md)
