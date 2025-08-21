# Kubernetes Architecture

> Core control plane & worker node components.

## Control Plane
| Component | Role |
|----------|------|
| API Server | REST/JSON front door, authn/z, admission |
| etcd | Consistent key-value store |
| Controller Manager | Reconciliation loops |
| Scheduler | Pod placement decisions |
| Cloud Controller | Integrates cloud resources |

## Worker Node
| Element | Function |
|--------|----------|
| Kubelet | Pod lifecycle management |
| Kube-Proxy | Services (iptables/ipvs) |
| CRI Runtime | Container interface (containerd) |
| CNI Plugin | Pod networking |
| CSI Driver | Storage integration |

## Reconciliation Loop
"Desired State" (YAML) → Controllers converge actual state continuously.

## Namespaces & Multi-Tenancy
- Resource quotas, limit ranges
- NetworkPolicies for isolation

## Extensions
| Type | Mechanism |
|------|-----------|
| Admission | Mutating / Validating webhooks |
| CRD | Custom resources & controllers |
| Operator | Domain logic automation |

---
**Next:** Operational practices → [K8s Operations](k8s-operations.md)
