---
name: managing-projects-beads
description: Interact with the "Beads" (bd) CLI to track issues, plan work, and manage dependencies. Use this to maintain context across sessions.
---

# Managing Projects (Beads)

## Context
"Beads" is a local, git-backed issue tracker. It stores tasks as JSONL data in a hidden `.beads` folder.
Use this skill to identify "ready" work (unblocked tasks), create new implementation plans, or log bugs found during development.

## Instructions
1. **Discovery**: Always start a new session by checking for unblocked work (`bd ready`).
2. **Claiming**: Before writing code, update the relevant issue status to `in_progress` so other agents/users know it is active.
3. **Atomic Work**: Link every code change to a specific Bead ID (e.g., `bd-a1b2`).
4. **Completion**: When finished, close the issue with a summary of the resolution.

## Essential Commands
* **Check Ready Work**: `bd ready --json` (Preferred for parsing)
* **Create Issue**: `bd create "Title" -t [bug|task|epic] -p [1-4]`
* **Update Status**: `bd update [id] --status in_progress`
* **Close Issue**: `bd close [id] --reason "Completed via PR #123"`
* **Read Issue**: `bd show [id] --json`

## Examples

### Scenario 1: Starting a Session
**User:** "What should we work on next?"
**Agent:** (Executes `bd ready --json`)
"I see task `bd-3f9a` ('Implement OAuth2 Login') is high priority and unblocked. Shall I start that?"

### Scenario 2: Creating a Plan (Epic)
**User:** "We need to add a payment system."
**Agent:** "I will create an Epic and breakdown tasks:"
1. `bd create "Payment System Integration" -t epic` -> Returns `bd-7x2y`
2. `bd create "Stripe API Client" -t task --deps parent:bd-7x2y`
3. `bd create "Checkout UI Component" -t task --deps parent:bd-7x2y`

### Scenario 3: Logging a Bug
**User:** "I noticed the header is misaligned on mobile."
**Agent:** (Executes `bd create "Header misalignment on mobile" -t bug -p 2 --label ui,mobile`)

## Error Handling
- If `bd` command is not found, ask the user to install it via `brew install steveyegge/beads/bd`.
- If `bd ready` returns nothing, check `bd list --status open` to see if items are blocked by dependencies.