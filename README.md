# Codesavoir Knowledge Base

Modern, curated, opinionated DevOps & IT engineering knowledge hub.

## Features
- MkDocs Material with dark/light mode, tabs, tags
- Structured domains: Foundations → Delivery → Reliability → Security
- High-signal playbooks & runbooks
- Style & contribution guides
- Automated build & deploy (GitHub Actions)

## Local Development
```bash
pip install -r requirements.txt  # (or see quick install below)
mkdocs serve
```
Site: http://127.0.0.1:8000

## Quick Start (No Virtualenv Shown)
```bash
python -m pip install --upgrade pip
pip install mkdocs-material mkdocs-awesome-pages-plugin mkdocs-git-revision-date-localized-plugin mkdocs-minify-plugin mkdocs-glightbox pymdown-extensions mkdocs-macros-plugin
mkdocs serve
```

## Contribution Workflow
1. Create feature branch
2. Add / update content under `docs/`
3. Run `mkdocs build --strict` (zero warnings goal)
4. Open PR with summary + screenshots if visual change
5. After merge main auto-deploys via GitHub Pages

## Content Philosophy
- Actionable > exhaustive
- Opinionated defaults with rationale
- Visual summaries (tables, lists) for scanning
- Cross-link related topics

## Roadmap
- Add diagrams (PlantUML / Mermaid)
- Search tuning (stop words, synonyms)
- Add analytics dashboards
- Content lint (custom macros)

---
© 2025 Codesavoir
