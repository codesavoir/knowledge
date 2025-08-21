# Branching Strategy

## Main Branches
- `main`: production-ready code.
- `develop`: integration branch for next release.

## Supporting Branches
- `feature/*`: new features.
- `hotfix/*`: urgent production fixes.
- `release/*`: prepare a release (version bump, docs).

## Flow
1. Create feature branch from develop.
2. Work & commit.
3. Open Pull Request (PR) into develop.
4. After testing, merge.
5. Create release branch -> finalize -> merge to main & tag.
