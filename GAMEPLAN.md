# Clean Handoff Standalone Skill GamePlan

## Outcome

Deliver Clean Handoff as a self-contained standalone Codex skill under `skills/clean-handoff/`, with canonical explicit invocation `$clean-handoff`, whose primary job is to move the minimum useful working context into one new Codex task safely and clearly.

The finished skill must:

- Support one Direct Handoff that creates exactly one new task in the intended saved project and one Portable Handoff fallback that produces copyable text without creating a task.
- Produce a concise handoff containing the objective, completed work, remaining work, important decisions, repository state, validation state, risks, and the immediate next action.
- Require the destination task to inspect the live repository and live canonical `GAMEPLAN.md` before continuing; transferred text is context only and never carries approval.
- Use built-in Codex project and task capabilities directly. Do not require custom persistent receipts, prepared packets, finalization records, sideband transaction state, or replay protocols for an ordinary handoff.
- Keep Checkpoint, Resume, and Status outside the core handoff product. Retain them only if a separately demonstrated user need justifies a thin independent workflow; otherwise classify them for retirement without deleting them prematurely.
- Have no runtime dependency on ScopeLock, plugin metadata, plugin caches, or files outside the installed skill package.
- Preserve existing Phase D and v0.8 artifacts as evidence and recovery inputs while simplification, compatibility, and retention decisions are validated.
- Maintain one canonical implementation per retained behavior, the smallest cohesive runtime justified by the user workflow, reproducible generated artifacts, and evidence-backed cleanup.
- Pass official validation, focused automated tests, supported-platform CI, fresh installation, the two supported handoff flows, and any explicitly retained compatibility path.
- Publish the completed standalone skill as a clean public GitHub repository at `robertbradley-oss/clean-handoff`, replacing the plugin-era repository only after its history and release assets are recoverably preserved and the replacement is directly validated.

## Strategy

Use an evidence-led simplification:

1. Treat Phases A-D as historical evidence and a working baseline, not as a mandate to keep every implemented feature.
2. Center the product on one direct task handoff and one portable text fallback.
3. Use built-in Codex task creation, a compact prompt, and destination-side live inspection instead of a custom transfer protocol wherever those capabilities satisfy the user need.
4. Classify each existing module, command, workflow, test, and compatibility surface as retain, simplify, separate, or retire according to demonstrated user value and safety.
5. Keep only the safety rules necessary to select the right project, avoid secret leakage, create one task, prevent transferred approval, and stop on meaningful live-state uncertainty.
6. Preserve potentially consumed or historically necessary artifacts until Phase F proves their disposition and recovery path; simplification is not deletion authority.
7. Validate the minimal installed skill and its two supported flows before replacing or retiring broader plugin-era behavior.
8. Keep the canonical root `GAMEPLAN.md` tracked in the public standalone repository as durable project context. Produce product files from an exact source commit and explicit allowlist while excluding plugin-era product files and local `.gameplan/` evidence.
9. Preserve the old public repository's branches, tags, releases, assets, and material metadata before moving the public name to the standalone replacement; never merge or force-push the unrelated histories.
10. Treat deletion of the retired public repository as a final, separately approved material action after the replacement passes fresh-clone, CI, installation, and recovery checks.

Each write-based lettered phase requires an exact Approved Execution Slice. The already completed Phase D foundation and checkpoint boundaries remain historical milestones, not subphases. Close each lettered phase from direct evidence before advancing to the next letter.

## Guardrails

- Target `name: clean-handoff` and `skills/clean-handoff/`.
- Prefer the simplest built-in Codex path that completes the handoff; custom storage or protocol machinery requires a demonstrated platform gap and explicit approval.
- Create at most one destination task per Direct Handoff request. Never retry task creation automatically.
- Persist no transfer state by default. Portable Handoff may return text; Direct Handoff may use only the transient context required by the platform call unless a separately approved recovery requirement proves durable state necessary.
- Verify actual Codex invocation syntax instead of assuming `/clean-handoff` works literally.
- The installed skill must not depend on `.codex-plugin/`, plugin caches, or files outside its package.
- GamePlan is the only strategy and execution authority.
- Track the canonical root `GAMEPLAN.md` in `robertbradley-oss/clean-handoff`; keep `.gameplan/` reports, footprints, archives, task-temporary artifacts, and other local evidence out of the public repository unless separately approved.
- Stored handoff material can never create, restore, or broaden approval.
- With no valid approved GamePlan slice, transfer context only and stop for approval.
- Do not preserve feature parity with the six-workflow Phase D package or v0.8 protocol unless a current consumer or user need justifies it.
- Remove Clean Handoff's ScopeLock dependency without modifying ScopeLock itself.
- Preserve unrelated work and all artifacts with unresolved consumers or provenance.
- Do not optimize for arbitrary line, file, or size targets.
- Optimize for one canonical implementation per behavior, fewer authoritative surfaces, cohesive modules, reproducible outputs, and evidence-backed cleanup.
- Module extraction must not duplicate authority, schemas, normalization, safety rules, or transaction logic.
- Never delete, relocate, or archive material without consumer analysis, recovery instructions, direct validation, and explicit approval.
- Quantify Clean Handoff and ScopeLock separately and distinguish canonical source, generated distributions, staging copies, caches, historical evidence, compatibility artifacts, and unexplained duplication.
- Matching content is not automatically redundant; establish authority, lineage, consumers, and regeneration first.
- Do not modify installed caches as source.
- Preserve the unrelated private-source and legacy-public histories through checksummed recovery evidence; do not merge, rebase, or force-push one into the other.
- Commits, pushes, releases, publication, repository movement, public archival, and material deletion require separate approval.
- Every write phase must include `GAMEPLAN.md`, its evidence report, and its Task Footprint in Allowed files when those artifacts will be updated.
- A phase is complete only when every completion criterion has direct current evidence and every approved validation passes.
- Phase names use letters only. Historical implementation boundaries may have descriptive milestone names, but future work advances and closes by lettered phase rather than numbered or pseudo-phase steps.

## Approved Execution Slice

None approved. The Skills-repository publication slice closed on 2026-07-23 with direct evidence in `.gameplan/reports/2026-07-22-skills-repository-publication.md`.

## Historical Retained-Repository Deletion Record

### Retained-repository deletion slice — completed

Status: **approved on 2026-07-22** by the user's exact statement: “I explicitly approve the exact proposed retained-repository deletion slice in GAMEPLAN.md.”

Objective: Permanently delete only `robertbradley-oss/clean-handoff-source` and `robertbradley-oss/clean-handoff-legacy` from GitHub after immediately re-proving both recovery bundles and the legacy release-asset archive, while preserving the canonical public `robertbradley-oss/clean-handoff` repository, installed standalone skill, external recovery directory, local workspace, and all unrelated state.

Allowed workspace writes:

- `GAMEPLAN.md`
- `.gameplan/reports/2026-07-22-retained-repository-deletion.md`
- `.gameplan/footprints/2026-07-22-retained-repository-deletion.md`
- `.gameplan/footprints/2026-07-21-clean-handoff-standalone-compiled.md`
- `.gameplan/tmp/retained-repository-deletion/`

Approved external mutations after exact approval:

- Permanently delete private `robertbradley-oss/clean-handoff-source` with `gh repo delete robertbradley-oss/clean-handoff-source --yes` exactly once.
- After confirming the first repository is absent and the canonical repository plus recovery archive remain exact, permanently delete public `robertbradley-oss/clean-handoff-legacy` with `gh repo delete robertbradley-oss/clean-handoff-legacy --yes` exactly once.

Constraints:

- Treat `robertbradley-oss/clean-handoff` as protected and read-only. Its visibility, default branch, metadata, refs, actions, issues, releases, and files must not change.
- Treat `C:/Users/robby/Documents/Codex/2026-07-22/clean-handoff-public-recovery/` as protected and read-only. Do not move, compress, rename, rewrite, or delete it.
- Treat `C:/Users/robby/.codex/skills/clean-handoff/`, the local workspace, Phase F archive, Codex configuration, plugin/cache paths, and every unrelated repository as protected and read-only.
- Deletion removes the live GitHub repository pages, URLs, release pages, issue/PR presentation, settings, and social metadata. Recovery can recreate Git histories and files but cannot promise byte-for-byte restoration of GitHub-hosted presentation or URLs.
- Do not archive, privatize, transfer, rename, recreate, fork, mirror-push, release, tag, or otherwise mutate either deletion target before deletion.
- Run each exact deletion command at most once. Do not retry automatically. If the first deletion succeeds and the second fails, retain the partial state, preserve all recovery evidence, and stop without recreating either repository.
- Any mismatch in repository identity, exact heads, recovery manifest, bundle verification, isolated restore, legacy release-asset evidence, canonical repository fingerprint, installed-skill fingerprint, or protected-state check stops before the next deletion.
- Remove only `.gameplan/tmp/retained-repository-deletion/` after durable evidence is written. No other local or external deletion is authorized.

Completion criteria:

1. Immediately before deletion, the 21-entry external recovery manifest has SHA-256 `a19c87851f52a57983a3b0cd344e67086706298677f0a3ff5ed99b4ef536bc31`; every listed file matches its byte count and SHA-256; both bundles verify as complete histories and restore in isolation with every expected branch/tag head; all eleven legacy release assets match retained metadata.
2. Immediately before deletion, canonical `robertbradley-oss/clean-handoff` remains public at exact head `5a308ab7426cbf0b6b5f81f14b634b1b5b4ca0e6`, with default `main`, the intended metadata, exactly 21 tracked paths, and passing six-cell CI run `29973554084`.
3. The installed 15-file `$clean-handoff` package remains byte-identical to the canonical public package before and after both deletions and still exposes only Direct and Portable Handoff.
4. Only `robertbradley-oss/clean-handoff-source` and `robertbradley-oss/clean-handoff-legacy` are deleted; both exact GitHub API names are absent afterward, while the canonical repository and every protected or unrelated repository remain present and unchanged.
5. The external recovery directory and its exact manifest remain present and valid after deletion; concise evidence records the irreversible effects and manual recovery boundary; task-owned temporary restores are absent.
6. The deletion report directly covers every criterion, the task footprint and rebuilt fourteen-source compiled footprint are finalized, `Approved Execution Slice` returns to `None approved`, the retained-repository open question is resolved, and Current State records the final canonical-only GitHub layout.

Exact validation and execution sequence after approval:

1. Reinspect the three exact repositories, their visibility/default branch/heads, canonical metadata and inventory, legacy branches/tags/releases/assets/issues/PRs, the installed 15-file skill, the external recovery directory, and current workspace status. Stop on drift.
2. Recompute every `MANIFEST.tsv` row's byte count and SHA-256; require the exact manifest hash above; compare all eleven release assets with the retained release metadata.
3. Run `git bundle verify` on `legacy-public.bundle` and `private-source.bundle`; restore each with `git clone --mirror` only under `.gameplan/tmp/retained-repository-deletion/`; compare every restored branch and tag ref with `RECOVERY.md` and retained metadata.
4. Reconfirm canonical head/settings/tree/CI and compare the canonical 15-file skill manifest with the installed skill.
5. Run `gh repo delete robertbradley-oss/clean-handoff-source --yes` exactly once. Require the exact API name to be absent, then recheck the canonical repository, external recovery manifest, and installed skill before continuing.
6. Run `gh repo delete robertbradley-oss/clean-handoff-legacy --yes` exactly once. Require both deletion targets to be absent and canonical `clean-handoff` to remain exact.
7. Revalidate the recovery manifest, canonical repository, installed skill, unrelated/protected repository presence, and workspace boundary; write the durable report before cleanup.
8. Dry-run and remove only `.gameplan/tmp/retained-repository-deletion/`; finalize the report and task footprint; rebuild and finalize the compiled footprint from fourteen ordered sources; close through one targeted GamePlan Update only if every criterion passes.

Validation authorization: Exact approval grants standing authority only for the read-only inspections and bundle restores above, the two exact one-time `gh repo delete` commands in the recorded order, task-temporary cleanup, and the four administrative workspace writes. It grants no mutation of the canonical repository, recovery archive, installed skill, local product files, other GitHub repositories, Codex state, or any automatic retry or recreation.

Evidence state: Finalized. Both complete bundles and all eleven assets were re-proven immediately before deletion; `clean-handoff-source` and then `clean-handoff-legacy` were deleted exactly once; both API names are absent; canonical `clean-handoff`, six-cell CI, installed bytes, external recovery, unrelated repositories, and protected workspace state remain exact. Evidence: `.gameplan/reports/2026-07-22-retained-repository-deletion.md`.

#### Deletion-authentication amendment — completed

Status: **approved on 2026-07-22** by the user's exact statement: “I explicitly approve the exact proposed deletion-authentication amendment in GAMEPLAN.md.”

Objective: Add only GitHub's required `delete_repo` OAuth scope to the already active `robertbradley-oss` CLI credential, verify that exact capability, and then resume the otherwise unchanged approved recovery-and-deletion sequence.

Amended authorization and sequence:

- Run `gh auth refresh --hostname github.com --scopes delete_repo` exactly once for the already active `robertbradley-oss` account. Do not switch accounts, reset scopes, add any other scope, or expose credential material.
- The command may require browser or device confirmation by the user. If confirmation is unavailable, cancelled, ambiguous, or fails, stop without retry and leave both repositories intact.
- After success, run `gh auth status --hostname github.com` and require the active account to remain `robertbradley-oss` with `delete_repo` present in addition to its existing scopes. Do not print or persist the token.
- Only after that proof, resume the approved deletion slice from exact sequence step 1; all recovery gates, one-time deletion order, partial-failure behavior, protected paths, completion criteria, and prohibitions remain unchanged.

Validation authorization: Exact approval of this amendment grants standing authority only for the one scope-refresh command above, any user-facing OAuth confirmation it launches, and the supported read-only status verification. It grants no account switch, scope reset, additional scope, credential export, deletion retry, or other mutation.

## Historical Public Cutover Execution Record

### Recovery-and-public-cutover slice — completed

Status: **approved on 2026-07-22** by the user's exact statement: “I explicitly approve the exact proposed recovery-and-public-cutover slice in GAMEPLAN.md.”

Objective: Preserve and directly restore-prove both existing repository histories and every legacy public release asset, move the plugin-era public repository safely out of the canonical name, publish only the validated 20-file standalone candidate as a new clean public `robertbradley-oss/clean-handoff` history, validate it from a fresh clone and against the installed skill, remove the now-stale configured legacy marketplace through its supported command, and leave both old GitHub repositories retained for a separately approved final deletion.

Allowed workspace writes:

- `GAMEPLAN.md`
- `.gameplan/reports/2026-07-22-public-cutover.md`
- `.gameplan/footprints/2026-07-22-public-cutover.md`
- `.gameplan/footprints/2026-07-21-clean-handoff-standalone-compiled.md`
- `.gameplan/tmp/public-cutover/`

Approved external writes and mutations after exact approval:

- Create only `C:/Users/robby/Documents/Codex/2026-07-22/clean-handoff-public-recovery/` for checksummed Git bundles, all eleven legacy release assets, repository/release/PR metadata, a complete manifest, and recovery instructions.
- Rename public `robertbradley-oss/clean-handoff` to `robertbradley-oss/clean-handoff-legacy` only after the complete recovery set passes isolated restoration.
- Create one new public `robertbradley-oss/clean-handoff`, push one clean `main` history containing exactly the validated 20-file candidate, apply concise repository metadata, and observe its CI.
- Remove only the configured legacy marketplace named `clean-handoff` with `codex plugin marketplace remove clean-handoff`, after successful replacement validation and a final installed-skill fingerprint check.
- If cutover fails after the legacy rename but before replacement creation, rename `clean-handoff-legacy` back to `clean-handoff`. If replacement validation fails after creation, rename the replacement to the currently absent `clean-handoff-standalone-hold`, rename the legacy repository back to `clean-handoff`, preserve all evidence, and stop without deletion.

Constraints:

- The replacement source is exactly private commit `7afaf864a990b6839a49c213d520b7adac645171` and only these 20 paths: `.github/workflows/ci.yml`, `.gitignore`, `LICENSE`, `README.md`, `requirements-validation.txt`, and the exact 15 files under `skills/clean-handoff/` at that commit.
- Build the replacement in `.gameplan/tmp/public-cutover/` as a new repository with one clean initial commit. Never merge, rebase, force-push, graft, or expose the private-source or plugin-era histories.
- Treat `robertbradley-oss/clean-handoff-source`, the installed standalone skill, the Phase F archive, unrelated workspace files, all other repositories, and all other Codex configuration as read-only.
- Before any GitHub mutation, reconfirm the two source commit heads and full legacy inventory; prove `clean-handoff-legacy` and `clean-handoff-standalone-hold` remain absent; stop if any input has changed.
- Preserve the old public repository as public and unarchived under `clean-handoff-legacy` during this slice. Do not delete, privatize, archive, transfer, release from, or otherwise alter either retained old repository.
- The replacement receives no plugin-era tags, releases, assets, branches, marketplace files, GamePlan evidence, local artifacts, or private history. Do not create a release, package publication, PR, or tag.
- Do not overwrite the installed skill. Compare it read-only with the fresh public clone before marketplace removal and again afterward.
- Delete only `.gameplan/tmp/public-cutover/` after durable evidence is written and validated. The external recovery directory and both retained GitHub repositories are not cleanup candidates in this slice.
- Any failed checksum, restoration, candidate manifest, local validation, CI cell, fresh-clone validation, installed-byte comparison, repository-setting check, marketplace removal, or rollback check keeps the slice active and stops final closure.

Completion criteria:

1. The external recovery directory contains checksummed, isolated-restore-proven bundles for both the plugin-era public and private-source histories; all eleven legacy release assets match their GitHub SHA-256 digests; repository, branch, tag, release, asset, and merged-PR metadata plus concise recovery instructions are retained.
2. The old public repository is retained unchanged except for its approved rename to `clean-handoff-legacy`; its branch heads, five tags, five releases, eleven assets, and merged PR remain accessible and match the recovery inventory.
3. The new public `robertbradley-oss/clean-handoff` has one clean `main` history containing exactly the approved 20 paths and no plugin-era, private-source, GamePlan, staging, cache, generated-distribution, or local-evidence surface.
4. Syntax, the complete standalone suite, public help, whitespace checks, and the pinned official skill validator pass before publication and from a fresh clone of the exact public commit; public CI passes all six Windows/macOS/Linux by Node 22/24 cells.
5. The fresh-clone 15-file skill manifest is byte-identical to the approved committed package and retained installed `$clean-handoff` package; the installed skill remains unchanged and exposes only Direct and Portable Handoff.
6. The replacement repository is public at the canonical URL with `main` as default, the intended description/topics/license, and no unexpected branch, tag, release, asset, issue, or pull request.
7. The supported marketplace removal succeeds only after criteria 1–6 pass; the legacy marketplace is absent afterward while the standalone installation and every unrelated plugin, marketplace, skill, repository, archive, and workspace path remain unchanged.
8. The cutover report directly covers every criterion, the footprint is finalized and compiled, task-owned temporary files are absent, `Approved Execution Slice` returns to `None approved`, and final deletion of `clean-handoff-legacy` and `clean-handoff-source` remains unapproved.

Exact validation and execution sequence after approval:

1. Reinspect both GitHub repositories, exact branch heads, tags, releases, assets, PRs, visibility, settings, and local remotes; confirm the two reserved names and external recovery target are absent; fingerprint the installed standalone skill, configured marketplaces, and all unrelated plugin/skill entries.
2. Clone both existing repositories with `git clone --mirror`, create `git bundle create --all` bundles, export the legacy metadata, download all eleven release assets into tag-specific directories, build a sorted byte/SHA-256 manifest, and compare every asset hash with its GitHub digest.
3. Restore each bundle under `.gameplan/tmp/public-cutover/`, verify every expected branch/tag head, and verify the archived metadata, asset inventory, checksums, and recovery instructions before any GitHub mutation.
4. Run `git -c core.autocrlf=false archive` at `7afaf864a990b6839a49c213d520b7adac645171` for the exact 20-path allowlist, restore it under `.gameplan/tmp/public-cutover/replacement/`, prove the exact path manifest, and initialize a new `main` repository with one commit titled `Initial standalone Clean Handoff skill`.
5. In the candidate, run recursive `node --check`, `node --test skills/clean-handoff/tests/*.test.mjs`, `node skills/clean-handoff/scripts/clean-handoff.mjs --help`, `git diff --check`, the pinned official validator from `requirements-validation.txt`, and exact committed/candidate/installed skill-manifest comparison.
6. Run `gh repo rename clean-handoff-legacy --repo robertbradley-oss/clean-handoff --yes`, then `gh repo create robertbradley-oss/clean-handoff --public --source .gameplan/tmp/public-cutover/replacement --remote origin --push --description "Create trustworthy project handoffs for fresh Codex tasks."`; apply the approved topics and inspect all repository settings and refs.
7. Identify the CI run for the exact public commit, run `gh run watch <exact-run-id> --exit-status`, and prove all six jobs passed. Fresh-clone the canonical URL under `.gameplan/tmp/public-cutover/fresh-clone/`, repeat every command in step 5, and confirm criteria 2, 3, 5, and 6 directly.
8. Re-fingerprint the installed standalone skill, run `codex plugin marketplace remove clean-handoff` exactly once, inspect supported plugin/marketplace state, and re-fingerprint the installed skill plus unrelated entries. Do not retry or edit configuration manually on failure.
9. Reinspect both retained old repositories and the replacement, validate the external recovery manifest again, remove only `.gameplan/tmp/public-cutover/`, finalize the report and footprint, rebuild the compiled footprint, and close through one targeted GamePlan Update only if every criterion passes.

Validation authorization: Exact approval of this proposal grants standing authority only for the bounded archive exports/downloads, temporary construction, tests and inspections, two Git bundles, one legacy rename, one new public repository and clean initial push, repository metadata, CI observation, fresh clone, one supported marketplace-removal command, the stated non-destructive rollback renames if required, task-temporary removal, and administrative evidence writes above. It grants no authority to delete, privatize, archive, transfer, merge, force-push, release, tag, or otherwise mutate either retained old repository or any unrelated state.

Evidence state: Finalized. The first CI failure and rollback, exact source-blob correction, passing six-cell run `29973554084`, final canonical cutover, supported marketplace removal, retained-state proof, and cleanup are recorded in `.gameplan/reports/2026-07-22-public-cutover.md`. No retained repository was deleted.

#### Public-cutover line-ending amendment — completed

Objective: Repair only the public repository's cross-platform checkout contract by adding the exact source `.gitattributes`, validate the retained candidate on all six CI cells and from a default Windows clone, then resume the already approved name cutover and marketplace-removal sequence without deleting or rewriting history.

Amended scope and mutations:

- Add `.gitattributes` from private commit `7afaf864a990b6839a49c213d520b7adac645171` as the twenty-first replacement path. Its exact Git blob is `dcb9ec8aa947092e514dc24e055e88bb3bca38dc`; it enforces LF for text and marks PNG/JPEG/GIF/WebP files binary.
- Modify only `.gameplan/tmp/public-cutover/replacement/.gitattributes` and its temporary Git repository; create one second commit titled `Preserve LF checkouts across platforms` and push it only to `robertbradley-oss/clean-handoff-standalone-hold` using that exact URL without force.
- Observe the hold repository's six-cell CI. If every cell passes, fresh-clone it with default Windows Git behavior, repeat the exact local candidate gates, and prove the 15-file skill remains byte-identical to the installed package.
- Only after those checks pass, rename canonical `clean-handoff` to `clean-handoff-legacy`, rename `clean-handoff-standalone-hold` to `clean-handoff`, validate names/settings/refs again, and resume original steps 8–9 including the one supported marketplace removal.
- If any amended validation fails, retain the current safe names (`clean-handoff` legacy and `clean-handoff-standalone-hold` candidate), make no further repository mutation, keep the marketplace configured, and stop for evidence-backed review.

Constraints:

- This amendment supersedes only the original 20-path count with 21 paths and permits exactly one non-force corrective commit on the held candidate. Every other approved constraint, completion criterion, recovery artifact, installed-skill protection, rollback rule, deletion prohibition, and validation command remains unchanged.
- Do not modify any skill file, test, workflow, README, license, requirement, private-source ref, plugin-era ref, installed file, archive file, marketplace configuration before the amended gate passes, or unrelated state.
- Do not delete, squash, rebase, reset, force-push, recreate, privatize, archive, release, tag, or open a PR in any repository.

Completion evidence required before resuming cutover:

1. The held candidate has exactly 21 tracked paths, only `.gitattributes` differs from `e61b384`, and its new commit has `e61b384` as its sole parent.
2. A local checkout with `core.autocrlf=true` retains LF bytes for `SKILL.md`; recursive syntax, all standalone tests, help, whitespace, official validation, and installed-manifest comparison pass.
3. All six public CI cells pass at the exact amended hold commit, including the previously failing Windows 22 and 24 cells.
4. A fresh default Windows clone matches the held commit and the installed 15-file skill byte-for-byte before either approved rename resumes.

Validation authorization: Exact approval of this amendment grants standing authority only for the one `.gitattributes` extraction, one temporary candidate commit, one ordinary push to the exact hold repository, CI observation, one default Windows fresh clone, the existing local validations, the two already approved success-path renames, and resumption of original steps 8–9 after all amended gates pass. It grants no product/test/workflow repair, retry after a failed amended gate, force-push, deletion, release, tag, PR, or additional repository creation.

Status: **approved on 2026-07-22** by the user's exact statement: “I explicitly approve the exact proposed public-cutover line-ending amendment in GAMEPLAN.md.”

#### Source-blob identity correction — completed

The approved line-ending amendment identifies the source `.gitattributes` by both exact commit/path and blob ID, but its recorded blob ID was produced after PowerShell transformed the displayed byte stream. Repository-native inspection at 2026-07-22T22:02:38-04:00 proves `7afaf864a990b6839a49c213d520b7adac645171:.gitattributes` is the 87-byte Git blob `dcb9ec8aa947092e514dc24e055e88bb3bca38dc`.

Proposed correction:

- Replace only `dda4d227bd182779f052605c91ac88de409ba02a` with `dcb9ec8aa947092e514dc24e055e88bb3bca38dc` in the approved amendment's `.gitattributes` identity.
- Preserve the exact source commit, path, content, 21-path boundary, single corrective commit/push, validation gates, success-path renames, marketplace sequence, rollback behavior, deletion prohibitions, and every other approved field unchanged.
- Extract the file with repository-native Git plumbing and verify the staged blob equals `dcb9ec8aa947092e514dc24e055e88bb3bca38dc` before committing. Any mismatch stops without a write, commit, push, retry, or repository mutation.

Status: **approved on 2026-07-22** by the user's exact statement: “I explicitly approve the exact proposed source-blob identity correction in GAMEPLAN.md.”
## Historical Phase G Execution Record

### Phase G — Full Validation and Closure

Status: **approved on 2026-07-22** by the user's exact statement: “I explicitly approve the exact proposed Phase G full-validation-and-closure slice in GAMEPLAN.md.”

Objective: Prove the retained 15-file Direct/Portable package as a self-contained installed skill, establish current Windows/macOS/Linux and Node 22/24 evidence, exercise one real Direct Handoff and one Portable Handoff, prove rollback/reinstallation and archival recovery, resolve final consumer and safety checks, and close this GamePlan without releasing or publishing the product.

Allowed workspace writes:

- `GAMEPLAN.md`
- `.github/workflows/ci.yml`
- `.gameplan/reports/2026-07-22-phase-g-full-validation-and-closure.md`
- `.gameplan/footprints/2026-07-22-phase-g-full-validation-and-closure.md`
- `.gameplan/footprints/2026-07-21-clean-handoff-standalone-compiled.md`
- `.gameplan/tmp/phase-g/`
- `.git/` only for the exact branch, index, commit, and private-origin push commands below

Approved external mutations after exact slice approval:

- Create the previously absent user-skill path `C:/Users/robby/.codex/skills/clean-handoff/` from the reproducible package archive, temporarily move only that newly created path into `.gameplan/tmp/phase-g/rollback/clean-handoff/` to prove rollback, then restore it and retain the verified standalone installation.
- Create exactly one local Codex validation task in saved project `2d6ae4b0-af19-42fd-92ed-c80f80c97f29` (`clean handoff`) through one `create_thread` call, never retry automatically, wait for its validation-only response, and archive that validation task after evidence capture.
- Create branch `codex/phase-g-validation`, commit only the exact standalone package and cross-platform validation workflow, push only that branch to private remote `origin`, and observe its CI. Do not push to `marketplace`.
- Create an isolated Python environment only under `.gameplan/tmp/phase-g/` and download only the pinned `requirements-validation.txt` dependency needed by the official validator.

Constraints:

- Treat `skills/clean-handoff/`, `requirements-validation.txt`, the Phase F archive and checksum, all prior evidence, root v0.8 product files, plugin caches, ScopeLock, `.release-staging/`, and sibling-product surfaces as read-only inputs. A product-code, workflow, metadata, dependency, archive, or retained-evidence repair requires a separately approved amendment.
- Modify `.github/workflows/ci.yml` only to replace plugin-era validation paths with the standalone package's recursive syntax checks, full standalone suite, named-transition root regression, pinned official standalone-skill validator, and existing Windows/macOS/Linux by Node 22/24 matrix.
- Stage and commit only `.github/workflows/ci.yml`, `requirements-validation.txt`, and the exact files under `skills/clean-handoff/`. Before commit, prove the staged path set equals that allowlist and `git diff --cached --check` passes.
- The private validation commit and branch are evidence only: no pull request, merge, tag, release, marketplace push, public publication, force-push, rebase, or unrelated history change is authorized.
- Before installation, re-confirm the exact user-skill target is absent. Do not overwrite any pre-existing installation. The existing v0.8 plugin cache is read-only and must have the same manifest hash before and after install, rollback, and reinstall.
- Direct Handoff may call `create_thread` exactly once only after local validation, reproducible packaging, CI, and installed-byte comparison pass. A queued, failed, unknown, wrong-project, or ambiguous result stops without retry and keeps Phase G active.
- The destination prompt is context-only and validation-only. It must require live repository and live `GAMEPLAN.md` inspection, state that no approval transfers, prohibit mutation, and request a concise observation before stopping.
- Portable Handoff must make no task-tool call and write no persistent transfer state.
- Temporary workspace artifacts must remain under `.gameplan/tmp/phase-g/`, be fingerprinted when used as evidence, and be removed before closure. No material deletion is authorized beyond task-owned temporary files; rollback uses a verified move rather than deletion.
- If any required command, CI cell, installation check, live workflow, archive recovery, privacy/accessibility check, consumer check, or footprint review fails or is uncertain, keep the slice active and stop for the smallest exact amendment or repair approval.

Completion criteria:

1. Every retained `.mjs` file passes syntax checks; focused and complete standalone tests, public help, the exact named-transition root regression, and the pinned official skill validator pass locally.
2. The updated private CI passes all six Windows/macOS/Linux by Node 22/24 cells at the exact validation commit, using the pinned official validator and no plugin validator or ScopeLock dependency.
3. Two `git archive` ZIPs made from the exact committed `skills/clean-handoff/` tree are byte-identical, their restored manifests match the committed package, and one archive is the source for the fresh user-skill installation.
4. The fresh installation is byte-identical to the committed package, surfaces `$clean-handoff` with only Direct and Portable workflows in a newly created task, and leaves the existing v0.8 plugin cache unchanged.
5. Direct Handoff selects the exact saved project, permits one call, creates exactly one destination task, performs no retry or custom transfer-state write, and the destination directly confirms live repository/GamePlan inspection plus non-transfer of approval before it is archived.
6. Portable Handoff returns bounded, copyable, redacted context with the required eight information fields, creates no task, writes no persistent state, and works for the approved non-Git case.
7. Repository-state, unavailable/ambiguous project identity, live-state uncertainty, secret redaction, output bounds, safe diagnostics, keyboard-readable guidance, and plain-language failure behavior have direct passing evidence.
8. Active runtime/package inspection proves no ScopeLock, plugin, cache, root-product, storage, receipt, packet, finalization, replay, or retired Phase D dependency; consumer inspection finds no unresolved current dependency on removed surfaces.
9. Moving the newly installed standalone skill out restores the pre-phase plugin-only state without changing the plugin cache; restoring the verified standalone directory re-establishes the exact installed manifest and invocation surface.
10. The Phase F archive checksum passes and an isolated representative restoration matches its internal manifest; deletion/retention evidence remains intact and no new cleanup candidate or open obligation is left unresolved.
11. The Phase G footprint and rebuilt compiled footprint are internally consistent, finalized, and contain no open cleanup obligation; protected pre-existing paths and unrelated work remain unchanged.
12. One targeted closing Update records Phase G evidence, compacts Current State, sets `Approved Execution Slice` to `None approved`, resolves or explicitly retains every Open Question, and marks the GamePlan complete without claiming a release or publication.

Exact local validation and Git commands, run from the workspace root in this order where dependencies apply:

1. `node --version` and `git --version`.
2. `$files = Get-ChildItem -LiteralPath 'skills/clean-handoff' -Recurse -File -Filter '*.mjs' | Sort-Object FullName; foreach ($file in $files) { node --check $file.FullName; if ($LASTEXITCODE -ne 0) { exit $LASTEXITCODE } }`.
3. `node --test skills/clean-handoff/tests/minimal-handoff.test.mjs skills/clean-handoff/tests/package-boundary.test.mjs skills/clean-handoff/tests/workflow-cli.test.mjs`.
4. `node --test skills/clean-handoff/tests/*.test.mjs`.
5. `node --test --test-skip-pattern="^plugin packages one valid router skill$" tests/*.test.mjs`.
6. `node skills/clean-handoff/scripts/clean-handoff.mjs --help`.
7. `python -m venv .gameplan/tmp/phase-g/venv`; `.gameplan/tmp/phase-g/venv/Scripts/python.exe -m pip install --disable-pip-version-check --requirement requirements-validation.txt`; `.gameplan/tmp/phase-g/venv/Scripts/python.exe C:/Users/robby/.codex/skills/.system/skill-creator/scripts/quick_validate.py skills/clean-handoff`. The validator file must first match SHA-256 `5347a0a09cfb546bba1c0d1a30dae0a233d9a05f57bd4e7877155c588bcdabf7`.
8. After the bounded CI workflow edit: `git switch -c codex/phase-g-validation`; `git add -- .github/workflows/ci.yml requirements-validation.txt skills/clean-handoff`; exact staged-allowlist inspection; `git diff --cached --check`; `git commit -m "Validate standalone clean-handoff skill"`; `git push --set-upstream origin codex/phase-g-validation`.
9. Capture `git rev-parse HEAD`; use `gh run list --workflow CI --commit <exact-HEAD> --json databaseId,headSha,status,conclusion --limit 10` to identify the one matching run; then `gh run watch <matching-run-id> --exit-status`; finally inspect all six jobs for the exact HEAD.
10. `git archive --format=zip --prefix=clean-handoff/ --output=.gameplan/tmp/phase-g/clean-handoff-a.zip HEAD:skills/clean-handoff` and the identical command with output `clean-handoff-b.zip`; compare both SHA-256 values and restore both under separate `.gameplan/tmp/phase-g/` directories for exact manifest comparison.
11. Re-run commands 2-6 against the restored/install-stage package where path substitution is necessary, run the official validator against that restored package, and compare its sorted path/byte/SHA-256 manifest with the committed package before the approved fresh install.
12. Verify `C:/Users/robby/.codex/skills/clean-handoff/` is absent and fingerprint the existing v0.8 plugin cache; copy only the verified restored package to that exact target; compare manifests; perform the one approved Direct Handoff task-tool call and the zero-call Portable Handoff; move the exact target to `.gameplan/tmp/phase-g/rollback/clean-handoff/`, prove plugin-only rollback, restore the target, and compare manifests and plugin-cache fingerprints again.
13. Verify `.gameplan/archives/2026-07-21-clean-handoff-phase-d-inactive.zip` against its `.sha256` sidecar, restore it only under `.gameplan/tmp/phase-g/archive-restore/`, and compare every restored byte count and SHA-256 to `ARCHIVE-MANIFEST.tsv`.
14. `git status --short --untracked-files=all`; `git diff --check`; footprint reconciliation; remove only `.gameplan/tmp/phase-g/`; repeat status/diff checks; then perform the targeted GamePlan/footprint closure Update only if every prior criterion passed.

Validation authorization: After explicit approval of this exact proposed slice, standing authorization covers only the commands, bounded workspace writes, exact private Git branch/commit/push, exact user-skill install/move/restore, one direct validation task creation and archival, CI observation, and inspections above. It does not authorize product repair, a second task-creation attempt, additional dependency installation, release, publication, PR creation, merge, tag, public push, or any other external or material action.

Evidence state: Pending. Detailed results must be recorded in `.gameplan/reports/2026-07-22-phase-g-full-validation-and-closure.md`; provenance must begin in `.gameplan/footprints/2026-07-22-phase-g-full-validation-and-closure.md` before the first approved task mutation.

#### Approved Phase G validation-only amendment

The first private CI run at validation commit `af4778dd746e68e8c77fd1381c555996d7dca054` passed both Ubuntu cells but failed both macOS and both Windows cells in the same test-fixture precondition at `skills/clean-handoff/tests/fs-safety.test.mjs:19`. The fixture creates `root` through the lexical `tmpdir()` path but compares it with `realpath(tmpdir())`; hosted macOS and Windows normalize those spellings differently, so all four filesystem tests stop before testing runtime behavior. No runtime failure is established.

Proposed amendment:

- Add only `skills/clean-handoff/tests/fs-safety.test.mjs` to Phase G write scope.
- Replace only `const root = await fsp.mkdtemp(path.join(tmpdir(), "clean-handoff-d1-fs-"));` with `const root = await fsp.realpath(await fsp.mkdtemp(path.join(tmpdir(), "clean-handoff-d1-fs-")));` so the fixture and its containment root use canonical path spellings.
- Do not change `fs-safety.mjs`, any runtime behavior, assertions, skip policy, safety boundary, workflow, metadata, dependency, or other test.
- Validate with `node --test skills/clean-handoff/tests/fs-safety.test.mjs`, `node --test skills/clean-handoff/tests/*.test.mjs`, and `git diff --check`.
- Stage only `skills/clean-handoff/tests/fs-safety.test.mjs`; prove that exact staged path; commit with `git commit -m "Fix cross-platform filesystem test fixture"`; push normally to the existing private `origin/codex/phase-g-validation` branch without force; identify the one CI run for the new exact HEAD and require all six jobs to pass.
- If the focused/full local test or any new CI job fails for another reason, stop without another edit or retry and request a new exact amendment.

Status: **approved on 2026-07-22** by the user's exact statement: “I explicitly approve the exact proposed Phase G validation-only amendment recorded in GAMEPLAN.md.” This approval activates only the one-line test-fixture correction, exact local validations, one-file private commit/push, and six-cell CI observation recorded above.

#### Approved Phase G archive-normalization amendment

The approved test-only amendment is complete: focused and full local tests passed, corrective commit `297ea96cd9e24a62b140ecec312d887889541183` contains only `skills/clean-handoff/tests/fs-safety.test.mjs`, and private CI run `29964979623` passed all six Windows/macOS/Linux by Node 22/24 jobs. The next packaging gate exposed a separate command-level issue. On this Windows checkout, Git has `core.autocrlf=true`; the exact plain `git archive` commands produce two byte-identical ZIPs but convert the committed LF text to CRLF. Both restored manifests match each other and normalize back to the exact committed Git blobs, but they do not match the committed package byte-for-byte, and the restored focused suite fails its exact frontmatter-byte assertion. No product-code failure is established.

Proposed amendment:

- Change only Phase G command 10 by prefixing both archive commands with `git -c core.autocrlf=false archive`; retain the same format, prefix, committed subtree, and Phase G output paths.
- Remove and recreate only the task-owned `.gameplan/tmp/phase-g/clean-handoff-a.zip`, `.gameplan/tmp/phase-g/clean-handoff-b.zip`, `.gameplan/tmp/phase-g/restore-a/`, and `.gameplan/tmp/phase-g/restore-b/` artifacts from the failed packaging attempt.
- Before regeneration, require `git diff --exit-code HEAD -- skills/clean-handoff` to prove the package worktree exactly represents the committed package. After restoration, require both ZIP SHA-256 values to match and each restored sorted path/byte/SHA-256 manifest to match the committed package worktree exactly.
- Re-run the recursive syntax checks, focused and full standalone suites, public help, retained root regression, and pinned official validator against the restored package where path substitution applies.
- Do not change any package file, test, runtime behavior, CI workflow, metadata, dependency, committed history, installation path, or other Phase G command. No additional commit or push is authorized.
- If archive reproducibility, raw manifest equality, or any restored-package validation still fails, stop without installation or task creation and request a new exact amendment.

Status: **approved on 2026-07-22** by the user's exact statement: “I explicitly approve the exact proposed Phase G archive-normalization amendment recorded in GAMEPLAN.md.” This approval activates only the two conversion-disabled archive commands, exact task-owned archive/restore replacement, manifest comparison, and restored-package validations recorded above.

## Workstreams

### Phase A — Evidence Audit and Architecture Verdict

- Inventory Clean Handoff's skills, helpers, workflows, schemas, tests, documentation, packaging, storage, integrations, and consumers.
- Quantify Clean Handoff and ScopeLock separately across canonical runtime code, tests and fixtures, documentation, generated distributions and staging copies, historical evidence, duplicated content, and compatibility or migration scaffolding.
- Record exact paths, counts, bytes, line-count method where useful, authority, ownership, consumers, checksums, and regeneration or recovery paths.
- Classify components as reuse, adapt, replace, or retire.
- Distinguish identical content from duplicated behavior or authority.
- Verify whether any hook, app, MCP server, authentication layer, or plugin-only capability exists.
- Produce an evidence-backed standalone architecture verdict and repository-diet baseline.

Complete when both products have separate reproducible inventories, every product component is classified, consumers and uncertainties are recorded, the verdict is supported, and no product source has changed.

### Phase B — Product and Invocation Contract

- Verify the installed Codex invocation and namespacing model.
- Define frontmatter, display name, default prompt, discoverability, and implicit-invocation behavior.
- Define each workflow's inputs, outputs, mutations, failures, and approval boundaries.
- Keep direct and portable handoffs explicitly distinct.
- Define supported Codex, Node, Git, OS, and non-Git requirements.
- Define reasoning-effort recovery, accessibility, privacy, redaction, output limits, and diagnostics.

Complete when the product contract is verified, user-readable, and contains no ambiguity that would materially alter implementation.

### Phase C — Authority, Data, Compatibility, and Module Architecture

- Define live GamePlan discovery and behavior for absent, malformed, changed, closed, proposed, and approved slices.
- Require destination verification against the live plan immediately before continuation.
- Ensure stored packets contain only inert plan context and cannot carry approval.
- Remove ScopeLock calls, schemas, digests, and compatibility gates from the new design.
- Define checkpoint, transfer, transaction, storage, versioning, migration, and legacy-read behavior.
- Decide the disposition of every ScopeLock integration point.
- Evaluate decomposing the current 5,747-line `scripts/clean-handoff.mjs` into cohesive internal modules.
- Extract modules only where cohesion, ownership, maintainability, or test isolation improves; keep behavior integrated where separation would weaken safety or duplicate canonical rules.

Complete when authority and compatibility matrices are explicit, every proposed module has a justified boundary, and construction has no material architectural ambiguity.

### Phase D — Standalone Construction

- Complete the remaining construction under one Phase D execution boundary; do not introduce numbered subphases.
- Create the self-contained `skills/clean-handoff/` package.
- Bring required scripts, references, schemas, templates, tests, and metadata inside the package.
- Implement the verified identity and invocation contract.
- Reuse approved deterministic checkpoint, repository, redaction, storage, and transaction machinery.
- Implement live GamePlan verification.
- Remove plugin and ScopeLock runtime dependencies.
- Preserve approved legacy readability without silently rewriting user data.
- Ensure retired concepts cannot remain accidentally authoritative.

Complete when all supported workflows load and operate from the standalone package, with no runtime resolution outside it and no ScopeLock dependency.

### Phase E — Minimal Handoff Simplification

- Make Direct Handoff and Portable Handoff the only advertised and supported active workflows.
- Build both flows from one compact, human-readable context model containing only the objective, completed work, remaining work, important decisions, repository state, validation state, risks, and immediate next action.
- Direct Handoff must identify the intended saved project, make exactly one built-in task-creation call, never retry automatically, and persist no custom receipt, packet, finalization, replay, or sideband transfer state.
- Portable Handoff must produce copyable handoff text without creating a task or writing persistent transfer state.
- Both flows must tell the destination to inspect the live repository and live canonical `GAMEPLAN.md` before acting, and must state that transferred context carries no approval.
- Retain only safety behavior required by these flows: correct target selection, secret redaction, bounded output, honest failure reporting, no transferred approval, and confirmation when identity or live state is materially uncertain.
- Remove Checkpoint, Resume, Status, Incoming Handoff, storage, receipts, packets, finalizations, replay, and legacy transfer protocols from the active product path without deleting their files or evidence in Phase E.
- Record every broader Phase D module, command, workflow, reference, test, schema, template, and compatibility surface in one exact Phase F input register with its path, known consumers, active-path status, proposed disposition, and unresolved risk.
- Simplify guidance, metadata, runtime, and tests around the two retained flows without optimizing for an arbitrary size or line-count target.

Complete when direct evidence proves that Direct Handoff creates exactly one correctly targeted task, Portable Handoff creates no task and returns usable text, both flows enforce live destination inspection and non-transfer of approval, neither flow depends on persistent transfer machinery, the active skill exposes no other workflow, focused regression tests pass, and every displaced Phase D surface is recorded for explicit retention or cleanup approval in Phase F.

### Phase F — Migration, Retention, and Repository Diet

Produce an exact deletion and retention manifest recording each artifact's path, owner, category, authority, consumers, lineage, checksum, regeneration or recovery method, proposed disposition, risk, validation, and approval state.

The manifest must:

- Consume the exact Phase E disposition register and resolve every recorded broader Phase D surface.
- Remove reproducible distributions and staging copies only after regeneration is proven.
- Move large historical validation artifacts outside active workspaces or into compressed, checksummed archival storage.
- Retain concise summaries, manifests, checksums, provenance, and recovery instructions.
- Preserve anything used by another skill, product, installation path, test, rollback process, or evidence chain.
- Preserve uncertain material pending investigation.
- Keep compatibility aliases thin, non-authoritative, and governed by retirement conditions.
- Require direct validation and explicit approval before material deletion, relocation, or archival.

Complete when the minimal standalone skill works without the plugin, active workspaces contain no unexplained copies, every retained or separated artifact has a reason, and every cleanup action is recoverable and proven safe.

### Phase G — Full Validation and Closure

Validate syntax, official skill packaging, focused regression, supported platforms, repository states, Direct Handoff, Portable Handoff, destination live-state checks, ScopeLock absence, any explicitly retained compatibility path, self-contained installation, upgrade and rollback, reproducible distributions, representative archive restoration, privacy, accessibility, consumers, and deletion safety.

Complete when every criterion has direct evidence, all footprints and cleanup obligations are resolved, the standalone installation is proven from its intended distribution source, and the GamePlan is closed through one targeted Update.

## Current State

### Completed

- Phase A established separate product inventories, authority/consumer maps, repository-diet findings, and the standalone architecture verdict: build `skills/clean-handoff/`, remove its ScopeLock dependency without changing ScopeLock, and preserve unresolved recovery surfaces. Evidence: `.gameplan/reports/2026-07-20-phase-a-evidence-audit.md`.
- Phase B verified `$clean-handoff` invocation and documented the broader six-workflow product contract. Its invocation, privacy, redaction, accessibility, and platform evidence remain useful; its workflow breadth is superseded by the minimal Outcome. Evidence: `.gameplan/reports/2026-07-20-phase-b-product-contract.md`.
- Phase C documented the broader GamePlan, v2 transfer, checkpoint/storage, legacy, ScopeLock-removal, effort, and module contracts. Those records remain safety and compatibility evidence, but the custom transfer family is no longer a required end state. Evidence: `.gameplan/reports/2026-07-21-phase-c-architecture-contract.md`.
- Phase D completed and validated a self-contained six-workflow standalone package with the broader protocol. It is preserved as a working baseline and simplification inventory, not the required final product shape. Evidence: `.gameplan/reports/2026-07-21-phase-d-standalone-construction.md`.
- Phase E reduced the active product to Direct and Portable Handoff, proved the two local workflow boundaries and minimal runtime graph, preserved broader Phase D surfaces as inactive evidence, and produced the Phase F disposition register. Evidence: `.gameplan/reports/2026-07-21-phase-e-minimal-handoff-simplification.md`.
- Phase F archived and directly restore-validated the disconnected Phase D boundary, removed only the 25 approved inactive paths, retained a 15-file minimal package, and resolved the repository-diet footprint without changing other generated, installed, operational, or historical surfaces. Evidence: `.gameplan/reports/2026-07-21-phase-f-repository-diet.md`.
- Phase G proved the committed 15-file package locally, in six-cell CI, from reproducible restored archives, as a fresh user-skill installation, through one Direct Handoff and one Portable Handoff, through move-based rollback, and through historical archive restoration. The standalone `$clean-handoff` installation is retained; no release or publication occurred. Evidence: `.gameplan/reports/2026-07-22-phase-g-full-validation-and-closure.md`.
- Post-closure reconciliation replaced the stale plugin-first README with current standalone Direct/Portable guidance and updated the legacy inventory test to expect both retained skills. All focused, standalone, and root regressions pass; the working skill is unchanged. Evidence: `.gameplan/reports/2026-07-22-post-closure-reconciliation.md`.
- The supported legacy-plugin uninstall removed only `clean-handoff@clean-handoff` and its managed v0.8 cache. The configured marketplace, exact standalone `$clean-handoff` installation, repository source, Phase F recovery archive, historical evidence, all other installed plugins, and protected workspace state remain. Evidence: `.gameplan/reports/2026-07-22-legacy-plugin-uninstall.md`.
- Public standalone preparation committed the exact three-file private-source reconciliation, passed all six private CI cells, and proved two byte-identical standalone-only candidates whose committed, restored, and installed 15-file skill manifests match exactly. No public repository state changed. Evidence: `.gameplan/reports/2026-07-22-public-standalone-preparation.md`.
- Recovery and public cutover retained complete checksummed recovery for both prior histories and all eleven release assets, published the clean 21-path standalone history at `robertbradley-oss/clean-handoff`, passed all six public CI cells and a default-Windows fresh clone, preserved exact installed-byte identity, moved the plugin-era repository to `clean-handoff-legacy`, retained the private source, and removed only the stale configured marketplace through the supported command. Evidence: `.gameplan/reports/2026-07-22-public-cutover.md`.
- Final retained-repository deletion re-proved both complete histories and every legacy asset, deleted only `clean-handoff-source` and `clean-handoff-legacy`, confirmed canonical `clean-handoff` is the sole remaining Clean Handoff GitHub repository, retained exact installed bytes and external recovery, preserved all unrelated state, and finalized all task cleanup. Evidence: `.gameplan/reports/2026-07-22-retained-repository-deletion.md`.
- Skills-repository publication added the exact canonical 15-file distribution to `robertbradley-oss/skills` through PR #2, passed the three-OS pull-request and merged-main CI matrices, passed a complete fresh-clone gate, preserved `robertbradley-oss/clean-handoff` as the sole implementation authority, and finalized task cleanup. Evidence: `.gameplan/reports/2026-07-22-skills-repository-publication.md`.
- The former v0.8 release GamePlan is superseded as governing strategy; its decision history remains preserved below.

### Active

- None.

### Blocked

- None.

## Task Footprint

- Finalized compiled: `.gameplan/footprints/2026-07-21-clean-handoff-standalone-compiled.md`; finalized source 15 is `.gameplan/footprints/2026-07-22-skills-repository-publication.md`.

## Next Move

Use `robertbradley-oss/clean-handoff` as the sole canonical implementation authority and `robertbradley-oss/skills/clean-handoff` only as its validated umbrella distribution. Preserve `C:/Users/robby/Documents/Codex/2026-07-22/clean-handoff-public-recovery/` until a separately approved retention policy provides equivalent recovery. No execution slice is currently approved.

## Open Questions

- Resolved: `robertbradley-oss/clean-handoff` is the clean public standalone history; the plugin-era repository is retained at `clean-handoff-legacy`.
- Resolved: checksummed bundles, all eleven release assets, material metadata, manifest, and recovery instructions are retained at `C:/Users/robby/Documents/Codex/2026-07-22/clean-handoff-public-recovery/`.
- Resolved: the stale configured `clean-handoff` marketplace was removed once through the supported command after replacement validation; the standalone `$clean-handoff` installation remains exact.
- Resolved: `clean-handoff-source` and `clean-handoff-legacy` were deleted only after immediate complete recovery proof; canonical `clean-handoff` and the external recovery directory remain exact.
- Retained: keep the checksummed Phase F archive in `.gameplan/archives/` until a separately approved external archival and retention policy exists.
- Retained: leave `.release-staging/`, ScopeLock distributions, and other historical generated surfaces unchanged because their separate recovery and consumer chains remain evidence.
- Retained uncertainty: support is proven on the current Codex client only; no earlier client-version floor is claimed without direct validation.
- Resolved: Checkpoint, Resume, and Status are retired from the core package and recoverable from the Phase F archive; create no optional skill unless a future demonstrated need is separately approved.
- Resolved: no current standalone consumer requires v2 receipts, packets, finalizations, sideband transfer storage, or unfinished v0.8 recovery; historical and installed v0.8 evidence remains retained.
- Resolved: Direct Handoff targets the current saved project through exact root matching; arbitrary saved-project selection is outside the completed product contract.

## Decisions

### Governing standalone-skill decisions

- 2026-07-24 — Publish and retain the canonical root `GAMEPLAN.md` in `robertbradley-oss/clean-handoff` as durable project context. Keep `.gameplan/` evidence and private/local artifacts outside the public repository by default.
- 2026-07-23 — Close the Skills-repository publication after PR #2, exact-head and merged-main three-OS CI, fresh-clone validation, canonical/imported/installed manifest equality, protected-state proof, and exact task-temp cleanup. Keep `robertbradley-oss/clean-handoff` as sole implementation authority and the umbrella repository as distribution only.
- 2026-07-23 — Approve the exact Skills-repository local-validation cache amendment: remove only the failed task-owned cache, rerun the complete local gate with ordinary Post Clean compilation, remove only its generated task-owned bytecode cache before boundary inspection, and otherwise preserve the approved product, validation, and external-mutation boundary unchanged.
- 2026-07-23 — Approve the exact Skills-repository publication slice after direct review reconfirmed both locked repository heads, the canonical 15-file package, the absent publication branch and pull request, and the retained installed boundary. Publish only a byte-identical umbrella distribution through one branch, commit, ready pull request, three-OS CI gate, merge, and fresh-clone verification; preserve canonical Clean Handoff as read-only authority.
- 2026-07-22 — Close the retained-repository deletion after both histories and all eleven assets were immediately re-proven, each exact target deletion ran once in the approved order, both API names became absent, canonical/CI/installed/recovery/unrelated state remained exact, task temp was removed through an exact dry run, and the fourteen-source footprint was finalized.
- 2026-07-22 — Clear the deletion-authentication blocker after the user completed interactive authorization and direct status inspection proved active account `robertbradley-oss` now has `delete_repo` plus its prior scopes. Resume only the unchanged recovery-first sequence; no deletion has yet run.
- 2026-07-22 — Stop before recovery restoration or deletion after the one approved GitHub scope-refresh attempt timed out at 304 seconds and a direct status recheck still showed no `delete_repo`. Honor the no-retry rule; preserve both targets and all protected state until the user completes interactive authorization or separately approves another attempt.
- 2026-07-22 — Approve the exact deletion-authentication amendment: run one `gh auth refresh --hostname github.com --scopes delete_repo` for the active `robertbradley-oss` account, permit user OAuth confirmation, verify the account and scope, and otherwise leave the approved recovery, deletion order, protections, and no-retry boundary unchanged.
- 2026-07-22 — Stop the approved retained-repository deletion before restoration or deletion because `gh auth status` shows no `delete_repo` scope and the installed CLI confirms that scope is mandatory. Propose one exact `gh auth refresh --hostname github.com --scopes delete_repo` amendment; do not broaden authentication or run either deletion command before approval.
- 2026-07-22 — Approve the exact retained-repository deletion slice: immediately re-prove both recovery histories and all legacy assets, delete only `clean-handoff-source` and then `clean-handoff-legacy` exactly once each, preserve canonical `clean-handoff`, the installed skill, external recovery, and all unrelated state, and stop without retry on drift or partial failure.
- 2026-07-22 — Accept “delete them then” as explicit approval in principle to remove both retained GitHub repositories. Because exact recovery commands, deletion order, partial-failure behavior, workspace evidence paths, and closure criteria were inferred, record one complete destructive-action proposal and require exact approval before either deletion command runs.
- 2026-07-22 — Close the recovery and public cutover after exact blob/LF proof, passing run `29973554084`, fresh-clone and installed-byte validation, final repository identity/inventory checks, one supported marketplace removal, recovery-manifest revalidation, and scoped task-temporary cleanup. Retain `clean-handoff-legacy`, `clean-handoff-source`, and the external recovery directory; no material deletion is approved.
- 2026-07-22 — Approve the exact proposed source-blob identity correction: replace only the PowerShell-transformed `.gitattributes` hash with repository-native blob `dcb9ec8aa947092e514dc24e055e88bb3bca38dc`; preserve every other approved amendment field unchanged.
- 2026-07-22 — Stop the approved line-ending amendment at preflight because the recorded `.gitattributes` blob ID was calculated from a PowerShell-transformed display stream. Repository-native Git proves the exact source blob is `dcb9ec8aa947092e514dc24e055e88bb3bca38dc`; propose only that identity correction and make no candidate or external mutation before approval.
- 2026-07-22 — Approve the exact proposed public-cutover line-ending amendment: add only the source `.gitattributes`, create and normally push one corrective hold-repository commit, require local/default-Windows/fresh-clone and six-cell CI evidence, then resume the two success-path renames and original marketplace-removal/closure sequence only if every amended gate passes.
- 2026-07-22 — Keep the recovery-and-public-cutover slice active after public CI run `29973033936`: macOS and Ubuntu pass at Node 22/24, while both Windows cells expose that the clean export omitted the source `.gitattributes` and therefore checked out `SKILL.md` as CRLF. Complete the approved rollback, retain the candidate under `clean-handoff-standalone-hold`, leave the marketplace configured, and propose only a one-file line-ending amendment.
- 2026-07-22 — Approve the exact proposed recovery-and-public-cutover slice, including the external recovery directory, both history bundles, legacy rename, clean public repository and initial push, repository metadata, CI and fresh-clone validation, one supported marketplace removal, bounded rollback renames, and explicit prohibition on deleting either old repository.
- 2026-07-22 — Accept “alright lets do it” as approval in principle for a clean standalone publication, not as exact approval of inferred external paths and mutations. Propose one complete recovery-and-public-cutover slice; preserve both old repositories and require a later material approval for deletion.
- 2026-07-22 — Close public standalone preparation after exact private commit `7afaf864a990b6839a49c213d520b7adac645171`, six-cell CI, two identical 20-file candidates, complete restored validation, manifest equality, temp cleanup, and unchanged public repository state; leave recovery/cutover and deletion unapproved.
- 2026-07-22 — Approve the exact public-standalone-preparation slice: adopt the README/test reconciliation and conditional CI behavior in one private commit, prove six-cell CI and two reproducible standalone-only candidates, inventory legacy-public recovery inputs, and make no public-repository mutation.
- 2026-07-22 — Accept public standalone publication and retirement/removal of the current plugin-era `robertbradley-oss/clean-handoff` repository in principle. Preserve its recoverable history and release assets, prove the replacement first, and require separate exact approvals for preparation, recovery/cutover, and final deletion.
- 2026-07-22 — Close the legacy-plugin-uninstall slice after the supported one-time removal and all six direct validations pass; retain the configured marketplace and recovery command, preserve the exact standalone skill, and return execution authority to `None approved`.
- 2026-07-22 — Approve the exact legacy-plugin-uninstall slice: remove only `clean-handoff@clean-handoff` through Codex's supported command exactly once, preserve the standalone `$clean-handoff` skill and configured marketplace, and require direct before/after evidence before closure.
- 2026-07-22 — Accept removal of the visible legacy `Handoff` entry in principle. Propose one supported, recoverable plugin uninstall while preserving the standalone user skill, configured marketplace, repository source, archives, and all unrelated Codex state; require exact approval before mutation.
- 2026-07-22 — Close the post-closure repository reconciliation after the README and exact legacy inventory expectation align with the completed standalone product, every approved validation passes, provenance is finalized, and the working skill remains unchanged.
- 2026-07-22 — Approve the exact post-closure repository-reconciliation slice: update only the stale root README and legacy inventory test plus their GamePlan evidence records, while keeping the working skill, runtime, packaging, CI, installation, generated artifacts, and history unchanged.
- 2026-07-22 — Accept the user's approval of a small README-and-test follow-up as approval in principle. Propose one exact post-closure repository-reconciliation slice, keep the completed lettered phases closed, and require exact approval of the inferred validation and provenance boundary before changing either requested file.
- 2026-07-22 — Close Phase G and this GamePlan after all 12 criteria pass: retain the verified standalone installation and private validation branch, finalize provenance, remove only task-owned temporary evidence, and make no release or publication claim.
- 2026-07-22 — Approve the exact proposed Phase G archive-normalization amendment: replace only the two task-owned ZIPs/restores using conversion-disabled `git archive`, prove byte-level equality with the committed package, and rerun the complete restored-package gate without product or history changes.
- 2026-07-22 — Keep Phase G active after the first restored-package gate: the approved test-only amendment and six-cell CI pass, but plain `git archive` under Windows `core.autocrlf=true` converts LF to CRLF and breaks byte equivalence plus one restored metadata assertion. Propose only a command-level archive-normalization amendment; do not change product code, install, or create a task.
- 2026-07-22 — Approve the exact proposed Phase G validation-only amendment: canonicalize only the filesystem test fixture root, run the recorded focused/full validations, commit and push only that test file, and require all six CI jobs to pass before resuming Phase G.
- 2026-07-22 — Keep Phase G active after private CI run `29964533031`: both Ubuntu jobs pass, while both macOS and both Windows jobs expose the same lexical-temp-versus-realpath test-fixture defect. Propose one test-only canonicalization amendment and do not edit the read-only package without explicit approval.
- 2026-07-22 — Approve the exact proposed Phase G full-validation-and-closure slice, including its bounded workspace writes, private validation branch/commit/push, fresh user-skill installation and rollback, exactly one live validation task, exact commands, and explicit prohibitions.
- 2026-07-22 — Accept the user's approval to proceed to Phase G as approval in principle only. Record one complete exact validation-and-closure proposal, but require explicit approval of its newly inferred workspace paths, private validation commit/push, user-skill installation and rollback, single live validation task, commands, and completion criteria before execution.
- 2026-07-21 — Close Phase F after F-MA-01 verified all 26 archive inputs, restore-tested the checksummed archive, removed only the 25 approved inactive paths, retained the validated 15-file Direct/Portable package, finalized both footprints, and left Phase G unapproved.
- 2026-07-21 — Approve the exact Phase F material-action amendment F-MA-01: archive and directly restore-validate the 25 inactive Phase D paths plus the recovery test baseline before deleting only those 25 paths; retain every other product, generated, installed, operational, and historical surface.
- 2026-07-21 — Approve the exact Phase F second validation-only amendment: replace only the still-failing reconciliation command with the recorded PowerShell-safe form; preserve every other field and prohibition, and keep F-MA-01 unapproved.
- 2026-07-21 — Approve the exact Phase F validation-only amendment: reuse the named legacy-inventory transition skip and replace only the PowerShell-unsafe reconciliation command; all other scope, criteria, commands, and prohibitions remain unchanged, and F-MA-01 remains unapproved.
- 2026-07-21 — Approve the exact proposed Phase F manifest-and-proof slice; authorize only the GamePlan, one evidence report, the Phase F footprint, and the compiled footprint, while withholding every cleanup, build, installation, migration, cache, release, publication, commit, push, and task-creation action.
- 2026-07-21 — Close Phase E after all nine completion criteria and every exact validation passed; retain only Direct and Portable Handoff in the active product, preserve broader Phase D surfaces for Phase F, finalize the footprint, and leave Phase F unapproved.
- 2026-07-21 — Approve the exact proposed Phase E execution slice: simplify the active standalone skill to Direct and Portable Handoff, prove both locally, preserve displaced files, create the Phase F disposition register, and authorize no deletion, installation, live task creation, migration, release, or publication.
- 2026-07-21 — Revise Phase E to retain only Direct Handoff and Portable Handoff as active workflows, prove both directly, disconnect broader Phase D machinery without deleting it, and record every displaced surface for explicit retention or cleanup approval in Phase F.
- 2026-07-21 — At the user's direction, pause Phase E and revise the product around a minimal handoff workflow: one Direct Handoff, one Portable fallback, exactly one task-creation call, destination-side live inspection, and no custom persistent transfer protocol by default. This supersedes six-workflow parity and the v2 receipt/packet/finalization family as required end-state behavior while preserving Phase D as evidence and a safe simplification baseline.
- 2026-07-21 — Superseded by the minimal-handoff strategic reset: narrow the former Phase E hardening proposal to direct safety-critical gaps, one minimal CI addition, concise evidence, and one final regression cycle.
- 2026-07-21 — Close Phase D after all eight construction criteria and every exact validation passed; finalize its footprint, retain the platform link-creation capability skip as an explicit Phase E/G risk, and leave Phase E unapproved.
- 2026-07-21 — Approve the exact Phase D complete standalone construction slice as one lettered-phase execution boundary; later hardening, installation, migration, cleanup, live demonstrations, and release work remain deferred to Phases E-G.
- 2026-07-21 — Close the Phase D checkpoint slice after all nine checkpoint-domain and transaction criteria and every exact validation passed; checkpoint is the only operational construction-stage command and the live-GamePlan-authority slice remains unapproved.
- 2026-07-21 — Approve the exact proposed Phase D checkpoint-domain and transaction slice; keep all other workflows, GamePlan authority, transfers, installation, legacy migration, and root-product changes deferred.
- 2026-07-21 — Close the Phase D standalone-foundation slice after all nine twice-amended criteria and every exact approved validation passed; preserve official-validator and package-surfacing obligations for Phase G and leave the checkpoint slice unapproved.
- 2026-07-21 — Approve the exact second Phase D standalone-foundation transition-validation amendment: skip only the named legacy single-skill source-inventory assertion, require every other root test and gate, forbid legacy plugin build/install/reload/distribution, and require Phase G package-surfacing evidence.
- 2026-07-21 — The first Phase D standalone-foundation validation amendment successfully runs the root suite; 62 of 63 tests pass, and the sole failure identifies the locked standalone path's coexistence with the legacy plugin's whole-`skills/` discovery root. Keep the foundation slice active and do not waive or repair this boundary without separate approval.
- 2026-07-21 — Approve the exact Phase D standalone-foundation validation-only amendment: accept its passing focused metadata boundary test, defer an actual bundled official-validator pass to Phase G, and run the unchanged root suite through `npm.cmd test`; leave every other objective, boundary, criterion, and command unchanged.
- 2026-07-21 — Approve the exact proposed Phase D standalone-foundation slice; checkpoint, transfer, GamePlan-authority, routing, legacy, installation, and existing root-product changes remain outside its boundary.
- 2026-07-21 — Use letters only for phase names. Treat the completed foundation and checkpoint boundaries as historical milestones within Phase D, not numbered phases; complete the remaining Phase D scope under one lettered-phase execution boundary before advancing to Phase E.
- 2026-07-21 — Close Phase C after all eight architecture criteria and both runs of every exact approved validation passed; leave Phase D unapproved.
- 2026-07-21 — Consume only live root `GAMEPLAN.md` through one strict read-only adapter; snapshots, digests, packets, capsules, receipts, checkpoints, and summaries remain inert evidence and never transfer approval.
- 2026-07-21 — Replace active transfer contracts with one v2 family, retain checkpoint Markdown v1 and Git-common storage layout v2, and isolate v0.8 transfers behind a read-only legacy reader with no silent migration.
- 2026-07-21 — Remove every active Clean Handoff ScopeLock call, field, digest, gate, and compatibility authority while leaving ScopeLock and retained historical evidence unchanged.
- 2026-07-21 — Decompose the monolith by canonical ownership and test seams, but keep checkpoint and transfer transaction ordering cohesive and reject size-driven or one-command-per-file splits.
- 2026-07-21 — Use platform-owned live effective-effort metadata with exact supported-value equality; explicit user selection recovers source setup only, and absent destination evidence stops at `confirmation-required/effort-unavailable`.
- 2026-07-21 — Approve the exact Phase C Authority, Data, Compatibility, and Module Architecture slice with documentation-only writes and no construction authority.
- 2026-07-21 — Close Phase B after all seven completion criteria and every exact approved validation passed; leave Phase C unapproved.
- 2026-07-20 — The user explicitly approved revising the locked Outcome from `/clean-handoff` to `$clean-handoff`, aligning strategic identity with direct installed-client evidence.
- 2026-07-20 — Direct installed-client evidence establishes `$clean-handoff` as the standalone invocation; `/clean-handoff` selects the slash-command surface and cannot remain the invocation target.
- 2026-07-20 — Use standalone identity `clean-handoff`, display name `Clean Handoff`, explicit implicit-invocation policy, and no standalone `$handoff` alias or plugin namespace.
- 2026-07-20 — Support non-Git repositories only through Portable Handoff; all saved-project checkpoint, inspection, and direct-transfer workflows require verified Git identity.
- 2026-07-20 — Require Node.js 22+ and Git 2.45+ for the standalone runtime, preserve exact supported reasoning effort or stop, and defer release support claims to direct Windows, macOS, and Linux validation.
- 2026-07-20 — Approve the exact Phase B Product and Invocation Contract slice for read-only investigation and writes limited to the GamePlan, one evidence report, and one Task Footprint.
- 2026-07-20 — Accept the Phase A evidence audit and its verdict that Clean Handoff should become a self-contained standalone skill while ScopeLock remains an independent plugin product.
- 2026-07-20 — Treat installed caches, personal plugin copies, generated distributions, staging trees, and sideband evidence as consumers or recovery surfaces, never alternate source authority.
- 2026-07-20 — Require a deterministic Clean Handoff distribution builder or equivalent tagged recovery proof before `.release-staging/` can become a cleanup candidate.
- 2026-07-20 — In Phase C, evaluate cohesive contract, repository, storage, checkpoint, transfer, GamePlan-authority, and CLI boundaries while retaining one canonical rule owner and black-box transaction coverage.
- 2026-07-20 — Build a standalone `clean-handoff` skill.
- 2026-07-20 — Use evidence-led reuse rather than blind conversion or clean-sheet replacement.
- 2026-07-20 — Keep GamePlan as the sole strategy and execution authority.
- 2026-07-20 — Remove ScopeLock from Clean Handoff runtime without modifying ScopeLock.
- 2026-07-20 — Adopt repository diet based on canonical behavior, cohesion, reproducibility, and evidence, not arbitrary size targets.
- 2026-07-20 — Quantify Clean Handoff and ScopeLock separately so ownership and evidence remain attributable.
- 2026-07-20 — Evaluate monolith decomposition only where maintainability or test isolation improves without weakening safety.
- 2026-07-20 — Require explicit approval before material deletion, relocation, compression, or archival.
- 2026-07-20 — Organize and approve work phase by phase under exact execution slices.
- 2026-07-20 — Lock this strategic GamePlan with no execution slice approved.

### Historical v0.8 decisions — retained but superseded as governing strategy

- 2026-07-18 — Treat the projectless v0.7.0 run as the primary redesign case and make its acceptance cases release-blocking.
- 2026-07-18 — Separate exhaustive Checkpoint from concise Quick Handoff so a quick transfer does not automatically incur checkpoint cost.
- 2026-07-18 — Use the resolved Git common directory as the initial Git sideband provider because outside-worktree storage is structurally safer than ignore rules.
- 2026-07-18 — Keep legacy `.codex-handoff/` evidence readable while prohibiting automatic v0.8 writes to project source.
- 2026-07-18 — Preserve authorization only from a structured live-user-request capsule; stored evidence can never manufacture authorization.
- 2026-07-18 — Use a short-lived helper-issued receipt to bind preflight evidence to preparation across the local, non-adversarial helper boundary.
- 2026-07-18 — Perform releases from this source repository and never from the installed plugin cache.
- 2026-07-18 — Keep AgentReceipt work in its own project.
- 2026-07-18 — Adopt the former file as the canonical Clean Handoff v0.8 game plan, with completion status based only on repository and test evidence.
- 2026-07-18 — Implement the authoritative preflight coordinator as a policy-helper evidence gate followed by exactly one zero-write `transfer-preflight` call; stop the current workflow slice at the verified receipt.
- 2026-07-18 — Derive the repository-state token inside the packaged transfer helper from its coherent snapshot so caller-authored evidence cannot manufacture repository authority.
- 2026-07-18 — Close the completed preflight ScopeLock after its seven-file boundary and all four approved validation commands passed.
- 2026-07-18 — Require `prepare-transfer` to reproduce the receipt's repository-state token before storage mutation and retain that opaque token in every validated packet.
- 2026-07-18 — Close the transactional-preparation ScopeLock after its three-file boundary, focused 14-test suite, complete 33-test suite, syntax check, and diff check passed.
- 2026-07-18 — Resolve prepared evidence explicitly after destination-task creation fails: retain must be verification-only, while discard must revalidate the exact receipt and packet identity, delete no directory, and remove only the verified packet.
- 2026-07-18 — Finalize only from a direct live `create_thread` result: preserve the prepared packet, publish one immutable sibling receipt, bind the transfer to the exact destination thread and host, and record authorization as `not-evaluated`.
- 2026-07-18 — Cap the compact Quick Handoff prompt at 8 KiB so transfer size is deterministic and testable while detailed evidence remains local.
- 2026-07-18 — Render the destination prompt only after identity-safe revalidation of one exact prepared packet; expose source authorization as context while leaving destination authorization `not-evaluated`.
- 2026-07-18 — Route source-side Quick Handoff through one preparation, one render, and exactly one `create_thread` call; finalize only direct thread-and-host authority, treat queued creation as pending, and retain failed evidence by default with discard only after explicit approval.
- 2026-07-18 — Make destination authorization evaluation a packaged read-only `verify-transfer` operation; every mismatch returns bounded `confirmation-required` evidence without mutation or raw authority disclosure.
- 2026-07-19 — Bridge the compact prompt to destination verification with exactly one canonical base64url capsule containing the exact prepared-transfer result; pass it unchanged to one `verify-transfer` call before mutation.
- 2026-07-19 — Treat packaged Checkpoint publication and shared ScopeLock reserved-sideband classification as v0.8 release blockers while deferring non-Git Quick Handoff, a Codex-managed provider, and fully automated live task-tool simulation.
- 2026-07-19 — Complete shared sideband compatibility by accepting only packaged `scopelock/context/v2` evidence with the exact reserved-sideband classification and fail closed for incompatible evidence.
- 2026-07-19 — Close reserved-sideband integration Lock `2026-07-19T062352Z` with evidence retained and require a fresh boundary before Checkpoint implementation.
- 2026-07-19 — Publish Checkpoint only through the exact saved project's verified Git-common-directory namespace and use project-local `.codex-handoff/` only as a read-only fallback.
- 2026-07-19 — Close packaged Checkpoint Lock `2026-07-19T165251Z` after approved validation and require a new boundary for documentation and metadata reconciliation.
- 2026-07-19 — Pause ScopeLock as the Clean Handoff development-management mechanism while retaining prior evidence and packaged runtime compatibility for v0.8.
- 2026-07-19 — Separate canonical private source from public distribution and never merge or force-push their unrelated histories.
- 2026-07-19 — Make release validation reproducible with pinned PyYAML, GitHub Actions, and official validator sources.
- 2026-07-19 — Treat installed ScopeLock `context/v1` as an environment mismatch rather than permission to weaken the v2 contract.
- 2026-07-19 — Correct the assumption that ScopeLock canonical source already supplied v2; require an explicit source, version, build, and install lifecycle.
- 2026-07-19 — Accept the validated ScopeLock v2 source phase and the exact local 0.2.0 lifecycle required for Clean Handoff release testing, while withholding push, tag, and publication authority.
- 2026-07-19 — Accept ScopeLock commit `faa87b1` and its validated local package while requiring supported reinstall before treating the runtime blocker as resolved.
- 2026-07-19 — Complete the supported Windows live Quick Handoff gate with installed-byte verification, one proceed destination, one drift confirmation destination, and ScopeLock inactive for development management.
- 2026-07-19 — Correct the final v0.8 product boundary to 26 paths, isolate it on a candidate branch, and keep GamePlan, readiness, sideband, staging, ScopeLock documentation, commit, push, tag, and publication outside that authorization.
- 2026-07-20 — Treat private CI run `29714928886` as real evidence, reject platform waivers, and repair only the canonical temp-root fixture and non-authoritative Windows `fsutil` path.
- 2026-07-20 — Accept private CI run `29787051070` at candidate `26e06c5` as completion of the cross-platform source gate while withholding public main, tag, release, and publication.
- 2026-07-20 — Preserve public candidate `3f74015` but reject publication after fresh-task testing exposed a missing packaged v0.8 contract.
- 2026-07-20 — Accept public follow-up `868dc3f` as the packaging correction but reject publication after fresh-task testing exposed project-list envelope incompatibility.
- 2026-07-20 — Accept the three-file project-list correction that preserves direct arrays, recognizes only the exact schema-v1 envelope, and fails closed for malformed or oversized shapes; the later commit at current HEAD supersedes its former unstaged status.

## Refresh Triggers

- A plugin-only capability proves indispensable.
- Codex cannot expose an acceptable standalone invocation.
- GamePlan cannot be consumed safely without competing authority.
- A legacy consumer prevents ScopeLock removal or cleanup.
- Generated distributions cannot be reproduced.
- Module extraction would duplicate or weaken safety-critical behavior.
- Historical evidence cannot be archived and restored safely.
- A demonstrated user need or platform gap requires durable checkpoint, recovery, or transfer state in the core product.
- Built-in Codex project or task capabilities cannot support the minimal direct handoff safely.
- Supported runtime or packaging requirements materially change.
- A phase completion claim loses direct evidence.
- User approval changes Outcome, Strategy, Guardrails, phase order, or an execution boundary.

## Last Refreshed

2026-07-24 — The user approved publishing the canonical root `GAMEPLAN.md` in the public Clean Handoff repository while retaining `.gameplan/` evidence and private/local artifacts outside the repository. No execution slice is approved.
