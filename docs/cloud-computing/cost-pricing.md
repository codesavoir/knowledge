---
# Cost & Pricing (FinOps Foundations)

tags: [Cloud, FinOps]
---

## 1. Pricing Primitives
| Resource | Typical Metric | Levers |
|----------|----------------|--------|
| Compute | vCPU hours, memory GB-hr | Instance family, purchase option |
| Storage | GB-month, requests | Class, lifecycle policy |
| Data Transfer | GB egress | Architecture locality, caching |
| Managed Services | API calls, capacity units | Right-sizing tier |
| Serverless | Invocations, duration, memory | Code efficiency, concurrency |

## 2. Cost Awareness Design
Shift-left cost by incorporating architecture reviews (scalability floor/ceiling, data retention). Use tags for allocation early.

## 3. Purchase & Commitment Options
| Option | Benefit | Risk |
|--------|---------|------|
| On-Demand | Flexibility | Highest unit cost |
| Reserved / Savings Plans | Lower rate | Underutilization waste |
| Spot / Preemptible | Deep discount | Interruption handling needed |

## 4. Optimization Techniques
- Right-size instances using utilization histograms.
- Schedule non-prod off-hours shutdown.
- Implement lifecycle tiers (hot → warm → archive).
- Use compression & object versioning lifecycle expiry.
- Optimize data transfer (edge caching, keep traffic intra-region).

## 5. Metrics & KPIs
| KPI | Meaning | Target Idea |
|-----|--------|-------------|
| Cost per user / feature | Unit economics | Trending downward QoQ |
| % Tagged Spend | Allocated / total | > 90% |
| Idle Resource % | Unused provisioned cost | < 5% |
| Reserved Coverage | Portion covered by commitments | 60–80% steady workloads |
| Waste Rate | Reclaimable vs total | Declining |

## 6. FinOps Operating Cycle
Inform → Optimize → Operate (data visibility → decision & action → continuous governance).

## 7. Anti‑Patterns
| Anti‑Pattern | Impact | Remedy |
|-------------|--------|--------|
| All on-demand usage | High sustained cost | Commit baseline via reservations |
| No tagging standard | Unallocated spend, disputes | Enforce tag policy in CI |
| Over-provision for peak | Waste | Autoscaling + buffer |
| Aggressive rightsizing w/o performance test | Instability | Load test before change |

## 8. Checklist
- Unified tagging schema enforced?
- Idle assets report automated?
- Commitment coverage dashboard?
- Data lifecycle policies applied?
- Egress cost reviewed monthly?

## 9. Next
Review [Case Studies](case-studies.md) or back to [Security Basics](security-basics.md).
