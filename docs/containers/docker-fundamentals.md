# Docker Fundamentals

> Building minimal, secure, efficient container images.

## Image Principles
- Deterministic builds (pin versions, digest base)
- Minimal attack surface (distroless / alpine caution)
- Layer efficiency (order matters)
- Non-root runtime user

## Example Multi-Stage
```Dockerfile
# syntax=docker/dockerfile:1.7
FROM python:3.12-slim AS build
WORKDIR /app
COPY pyproject.toml poetry.lock ./
RUN pip install --no-cache-dir poetry && poetry export -f requirements.txt --output requirements.txt
COPY . .
RUN pip install --prefix /install -r requirements.txt

FROM gcr.io/distroless/python312-debian12
WORKDIR /app
COPY --from=build /install /usr/local
COPY src/ .
USER nonroot
ENTRYPOINT ["python", "main.py"]
```

## Security
- Scan (Trivy/Grype) in pipeline
- Use `--platform` for multi-arch builds
- Drop capabilities in runtime

## Operational Tips
- Leverage BuildKit & cache mounts
- Keep `.dockerignore` curated

---
**Next:** Harden container images → [Image Hardening](image-hardening.md)
