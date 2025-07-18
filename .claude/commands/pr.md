---
description: Create a pull request for the current branch
allowed-tools: Bash(git:*), Bash(gh:*)
---

# Create Pull Request

Create a pull request for the current branch.

## Your Task:

1. Check the current branch status and ensure it's up to date
2. Review all changes that will be included in the PR
3. Analyze the commit history from the base branch to understand the full scope
4. Determine appropriate label based on branch type and changes
5. Create a comprehensive PR with a clear title, detailed description, and proper labels
6. Push the branch to remote if needed

## Context:

- Current branch: !`git branch --show-current`
- Git status: !`git status`
- Changes since main: !`git diff main...HEAD`
- Commit history: !`git log main...HEAD --oneline`
- Remote tracking: !`git status -b --porcelain`

## PR Requirements:

- Clear, descriptive title
  - For feature branches, start with "feat:", for fix branches, start with "fix:"
  - If a branch is still WIP, start with branch name with "[WIP]"
- Summary section with bullet points of key changes
- Test plan with actionable items
- Proper formatting with markdown
- Appropriate label from available options

## Available Labels:

- **feature**: New features and enhancements
- **fix**: Bug fixes and corrections
- **wip**: Work in progress (incomplete features)
- **prod release**: Production release PRs

## Label Selection Guidelines:

- Use "feature" for new functionality, improvements, or enhancements
- Use "fix" for bug fixes, corrections, or hotfixes
- Use "wip" for incomplete work or draft PRs
- Use "prod release" for production release PRs from develop to main

Create the PR using the `gh pr create` command with appropriate title, body, and `--label` flag.
