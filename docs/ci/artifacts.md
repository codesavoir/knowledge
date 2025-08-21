# Artifact Management

> Ensuring integrity, traceability, and efficient distribution of build outputs.

## Artifact Principles
- Immutable once published
- Content-addressable where possible (digest)
- Provenance & SBOM attached
- Retention policy aligned to compliance

## Lifecycle
```
Source -> Build -> Sign/Attest -> Store -> Promote -> Deploy -> Archive
```

## Repository Types
| Type | Examples | Notes |
|------|----------|-------|
| Packages | PyPI, npm | Pin exact versions |
| Containers | OCI registries | Multi-arch manifests |
| Binaries | JFrog, GitHub Releases | Checksums + signatures |
| Config Bundles | Helm charts, Kustomize | Versioned with app |

## Security
- Sign images (cosign) & generate attestations (SLSA)
- Scan on push + continuous re-scan
- Enforce provenance policy at deploy

## Metadata
| Attribute | Purpose |
|----------|---------|
| Version | Trace release lineage |
| Digest | Integrity verification |
| Build ID | Link back to pipeline |
| SBOM | Dependency transparency |
| License | Compliance checks |
| Security Scan Report | Risk posture |

## Cleanup Policy Example
- Keep last 30 prod releases
- Keep artifacts referenced by active deployments
- Auto-expire SNAPSHOT after 14 days

---
**Next:** Move to Cloud strategy → [Multi-Cloud Strategy](../cloud/multicloud-strategy.md)
