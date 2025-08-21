# Makefile Patterns

## Phony Targets
```
.PHONY: build test clean
```

## Self-Documenting
```
help: ## List targets
	@grep -E '^[a-zA-Z_-]+:.*?##' Makefile | awk -F: '{print $1}'
```

## Caching
Use stamp files to avoid redundant work.

> TODO: Add docker buildx example.
