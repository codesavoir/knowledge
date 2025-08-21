# GitHub Actions Patterns

> Reusable, secure workflow design strategies.

## Core Principles
- Reuse via composite actions & workflow_call
- Principle of least privilege (scoped permissions)
- Caching with keys tied to inputs
- Deterministic builds (pin actions SHAs)
- Defense in depth (branch protections, OIDC tokens)

## Common Patterns
| Goal | Pattern | Notes |
|------|---------|-------|
| Matrix builds | `strategy.matrix` | Limit fan-out to control concurrency |
| Reuse | `workflow_call` | Centralize compliance steps |
| Secrets minimization | OIDC + cloud role | Avoid long-lived keys |
| Speed | Layered caching (pip/npm/docker) | Bust with hashFiles |
| Artifact integrity | Provenance / SBOM step | Attestations (cosign) |

## Directory Layout Suggestion
```
.github/
  workflows/
    build.yml
    release.yml
  actions/
    lint/
      action.yml
    security-scan/
      action.yml
```

## Security Hardening
- Pin `actions/checkout@<sha>` not only tag
- Restrict `pull_request_target` usage
- Use `permissions:` minimal (default `read-all` → explicitly set)
- Validate third-party action trust

## Observability
- Step timings (Graph view)
- Emit OpenTelemetry via wrapper (optional)

---
**Next:** Deep dive Jenkins vs GitHub Actions → [Jenkins Pipelines](jenkins.md)
