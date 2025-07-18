---
description: Commit changes to GitHub in logical, well-structured commits
allowed-tools: Bash(git:*)
---

# Commit Changes

Commit the changes so far to GitHub in one or few discrete commits that make sense.

## Your Task:

1. Review the current changes using git status and git diff
2. Analyze the nature of the changes and group them logically
3. Create meaningful commit messages that explain the "why" not just the "what"
4. Only commit files that are already staged (do not stage new files unless explicitly requested)
5. Follow the existing commit message style from recent commits

## Guidelines:

- Use present tense, imperative mood ("Add feature" not "Added feature")
- Keep the first line under 72 characters
- Focus on the purpose and impact of the changes
- Group related changes into single commits
- Separate different types of changes (features, fixes, refactoring) into different commits

## Context:

- Current status: !`git status`
- Staged changes: !`git diff --staged`
- Recent commits for style reference: !`git log --oneline -10`
