# Playbook: TLS Certificate Expiry

## Detection
- Alert: Cert expires < 14 days.

## Triage
- Identify issuing CA & automation path.
- Check ACME / cert-manager logs.

## Mitigation
- Force renew (cert-manager annotate).
- Manual replacement if automation failed.

## Prevention
- Short cert lifetimes + automation.
- Dashboard of expiry dates.

> TODO: Add openssl command examples.
