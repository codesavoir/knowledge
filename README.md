# Codesavoir Knowledge Base

Concise, vendor‑neutral DevOps & IT knowledge (current focus: Cloud Computing & Git Flow).

## Purpose
Offer clear, actionable reference material without noise.

## Current Sections
- Cloud Computing (foundations, architecture, security, cost, resilience)
- Git Flow (branching, commits, review, releases)

## Quick Start
```bash
python -m pip install --upgrade pip
pip install mkdocs-material pymdown-extensions mkdocs-git-revision-date-localized-plugin \
           mkdocs-minify-plugin mkdocs-glightbox mkdocs-macros-plugin
mkdocs serve
```
Site: http://127.0.0.1:8000

## Deploy
GitHub Actions builds on PRs and deploys only after merge to `main` (GitHub Pages).

## Contribution Policy (Restricted)
This is a public read‑only knowledge base. Write access is limited to a small maintainer group.
- External PRs: Not accepted (will be closed politely).
- Issues: Tracking—feature suggestions are welcome.

## Maintainer Workflow
1. Create feature branch from `main`.
2. Edit / add docs.
3. `mkdocs build --strict` locally.
4. Open PR (auto build runs).
5. Required review (your account) → merge → auto deploy.

## Enforcing Restrictions (GitHub Settings)
Configure once (not in code):
1. Branch Protection: Settings → Branches → Add rule for `main`:
   - Require pull request before merging
   - Require approvals = 1 (you as reviewer)
   - Require status checks (Build job) to pass
   - Restrict who can push = maintainer team
2. CODEOWNERS (optional) to force your review:
```
# .github/CODEOWNERS
*  @ssumit22
```
3. Environment Protection (optional extra approval): Settings → Environments → `github-pages` → Required reviewers = you.

## Minimal Stack
- MkDocs Material (+ pymdown extensions, Mermaid via superfences)
- GitHub Actions → Pages

## License
All rights reserved

---
© 2025 Codesavoir
