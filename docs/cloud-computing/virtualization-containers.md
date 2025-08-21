---
# Virtualization & Containers (Execution Models)

tags: [Cloud, Compute]
---

## 1. Evolution
Physical → Virtual Machines → Containers → Serverless (functions / managed runtimes).

## 2. Virtual Machines
- Hardware abstraction via hypervisor (Type 1 bare‑metal vs Type 2 hosted).
- Strong isolation; full OS per guest.
- Overhead: boot time, patching lifecycle, larger images.

## 3. Containers
| Aspect | VM | Container |
|--------|----|----------|
| Isolation | Hypervisor boundary | Kernel namespaces / cgroups |
| Boot Speed | Minutes | Seconds |
| Density | Lower | Higher |
| Image Size | GB | MB‑hundreds |
| Custom Kernel Modules | Yes | Limited |

## 4. Container Orchestration Essentials
| Concern | What It Does |
|---------|--------------|
| Scheduling | Places workloads on nodes respecting resource requests |
| Service Discovery | Stable virtual endpoints for dynamic pods |
| Autoscaling | Adjust replicas from metrics/queue depth |
| Rollouts | Controlled deployment (blue/green, canary) |
| Secret Management | Inject credentials securely |
| Network Policy | East‑west traffic control |

## 5. Serverless (FaaS / Managed Containers)
| Attribute | Functions | Managed Container Service |
|-----------|----------|---------------------------|
| Scale to Zero | Yes | Sometimes (depends) |
| Stateful Sessions | No (stateless) | Limited (sticky sessions) |
| Startup Latency | Possible cold start | Warm containers/pods |
| Use Case | Event driven, bursty | Steady services, APIs |

## 6. Decision Matrix
| Requirement | Lean VM | Lean Containers | Lean Functions |
|-------------|--------|----------------|----------------|
| Legacy OS deps | ✓ | ~ | ✗ |
| High portability | ~ | ✓ | ~ |
| Spiky event traffic | ~ | ✓ | ✓✓ |
| Long‑running batch | ✓ | ✓ | ✗ (timeouts) |
| Fine kernel tuning | ✓ | ~ | ✗ |
| Minimal ops overhead | ~ | ✓ | ✓✓ |

## 7. Image Hygiene Practices
- Pin base image digest.
- Multi‑stage builds to strip tooling.
- Regular vulnerability scans (CI gate severity threshold).
- Immutable tags + provenance metadata.

## 8. Anti‑Patterns
| Anti‑Pattern | Issue | Alternative |
|-------------|-------|------------|
| Monolithic container (DB + app) | Coupled lifecycle, scaling mismatch | Separate services |
| Running containers as root | Escalation risk | Non‑root user, drop caps |
| Excessive tiny functions with tight coupling | Observability & coordination overhead | Cohesive service design |

## 9. Next
Continue to [Compute, Storage & Networking](compute-storage-networking.md) or back to [Key Concepts](key-concepts.md).
