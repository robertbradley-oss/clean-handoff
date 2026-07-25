# Direct Handoff

Use this workflow only after the user explicitly requests a new Codex task.

1. When the client supports independent read-only calls, begin saved-project listing and bounded live workspace inspection concurrently. Confirm that task creation is available while gathering only the objective, completed work, remaining work, important decisions, repository state, validation state, risks, and immediate next action.
2. Bound ordinary source inspection to current conversation context, the live root `GAMEPLAN.md` sections needed to establish authority and current work, concise repository status, and directly relevant validation evidence. Do not inventory the repository, read historical evidence, run tests, or scan unrelated files unless material uncertainty requires it.
3. Call `node scripts/clean-handoff.mjs prepare --project-root <root>` once with `mode: "direct"`, the saved-project list, and the compact context. Stop unless the result reports one exact match.
4. Use only the returned `handoff_text` as the destination prompt. It is context only and carries no approval.
5. For a Git project, use an isolated worktree by default. Use the saved project directly only when the user explicitly requests that local shared-checkout behavior; explain that it can avoid worktree provisioning but lets the source and destination tasks modify the same checkout. A request for speed alone does not select the shared checkout.
6. Invoke `create_thread` exactly once for the saved project at the returned match index and chosen environment. Do not retry automatically.
7. Report the direct tool result honestly. A queued, failed, or unknown result is not a created task; do not create local recovery state.

The destination must inspect its live repository and live canonical `GAMEPLAN.md` before acting. Treat the bounded source GamePlan read as live authority, and stop for one clear confirmation if identity, authority, or live state is uncertain or changes before task creation.
