# CI/CD Overview

> Strategy and principles for continuous integration and continuous delivery.

## Goals
- Fast feedback
- Deterministic, reproducible builds
- Shift-left security & quality
- Progressive, low-risk delivery

## Pillars
1. Source hygiene (branching, commit standards)
2. Build determinism (pin deps, SBOM)
3. Test strategy (pyramid + quality gates)
4. Security & compliance (SAST, SCA, secrets scan, policy)
5. Artifact management (immutability, provenance)
6. Deployment automation (idempotent, reversible)
7. Observability & verification (metrics, logs, traces, checks)

## Lifecycle Flow
```
Commit -> Pre-merge CI -> Merge -> Build & Scan -> Test Stages -> Package & Sign -> Deploy (Progressive) -> Verify -> Observe -> Learn
```

## Quality Gates
| Stage | Gate Examples |
|-------|---------------|
| Pre-merge | Lint, unit tests, license scan |
| Build | Reproducibility, SBOM generated |
| Test | Coverage threshold, integration suite |
| Security | SAST clean, critical vulns < threshold |
| Deploy | Error budget OK, health probes green |

## Key Metrics
- Lead time for change
- Change failure rate
- Pipeline duration / critical path
- Failed builds per 100 commits
- Mean time to rollback

## Patterns
- Trunk-based development + short-lived feature branches
- Pipeline as code
- Reusable workflow templates / composite actions
- Dynamic pipeline (only run impacted tests)
- Caching (deps, layers, test results)

## Anti-Patterns
- Monolithic pipeline file (no reuse)
- Manual promotion steps
- Hidden / tribal knowledge build scripts
- Flaky tests tolerated

---
**Next:** Explore implementation patterns → [GitHub Actions Patterns](github-actions-patterns.md)
