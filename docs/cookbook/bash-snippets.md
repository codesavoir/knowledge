# Bash Snippets

Handy reusable shell patterns.

## Safer Scripting Preamble
```bash
set -euo pipefail
IFS=$'\n\t'
```

## Parallel Loop (xargs)
```bash
printf '%s\n' host{1..10} | xargs -n1 -P4 -I{} ssh {} uptime
```

## JSON Parsing
```bash
jq -r '.items[] | .metadata.name'
```

> TODO: Add log parsing examples.
