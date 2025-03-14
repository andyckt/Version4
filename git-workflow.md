# Git Workflow for Solo Development

## Main Branches

- **main** (or master): Production-ready code. This branch should always be stable and deployable.
- **develop**: The main development branch where features are integrated. This is where you'll merge your feature branches.

## Supporting Branches

- **feature/[feature-name]**: For developing new features
- **bugfix/[bug-name]**: For fixing bugs
- **hotfix/[hotfix-name]**: For critical fixes to production code
- **release/[version]**: For preparing releases

## Workflow Overview

1. Create feature branches from `develop`
2. Develop new features in feature branches
3. Merge completed features back to `develop`
4. When ready for release, create a release branch from `develop`
5. Test and make final adjustments in the release branch
6. Merge the release branch to both `main` and `develop`
7. Tag the release in `main` with a version number 