---
# Key Concepts (Regions, Zones, Edge, Accounts)

tags: [Cloud, Key Concepts]
---

## 1. Geography & Fault Domains
| Term | Meaning | Why It Matters |
|------|--------|----------------|
| Region | Cluster of isolated Availability Zones within a geographic boundary | Latency selection, regulatory residency |
| Availability Zone (AZ) | Independent power / networking / cooling fault domain | Design for high availability across AZs |
| Edge / POP | Distributed caching / compute site | Reduce latency & egress from origin |

## 2. Blast Radius Reduction
> Spread critical tiers across ≥2 AZs to survive single AZ failure without user impact.

```
User -> Global DNS -> Region (AZ1 + AZ2) -> Load Balancer -> App Tier (multi‑AZ) -> Database (primary + replica) -> Object Storage (regional)
```

## 3. Identity & Isolation Units
| Layer | Purpose | Example Controls |
|-------|---------|------------------|
| Account / Subscription | Billing & isolation boundary | SCP / Policy, Budget alerts |
| Project / Resource Group | Lifecycle & access grouping | Role assignments, tags |
| Namespace (K8s) | Multi‑tenant segmentation | RoleBindings, NetworkPolicies |

## 4. Tagging & Metadata
| Tag Dimension | Why | Example |
|---------------|-----|--------|
| Environment | Lifecycle policies & risk segregation | env=prod | 
| Owner | Accountability | owner=platform-team |
| Cost Center | Chargeback / FinOps | cost_center=fin-ops |
| Data Sensitivity | Security controls & encryption requirements | data_class=pii |

## 5. Data Durability vs Availability
| Storage Type | Durability | Availability | Use Case |
|-------------|-----------|-------------|----------|
| Object (standard) | 11 9s | High | Static assets, backups |
| Block (premium) | High | AZ bound | Databases, low latency apps |
| File (managed) | Regional | Med | Shared content repositories |
| Archive | High (delayed) | Low | Cold logs, compliance data |

## 6. Latency Budget Awareness
Break end‑user response time into network transit, application processing, data access. Use budgets to prioritize optimization.

## 7. Capacity vs Scalability vs Elasticity
| Term | Short | Misconception |
|------|-------|--------------|
| Capacity | Max sustainable throughput | Just buy bigger servers |
| Scalability | Ability to increase capacity as needed | Only horizontal matters |
| Elasticity | Automatic scaling with demand | Same as scalability |

## 8. Next
Dive into [Virtualization & Containers](virtualization-containers.md) or return to [Overview](overview.md).
