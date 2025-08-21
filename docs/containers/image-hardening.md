# Image Hardening

> Reduce attack surface & improve supply chain integrity.

## Attack Surface Reduction
- Start from minimal base (distroless, alpine w/ caution)
- Remove package managers at runtime
- Eliminate shell if not needed

## Integrity & Provenance
- Pin base image by digest
- Record SBOM (cyclonedx, syft)
- Sign image + attestation (cosign)

## Vulnerability Management
- Continuous scanning (registry + pipeline)
- Set severity policy gates
- Patch base images promptly

## Runtime Hardening
- Run as non-root (USER)
- Read-only root FS + tmpfs mounts
- Drop Linux capabilities
- Seccomp & AppArmor profiles

## Example Policy (OPA snippet)
```rego
package policies.image

deny[msg] {
  input.Config.User == "root"
  msg = "Container must not run as root"
}
```

---
**Next:** Kubernetes architecture overview → [Kubernetes Architecture](k8s-architecture.md)
