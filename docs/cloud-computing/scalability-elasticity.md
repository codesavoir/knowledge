---
# Scalability & Elasticity

tags: [Cloud, Architecture]
---

## 1. Definitions
| Term | Formal Definition | Example |
|------|-------------------|---------|
| Scalability | System's ability to increase capacity by adding resources | Add more app replicas behind LB |
| Elasticity | Automatic dynamic adjustment of resources to load | Scale out to 10 pods during spike, back to 3 |

## 2. Dimensions of Scalability
- Horizontal: add more instances (preferred for resilience)
- Vertical: increase instance size (quick win, ceiling exists)
- Diagonal: temporary vertical + progressive horizontal blend

## 3. Metrics & Signals
| Signal | Use | Note |
|--------|-----|------|
| CPU / Memory utilization | Simple scaling trigger | Beware noisy metrics |
| Queue depth / lag | Work backlog scaling | Better for async processing |
| Request latency (p95) | User experience threshold | Combine with error rate |
| SLO burn rate | Early stress indicator | Proactive scaling |

## 4. Autoscaling Strategies
| Strategy | Description | Use Case |
|----------|-------------|---------|
| Threshold-based | Static metric thresholds | Stable, predictable traffic |
| Target tracking | Maintain metric target | CPU 60% stable utilization |
| Scheduled | Known time-based patterns | Marketing campaign spikes |
| Predictive | Forecast + pre‑scale | Seasonal or cyclical load |

## 5. State Handling
Stateless services scale linearly. For stateful layers, use read replicas, sharding, or partitioned queues.

## 6. Cost Alignment
Right‑size floor capacity; allow scale to zero where feasible (dev, batch). Monitor unused headroom.

## 7. Anti‑Patterns
| Anti‑Pattern | Impact | Improvement |
|-------------|--------|------------|
| Only vertical scaling | Rapid cost growth, single box risk | Design for horizontal early |
| Reactive scaling on CPU only | Slow response to surge types | Multi‑metric + queue signals |
| No scale down policy | Wasted idle spend | Implement cool‑down + min replicas |

## 8. Checklist
- Defined SLO (latency/error)?
- Chosen primary scaling signals?
- Separate scaling policies per tier (app vs worker)?
- Load test baseline throughput?

## 9. Next
Move to [Security Basics](security-basics.md) or revisit [Compute, Storage & Networking](compute-storage-networking.md).
