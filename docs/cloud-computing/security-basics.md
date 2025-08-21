---
# Security Basics & Governance

tags: [Cloud, Security]
---

## 1. Shared Responsibility Snapshot
| Layer | Customer | Provider |
|-------|----------|----------|
| Data | Classification, encryption, retention | Durable storage medium |
| Application | Code security, secrets handling | Runtime isolation |
| OS / Platform | Patch (IaaS) / configure (PaaS) | Patch (PaaS/FaaS) |
| Physical / Core Infra | - | Facilities, hardware, hypervisor |

## 2. Core Pillars
| Pillar | Focus | Example Control |
|--------|-------|----------------|
| Identity | Least privilege & authN/Z | Role-based access, SSO |
| Data Protection | Confidentiality & integrity | KMS-managed keys, envelope encryption |
| Network | Segmentation & exposure minimization | Private subnets, WAF |
| Detection & Response | Visibility & action | Centralized logs, alert runbooks |
| Governance | Policy, compliance, audit | Tag policies, config rules |

## 3. Identity & Access Patterns
- Use temporary credentials (OIDC / STS) over long-lived keys.
- Separate human vs machine roles; enforce MFA for humans.
- Principle of least privilege with periodic access reviews.

## 4. Encryption Practices
| State | Mechanism | Notes |
|-------|----------|------|
| At Rest | Provider-managed or customer-managed keys | Rotate keys; log key usage |
| In Transit | TLS 1.2+ enforced | Use cert automation (ACME) |
| In Use (emerging) | Confidential computing enclaves | Sensitive ML / finance workloads |

## 5. Network Safeguards
- Deny by default security groups / firewall rules.
- Layer 7 protection (WAF) for public HTTP ingress.
- Private endpoints / service endpoints to avoid public egress.

## 6. Secrets & Configuration
Store secrets in managed vault services; never in source control. Use envelope encryption and rotate on compromise triggers.

## 7. Observability for Security
Integrate audit logs, access logs, and network flow logs into SIEM. Define detection rules (anomalous location login, privilege escalation).

## 8. Threat Modeling Quick Pass
| Step | Question |
|------|----------|
| Assets | What data/functions are sensitive? |
| Entry Points | What interfaces are exposed? |
| Trust Boundaries | Where does data change classification? |
| Threats | Abuse scenarios (MITRE categories) |
| Controls | Prevent, detect, respond layers |

## 9. Zero Trust Principles
- Assume breach; authenticate & authorize each request.
- Continuous verification (device posture, context-aware access).
- Minimize implicit trust zones.

## 10. Governance & Policy Automation
Codify tagging, configuration, and guardrails via policy-as-code (e.g., OPA). Enforce drift detection pipelines.

## 11. Checklist
- MFA enforced for interactive users?
- Central log aggregation configured?
- Secrets scanning in CI?
- Data classification mapped to encryption policy?
- Access review cadence defined?

## 12. Next
Advance to [Cost & Pricing](cost-pricing.md) or revisit [Scalability & Elasticity](scalability-elasticity.md).
