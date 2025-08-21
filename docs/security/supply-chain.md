# Supply Chain Security

Protect build & dependency pipeline integrity.

## Threats
- Dependency compromise
- Typosquatting
- Build environment tampering

## Controls
- SBOM generation (CycloneDX / SPDX)
- Signature verification (Cosign)
- Reproducible builds
- Provenance attestations (in-toto, SLSA)

## Automation
- Policy gates in CI (signature, vuln severity thresholds)

> TODO: Add example Cosign verification step.
