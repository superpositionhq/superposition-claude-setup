---
description: Create a production release pull request from develop to main
allowed-tools: Bash(git:*), Bash(gh:*), Bash(npm:*), Bash(git log*), Read, Edit
---

# Production Release PR

Create a production release pull request from develop branch to main with version update and comprehensive changelog.

## Your Task:

1. Check if currently on develop branch (abort if not)
2. **Update main branch**: Fetch latest changes and ensure main is up to date
3. Check current version in package.json
4. Ask user for new version number
5. Update package.json version and run npm install to update package-lock.json
6. Analyze commits and PRs since last main merge
7. Create production release PR with comprehensive changelog and "prod release" label

## Context:

- Current branch: !`git branch --show-current`
- Current version: !`node -p "require('./package.json').version"`
- Git status: !`git status --porcelain`
- Last main merge: !`git log --oneline --grep="Merge.*main" -1`
- Recent commits since last main merge: !`git log --oneline $(git merge-base HEAD main)..HEAD`

## Validation Steps:

1. **Branch Check**: Must be on develop branch
2. **Clean Working Directory**: No uncommitted changes
3. **Main Branch Update**: Fetch and update main branch to latest
4. **Version Update**: Update package.json and package-lock.json
5. **Changelog Generation**: Analyze commits and PRs for release notes

## Release Process:

1. Verify on develop branch
2. **Fetch latest changes**: `git fetch origin` to get latest remote changes
3. **Update main branch**: `git checkout main && git pull origin main && git checkout develop`
4. Check current version (format: X.Y.Z)
5. Prompt for new version following semantic versioning
6. Update version in package.json
7. Run `npm install` to update package-lock.json
8. Analyze changes since last main merge (now accurate)
9. Create PR with title "prod release vX.Y.Z"
10. Generate comprehensive description with:

- Version bump summary
- Key features and improvements
- Bug fixes
- Breaking changes (if any)
- Migration notes (if needed)

## PR Requirements:

- Title format: "prod release vX.Y.Z"
- Base branch: main
- Head branch: develop
- Label: "prod release"
- Comprehensive changelog with categorized changes
- Link to related PRs and issues
- Migration guide if breaking changes exist

## Important Notes:

⚠️ **Critical**: Always update main branch before analyzing changes to ensure accurate changelog generation. This prevents including unrelated changes that are already in main but not reflected in the local main branch.

Execute the production release workflow ensuring all steps are completed successfully.
