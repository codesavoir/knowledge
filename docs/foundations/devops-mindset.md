# DevOps Mindset

> Building a culture of collaboration, feedback, and continuous improvement.

## Core Principles

| Principle | Description | Anti-Pattern |
|-----------|-------------|--------------|
| Flow | Shorten lead time from idea to prod | Large infrequent releases |
| Feedback | Fast, actionable signals | Ignored alerts |
| Learning | Kaizen & blameless culture | Punitive postmortems |
| Ownership | You build it, you run it | Throw over the wall |
| Automation | Codify repetitive tasks | Manual snowflake ops |

## CALMS Framework

- Culture: Psychological safety, cross-functional squads
- Automation: Pipelines as product, infra as code, policy as code
- Lean: Value stream mapping, limit WIP, remove toil
- Measurement: DORA metrics + business KPIs
- Sharing: InnerSource, playbooks, demos, mentoring

## DORA Metrics (Expand + Adapt)

| Metric | Optimize For | Levers |
|--------|--------------|--------|
| Deployment Frequency | Small, safe batch size | Trunk-based dev, feature flags |
| Lead Time | Fast idea-to-value | CI speed, test pyramid, review SLAs |
| MTTR | Rapid recovery | Runbooks, observability, chaos practice |
| Change Failure Rate | Safety with speed | Shift-left quality, progressive delivery |

## Team Topologies Alignment

| Topology | When Useful | Risks |
|----------|-------------|-------|
| Stream-aligned | Product delivery focus | Silo drift |
| Platform | Reduce cognitive load | Becoming gatekeeper |
| Enabling | Upskill & unblock | Over-consulting |
| Complicated Subsystem | Deep expertise | Knowledge isolation |

## Tactical Practices

### Shift Left Quality
- Contract tests for services
- Static analysis & SAST in PR
- Security controls as pipeline stages
- Policy as code (OPA/Rego)

### Continuous Verification
- Automated canary analysis (metrics, SLIs)
- Error budget burn alerts gating rollouts
- Synthetic + real user monitoring

### Governance as Enablement
- Golden paths / reference templates
- Scorecards (operability, reliability)
- Guardrails > gates

## Maturity Ladder

| Level | Labels | Characteristics | Focus Next |
|-------|--------|-----------------|------------|
| 1 | Ad-hoc | Manual deploys, heroics | Version control everything |
| 2 | Scripted | Basic CI, scripts | Pipeline as code, tests |
| 3 | Automated | Full CI/CD, infra as code | Observability & SLOs |
| 4 | Measured | DORA tracked, error budgets | Progressive delivery |
| 5 | Optimizing | Experimentation engine | Autonomous governance |

## Outcome Metrics
- Lead time p95 < 1 day
- Deployment frequency: daily per service
- MTTR < 30 min (critical path)
- Change fail < 10%
- Error budget policy respected

---
**Next:** Explore foundational Linux concepts → [Linux Basics](linux-basics.md)
