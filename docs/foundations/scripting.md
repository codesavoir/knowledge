# Scripting (Bash & Python)

> Build reliable automation with defensive patterns.

## Bash Principles
- Fail fast: `set -euo pipefail`
- Quoting matters: `"$var"`
- Use functions & meaning names
- Validate prerequisites & versions

### Template
```bash
#!/usr/bin/env bash
set -euo pipefail
IFS=$'\n\t'

log() { printf "[%s] %s\n" "$(date -Is)" "$*"; }
err() { log "ERROR: $*" >&2; }
trap 'err "Line $LINENO failed"' ERR

require() { command -v "$1" >/dev/null || { err "Missing $1"; exit 1; }; }
require jq

main() {
  : # script body
}
main "$@"
```

## Python Automation Pattern
```python
#!/usr/bin/env python3
from __future__ import annotations
import argparse, logging, sys, pathlib

logging.basicConfig(level=logging.INFO, format='%(asctime)s %(levelname)s %(message)s')

def parse_args():
    p = argparse.ArgumentParser(description='Example tool')
    p.add_argument('--input', required=True)
    return p.parse_args()

def main():
    args = parse_args()
    path = pathlib.Path(args.input)
    if not path.exists():
        logging.error('Input missing')
        return 1
    logging.info('Processing %s', path)
    return 0

if __name__ == '__main__':
    sys.exit(main())
```

## Patterns
| Problem | Bash | Python |
|---------|------|--------|
| JSON parse | `jq -r '.items[]'` | `json` module / `pydantic` |
| HTTP call | `curl -sS` | `requests` / `httpx` |
| Concurrency | GNU parallel | `asyncio` / `concurrent.futures` |
| CLI UX | flags + help | `argparse` / `typer` |

## Testing
- Bash: encapsulate logic -> test with `bats`
- Python: `pytest -q`, use fixtures, property tests for pure funcs

## Distribution
- Package Python tool with `pipx`
- Provide container image w/ pinned deps
- Document required env vars & exit codes

---
**Next:** CI/CD landscape → [CI/CD Overview](../ci/overview.md)
