# Clean Handoff

Clean Handoff is a Codex skill for continuing work in a new task or returning a short, copyable handoff. Invoke it with `$clean-handoff`.

The handoff includes the objective, completed and remaining work, important decisions, relevant files and validation state, and the immediate next action. The destination must inspect its live workspace before making changes. Handoff text does not transfer approval.

## Direct Handoff

Ask Codex:

```text
Use $clean-handoff to create a Direct Handoff to a new task.
```

The skill uses context already in the conversation. It lists saved projects once and selects the project explicitly named by the user, or the unique project whose local path matches the current workspace. If there is no unique match, it asks for clarification.

By default, the new task uses the selected project's existing local workspace. Source and destination tasks share that checkout, so coordinate any edits between them.

An isolated worktree is used only when explicitly requested. For example:

```text
Use $clean-handoff to create a Direct Handoff in an isolated worktree, starting from the existing branch <branch-name>.
```

Name an existing starting branch, or explicitly request the selected project's current working-tree state. The skill does not infer a starting branch.

The agent makes one `create_thread` call, reports whether it succeeded, and does not retry automatically or wait for the new task to run.

## Portable Handoff

Ask Codex:

```text
Use $clean-handoff to produce a Portable Handoff.
```

The skill returns the short handoff in one copyable Markdown block. It calls no task tools and writes no handoff files. Use this route when you want to paste the context yourself or direct task creation is unavailable.

## Scope and privacy

- Ordinary handoffs use conversation context without a repository inventory, test run, or helper script. If a root `GAMEPLAN.md` exists, the skill reads it once immediately before handoff as the authority for plan status.
- Neither workflow creates checkpoints, receipts, packets, caches, or persistent transfer state.
- The skill instructs the agent to omit secrets, raw tool output, and speculative details. Review portable text before sharing it outside its intended destination.
- The destination must inspect its own live workspace. Transferred context cannot create, restore, or broaden approval.

## Requirements

- A Codex client with standalone user-skill support.
- Direct Handoff additionally requires saved-project listing and task creation tools.
- An explicit worktree request requires a client that supports that task environment and starting-state selection.

The skill has no runtime helper or Node.js dependency. Node.js 22 or newer is used for the package's development tests; CI is configured to run them on Windows, macOS, and Linux with Node.js 22 and 24.

## Installation

Copy the complete committed [`skills/clean-handoff/`](skills/clean-handoff/) directory into a Codex user-skill directory named `clean-handoff`, then start a new task to reload the skill. A typical Windows location is:

```text
C:\Users\<user>\.codex\skills\clean-handoff\
```

If a skill is already installed there, compare it with this package before replacing files. The package contains:

```text
clean-handoff/
  SKILL.md
  agents/openai.yaml
  tests/skill.test.mjs
```

There are no `scripts/` or `references/` directories in this package. Old marketplace/plugin installation commands and helper commands do not install or run this standalone skill.

## Development

From the repository root:

```text
node --test skills/clean-handoff/tests/*.test.mjs
```

The three tests check the instruction contract, package layout, and metadata. They do not execute real Codex task creation or establish end-to-end handoff reliability.

## License

MIT. See [LICENSE](LICENSE).
