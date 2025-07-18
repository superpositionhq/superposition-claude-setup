# Superposition Claude Code Setup

This repository contains my Claude Code configuration and custom commands for running multiple AI coding agents in parallel.

## What's Included

### `.claude/settings.json`
Pre-configured settings with auto-approval for common operations like:
- Git operations (add, commit, push)
- File editing and creation
- GitHub PR creation
- Documentation updates

### `.claude/commands/`
Custom slash commands for Claude Code:

- **`/commit`** - Smart git commits with automatic change grouping
- **`/pr`** - Create GitHub PRs with proper context and labels
- **`/prod-pr`** - Production release workflow with changelogs
- **`/create-doc`** - Generate comprehensive technical documentation
- **`/update-doc`** - Keep docs in sync as code evolves
- **`/designer-mode`** - Product-focused design thinking
- **`/create-todo`** - Break features into trackable tasks
- **`/coding-guidelines`** - Enforce consistent code standards

## Quick Start

1. Clone this repo or copy the `.claude` folder to your project root
2. Install [Claude Code](https://docs.anthropic.com/en/docs/claude-code)
3. The settings and commands will be automatically loaded

## How to Use

Once installed, you can use commands like:

```
/commit
```
Claude will review your changes and create meaningful commits.

```
/create-doc auth-system
```
Claude will generate comprehensive documentation for your auth system.

```
/pr
```
Claude will create a GitHub PR with proper description and labels.

## Workflow Tips

- Use git worktree to run multiple Claude instances in parallel
- Start with specs, not code - use `/create-doc` first
- Chain commands for efficiency: "create-doc then commit then pr"

## Requirements

- Claude Code CLI
- Git configured with push access
- GitHub CLI (gh) for PR creation

## License

Feel free to use and modify these configurations for your own projects.