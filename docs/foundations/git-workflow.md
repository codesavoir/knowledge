# Git & Workflow

> High-velocity, low-drift source control practices.

## Principles
- Optimize for fast merge to trunk
- Small, reviewable PRs (< 400 LOC diff)
- Automate quality gates (lint, tests, security)
- Use feature flags over long-lived branches

## Branch Strategy
| Strategy | Use When | Notes |
|----------|----------|-------|
| Trunk-based | SaaS / microservices | Max flow, needs CI rigor |
| Short-lived feature branches | Most teams | PR review + automation |
| Release branches | Versioned platforms | Add cherry-pick discipline |

## Commit Hygiene
```
<type>(scope): concise change summary

Why:
Context + problem statement
How:
Key approach
Refs: JIRA-123, RFC-9
```
Types: feat, fix, refactor, docs, chore, test, perf, revert

## Review Excellence
- PR template with risk, test evidence, rollback plan
- Review SLA (e.g., < 4 business hours)
- Blocked label + async escalation channel
- Pair on complex diffs, comment on intent not style

## Automation Checklist
- Commit lint
- Conventional release notes generator
- Semantic version bump
- Mandatory status checks (tests, security scan)
- Protected main (fast-forward disabled)

## Handling Hotfixes
1. Branch from tag (production version)
2. Isolate minimal fix + tests
3. Patch release `vX.Y.(Z+1)`
4. Cherry-pick to main if diverged

## Anti-Patterns
- Stale long-running branches
- Squashing without preserving logical boundaries
- Force-push on shared branches
- Omitting CI for docs/infrastructure changes

---
**Next:** Productivity with scripting → [Scripting](scripting.md)
