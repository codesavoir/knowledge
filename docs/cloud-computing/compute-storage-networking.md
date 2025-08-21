---
# Compute, Storage & Networking Basics

tags: [Cloud, Core Services]
---

## 1. Compute Primitives
| Type | Characteristics | When To Use | Watch For |
|------|----------------|------------|----------|
| VM | Full OS control, predictable | Legacy apps, custom runtimes | Patch toil, slower scaling |
| Managed Containers | Orchestrated pods/services | Microservices, APIs | Cluster capacity mgmt |
| Functions (FaaS) | Event execution, scale to zero | Spiky workloads, glue logic | Cold starts, execution limits |
| Batch / Jobs | Scheduled / queue driven tasks | ETL, ML preprocessing | Queue sizing, retries |

## 2. Storage Spectrum
| Type | Access Pattern | Strengths | Constraints | Typical Cases |
|------|---------------|----------|-----------|---------------|
| Object | HTTP (eventual consistency) | Durability, scale, cost | Higher latency, no POSIX | Media, backups, logs |
| Block | Attached volume | Low latency, IOPS | AZ bound, manage lifecycle | Databases, high I/O apps |
| File | Shared hierarchical | Shared access, POSIX | Throughput ceilings | Content repos, legacy lift |
| In‑Memory Cache | Key/value | Microsecond latency | Volatile, cost/GB | Hot data, sessions |
| Archive | Cold retrieval | Ultra low cost | Retrieval delay | Compliance storage |

## 3. Networking Building Blocks
| Component | Purpose | Notes |
|----------|---------|------|
| VPC / VNet | Isolated virtual network | Define CIDR carefully (avoid overlaps) |
| Subnet (Public/Private) | Segment workloads & routing | Private for backend, public for ingress |
| Route Table | Direct traffic flows | Document custom routes |
| Internet / NAT Gateway | Outbound / inbound control | NAT for private egress |
| Load Balancer | Distribute traffic & health checks | Layer 4 vs 7 differences |
| Security Group / ACL | Stateful / stateless filtering | Principle of least privilege |
| DNS | Naming to IP resolution | TTL tuning impacts failover |
| CDN | Edge caching & acceleration | Offload origin, improve latency |

## 4. Reference Flow (Annotated)
```
Client → CDN → DNS → Load Balancer → App Service (containers/functions) → Cache → Database (primary/replica) → Object Storage (assets/logs)
```

## 5. Common Patterns
| Objective | Pattern | Benefit |
|----------|---------|---------|
| Read scalability | Cache aside | Reduce DB load |
| Resilience | Multi‑AZ deployment | Survive single AZ outage |
| Cost control | Lifecycle policies | Automatic tiering |
| Fault isolation | Segmented subnets & SGs | Limit blast radius |
| Latency reduction | CDN + edge compute | Closer to users |

## 6. Capacity Planning Inputs
- Baseline & peak RPS
- Data growth (GB/month)
- Latency SLO (p95)
- Availability target (%), implied downtime budget

## 7. Next
Proceed to [Scalability & Elasticity](scalability-elasticity.md) or return to [Virtualization & Containers](virtualization-containers.md).
