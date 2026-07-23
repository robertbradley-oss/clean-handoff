<p align="center">
  <img src="assets/logo.svg" alt="Clean Handoff" width="520">
</p>

# Clean Handoff

Move the minimum useful working context into one new Codex task—or produce
copyable handoff text—without transferring approval.

Clean Handoff is a self-contained Codex user skill invoked as `$clean-handoff`.
Its active product has two workflows: Direct Handoff and Portable Handoff.

## Why it exists

Long sessions accumulate decisions, constraints, commands, test results, repository state, and unfinished work. A raw transcript is too noisy, while an informal summary can quietly invent or omit facts.

Clean Handoff prepares a compact, human-readable summary containing only:

- the objective;
- completed work;
- remaining work;
- important decisions;
- repository state;
- validation state;
- risks;
- the immediate next action.

The receiver must inspect its live repository and live canonical `GAMEPLAN.md`
before acting. Handoff text is context only and never carries approval.

## Two workflows

### Direct Handoff

Direct Handoff matches the current workspace to exactly one saved local Codex
project, prepares bounded redacted text, and permits the agent to create one new
task in that project.

- The helper does not create the task.
- The agent makes exactly one Codex task-creation call and never retries
  automatically.
- No checkpoint, packet, receipt, cache, finalization record, or replay state is
  created.
- Missing, unavailable, or ambiguous project identity stops at a clear
  confirmation boundary.

### Portable Handoff

Portable Handoff returns the same bounded redacted context in a copyable
Markdown block.

- It creates no task and calls no task tool.
- It writes no persistent transfer state.
- It works for Git and non-Git workspaces.
- The receiver is told to inspect its own live workspace and `GAMEPLAN.md`
  before acting.

## Usage

Ask Codex to use the skill explicitly:

```text
Use $clean-handoff to create a Direct Handoff to a new task.
```

Or request copyable text:

```text
Use $clean-handoff to produce a Portable Handoff.
```

Direct Handoff requires an active workspace that matches exactly one saved
local project and a client that exposes Codex task creation. Portable Handoff
is the fallback when task creation or exact saved-project identity is
unavailable.

## Safety and privacy

- `GAMEPLAN.md` remains the only plan authority; transferred text cannot create,
  restore, or broaden approval.
- The packaged helper prepares text only. It does not call a network service,
  create a Codex task, or write transfer state.
- Direct Handoff permits one task call; Portable Handoff permits none.
- Output is bounded and redacted. Raw saved-project IDs, complete environment
  values, secrets, and raw subprocess diagnostics are not exposed.
- The workflows do not change project source, Git state, installation state, or
  retained evidence.
- Material uncertainty stops for confirmation instead of guessing.

Pattern-based redaction cannot recognize every sensitive value. Review Portable
Handoff text before sharing it outside its intended destination.

## Requirements and verified platforms

- A current Codex client with standalone user-skill support.
- Node.js 22 or newer for the packaged helper.
- Direct Handoff additionally requires saved-project listing and task creation.
- Portable Handoff supports Git and non-Git workspaces.

The source package passed CI on Windows, macOS, and Linux with Node.js 22 and
24. Phase G also proved a fresh Windows user-skill installation, Direct and
Portable workflows, move-based rollback, and exact restoration. No earlier
Codex client-version floor is claimed.

## Installation

The standalone skill is distributed from the exact committed
`skills/clean-handoff/` directory. The old marketplace/plugin commands do not
install this completed standalone product.

For local source use, copy the complete `skills/clean-handoff/` directory to a
Codex user-skill directory named `clean-handoff`, then start a new Codex task so
the skill is reloaded. The Phase G Windows installation target was:

```text
C:\Users\<user>\.codex\skills\clean-handoff\
```

Verify that the installed directory contains `SKILL.md`, `agents/`,
`references/`, `scripts/`, and `tests/`, then invoke `$clean-handoff` in the new
task. Phase G directly proved this installation lifecycle on Windows; the
package itself is cross-platform CI-verified.

## Retired plugin generation

Earlier plugin-era releases are retired. Their source history, release assets,
and recovery evidence are preserved separately from the standalone
distribution.

Checkpoint, Quick Handoff, Resume, Status, ScopeLock transfer gates, receipts,
packets, and sideband storage are not active `$clean-handoff` workflows.

## Development

The standalone helper is dependency-free:

```text
node skills/clean-handoff/scripts/clean-handoff.mjs --help
node --test skills/clean-handoff/tests/*.test.mjs
```

The standalone suite covers both workflows, exact project selection, redaction,
output bounds, safe failures, filesystem safety, package boundaries, and
zero-write behavior. In the private source repository, `npm test` additionally
runs the retained historical plugin regression suite.

## License

MIT. See [LICENSE](LICENSE).
