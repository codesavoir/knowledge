---
# Deployment Models (Public / Private / Hybrid / Multi‑Cloud / Edge)

tags: [Cloud, Architecture]
---

## 1. Overview
Deployment model choice determines latency envelope, control surface, compliance posture, and operational complexity.

## 2. Definitions
| Model | Core Idea | Strengths | Typical Risks |
|-------|----------|-----------|---------------|
| Public | Shared provider infrastructure | Elasticity, speed, global scale | Perceived loss of control, noisy neighbors |
| Private | Dedicated environment (on‑prem/DC or hosted) | Customization, data locality | CapEx, slower innovation cadence |
| Hybrid | Integrated public + private | Gradual migration, regulated workloads placement | Integration complexity, split tooling |
| Multi‑Cloud | Two+ public providers | Avoid concentration risk, best‑of‑breed | Skill dilution, latency, cost mgmt overhead |
| Edge | Compute near data source/user | Ultra‑low latency, bandwidth savings | Fragmented tooling, limited capacity |

## 3. Key Drivers & Mapping
| Driver | Points Toward | Rationale |
|--------|--------------|-----------|
| Strict data residency | Private / Regional Public | Control physical location |
| Rapid global expansion | Public | Provider PoP & region footprint |
| Existing DC sunk cost | Hybrid (transition) | Leverage assets while modernizing |
| Vendor lock concern | Multi‑Cloud (selective) | Negotiate leverage / resilience |
| Millisecond latency to device | Edge | Proximity reduces round trips |

## 4. Topology Patterns
- Hub & Spoke: Central shared services hub (identity, logging) with isolated spokes per workload.
- Hybrid Network Extension: Site‑to‑site VPN or dedicated circuit into cloud VPC/VNet.
- Multi‑Cloud via Service Layer: Abstraction (e.g., container platform / service mesh) standardizes deployment surface.
- Edge Fan‑Out: Central control plane orchestrates functions/containers at edge POPs.

## 5. Connectivity & Identity Considerations
| Aspect | Public | Hybrid | Multi‑Cloud |
|--------|-------|--------|------------|
| Identity Federation | IAM + SSO | Extend directory + IAM | Cross‑provider federation strategy |
| Network | Native constructs (VPC) | VPN / Direct Connect + routing | Traffic steering, anycast, mesh |
| Observability | Unified provider tools | Dual pipeline bridging | Normalization layer required |
| Security Controls | Cloud‑native + policy | Mixed toolchain | Consistency drift risk |

## 6. Cost & Complexity Curve
```
Public < Hybrid < Multi‑Cloud (increasing ops & governance complexity)
```
> Only pay the complexity tax you can staff & automate.

## 7. Anti‑Patterns
| Anti‑Pattern | Why It Hurts | Better Path |
|-------------|--------------|------------|
| Premature multi‑cloud | Doubled surface area, slow delivery | Single provider + abstract at portability seams |
| Lift & freeze hybrid | Stalls modernization benefits | Iterative re‑platform schedule with KPIs |
| DIY edge without clear latency KPI | Unproven value, wasted effort | Measure baseline latency first |

## 8. Decision Checklist
- Regulatory constraints documented? (region list)
- Latency SLO to end user defined (p50/p95)?
- Data classification informs placement?
- Exit strategy for primary provider sketched?
- Observability unified taxonomy planned?

## 9. Next
Proceed to [Key Concepts](key-concepts.md) or revisit [Service Models](service-models.md).
