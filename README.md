# How to Run 10 AI Coding Agents Simultaneously Without Losing Your Mind

You're probably already using AI coding tools. Cool. Now let me show you how to run 10 AI coding agents simultaneously without losing your mind.

Here's exactly how.

## First, you need docs (in your codebase)

This whole thing falls apart if your codebase is undocumented garbage. AI agents need context to write good code.

Here's the thing: Even if you have docs, they're probably rotting in Notion or Confluence. Separated from code. Always outdated. Useless for AI.

**The fix: Generate docs directly in your codebase.**

Gemini 2.5 Pro is perfect for this—1M token context window means you can dump your entire codebase and get comprehensive docs back.

My process:
- Feed Gemini the full auth system code
- Get back: API docs, architecture overview, usage examples
- Save as `docs/auth-system.md` right in the repo
- Repeat for payments, user management, everything

Why this matters:
- Docs live with code—they travel together
- AI agents can update them with the `update-doc` command
- Drop them straight into any AI's context window
- No more "wait, which Notion page was that?"

Takes a day. Worth it. Without good docs in your codebase, AI just writes random code that doesn't fit your patterns.

## The actual setup that matters

Claude Code is the unlock. Seriously underrated. This is the cornerstone of making this workflow actually work.

I pay $200/month for Claude MAX. Why? Because I burn through tokens like crazy, and MAX gives you extended requests to Opus 4. Sonnet 4 is amazing, but Opus is a different beast for complex implementations.

### Git worktree is the secret sauce

Here's the problem: When you're running parallel AI implementations, they override each other's changes.

```
Claude Code Agent 1: "I'll update the auth service..."
Claude Code Agent 2: "I'll refactor the auth service..."
Claude Code Agent 3: "I'll add types to the auth service..."
```

Same files. Total chaos. Changes lost.

Git worktree creates separate folders for each branch:

```bash
git worktree add ../feature-auth feature-auth
git worktree add ../payments payments-refactor
git worktree add ../dashboard new-dashboard
```

Now you have:
```
codebase/           
  feature-auth/     # auth feature branch in its own folder
  payments/         # payment refactor branch in its own folder
  dashboard/        # dashboard branch in its own folder
```

Each folder is a complete, independent checkout. Change files in one, the others stay untouched. No conflicts. No overrides.

Here's where it gets powerful:
- Open Cursor in each worktree folder
- Start Claude Code in each Cursor window
- Load relevant docs into each Claude instance
- Run them all simultaneously

Four branches. Four Cursor windows. Four Claude Code agents. All working on different parts of your codebase without stepping on each other.

When Feature A is building, you're reviewing Feature B and spec'ing Feature C. True parallelization without the pain.

Cursor is just for humans now. I only use it for tab completion when I need to make small edits myself. Whatever autocomplete you like works—Cursor, Copilot, whatever. But Claude Code does the heavy lifting.

## The workflow that actually works

Never start with code. Start with specs.

1. **Describe the spec to Claude Code.** What are you building? Why? What's the user flow?

2. **Generate the design doc.** Since you already have system docs, Claude can write perfect technical specs. "Based on our auth system, write a design doc for adding OAuth."

3. **Then implement.** Only after the spec is solid do you tell Claude to start coding.

This forces you to think before building. The AI writes better code when it understands the why, not just the what.

Pro tip: Use Wispr Flow for voice input. Describing features out loud is 10x faster than typing.

## How I actually work

Monday morning. Pick 3-4 features to ship this week.

- **9:00 AM:** Branch 1 - Voice spec into Claude Code. "We need OAuth for Google and GitHub."
- **9:10 AM:** Claude generates design doc. Review, approve.
- **9:15 AM:** "Implement the OAuth flow based on this spec."
- **9:20 AM:** Branch 2 - Check payment webhook implementation from Friday.
- **9:30 AM:** Branch 3 - New feature spec. Voice input again.

I'm describing features while Claude implements the last one. True parallelization.

## The magic moment

Week 2. Something clicks.

You stop thinking about lines of code. You start thinking in features.

- Need search? Spec it. Claude writes the design doc. Then the code.
- Need to refactor payments? Describe the new flow. Get a migration plan. Execute.

Feels like cheating. It's just better workflow design.

## Why this works now

The models finally got good enough.

- Claude Code with Opus 4 can implement entire features with proper context
- Gemini 2.5 Pro generates docs that actually capture your patterns
- Git worktree keeps everything isolated and parallel
- Voice input makes spec writing instant
- Custom commands eliminate friction

Two years ago? Disaster. Today? This is how I ship.

## The Claude Code commands that make this possible

I've open-sourced my entire Claude Code setup. These custom commands are what make the parallel workflow actually work.

New to Claude Code commands? Check out the [official docs](https://docs.anthropic.com/en/docs/claude-code/slash-commands) to understand how slash commands work.

The command suite:

**Design & Planning:**
- `create-doc` - Turn specs into comprehensive tech docs
- `designer-mode` - Think like Linear/Airbnb when building features
- `create-todo` - Break features into trackable tasks

**Development Flow:**
- `commit` - Smart commits that group changes logically
- `update-doc` - Keep docs in sync as you build

**Shipping:**
- `pr` - Create PRs with proper context and labels
- `prod-pr` - Full production release workflow with changelogs

### Why these commands matter

Each command has pre-authorized permissions in `settings.json`. Claude can execute git operations, create PRs, and update files without asking permission every time.

Example: When I say "commit this", Claude:
- Reviews all changes with `git diff`
- Groups related changes
- Creates meaningful commit messages
- Pushes to GitHub

No copy-paste. No manual git commands. Just natural language.

**Pro tips:**
- Double tap Esc to clear current message
- Triple tap Esc to rewind conversation
- Chain commands: "create-doc then commit then pr"

This isn't just about saving keystrokes. It's about staying in flow state while managing 10 parallel implementations.

## Start small

1. Pick one feature
2. Generate system docs with Gemini 2.5 Pro
3. Clone my Claude Code commands
4. Voice your spec into Claude Code
5. Let it write the design doc
6. Review, then implement

Don't parallelize everything day one. Master the spec-first workflow first.

But once you do?

Everything changes.

**Real question:** How many features did you ship last week? How many could you ship with 10 parallel AI agents?
