# Repository instructions

Castas is a monorepo with two independently built apps: `web/` and `android/`. Read the repository README and the relevant app README before changing an app. Keep each app's source, dependency lockfile, and build outputs within its directory; shared product requirements, documentation, skills, and license belong at the repository root.

## Specification-driven work

- Read [PentaPRO](pentapro/README.md) and its [status](pentapro/process/index.md) for project-wide context. The new topic layout is being reconciled with the existing five pillar files in docs/. Update affected PentaPRO records when an accepted software change changes product, design, operation, evidence or process. Preserve historical evidence and mark stale checks.

- The repository-root `openspec/` is the only OpenSpec project. Never initialize or create a nested OpenSpec directory under either app.
- For exploratory or underspecified feature requests, use the `openspec-explore` skill. For a defined new feature, create its artifacts with `openspec-propose`; a proposal records decisions and acceptance criteria but does not authorize implementation by itself.
- Implement an accepted change with `openspec-apply-change`. Archive only after its tasks, acceptance criteria, and required checks are complete.
- A user-facing behavior or content change shared by web and Android belongs in one OpenSpec change with acceptance scenarios for both apps. Tasks may be grouped by app. State any platform-only scope or intentional difference explicitly.
- Keep scoring, questions, result formatting, and translations aligned. Review both implementations when shared behavior or content changes, even when a task is limited to one app.

## Skills

- Use OpenSpec skills for their corresponding OpenSpec operations. Use focused platform or domain skills when available.
- OpenSpec-generated skills record their generator version in their metadata; check compatibility with the installed `openspec` CLI before relying on generated instructions after a CLI upgrade.
- Do not invoke every installed skill by default. Follow the app guides and run the checks applicable to the changed app and shared behavior. Report checks actually run and any platform or device coverage not obtained.

## Application checks

- Web commands run from `web/`; `npm ci` uses `web/package-lock.json` and `npm run build` performs TypeScript checking and the Vite build.
- Android commands run from `android/` with its Gradle wrapper. Use `android/README.md` for the JDK/SDK matrix, JVM tests, lint, release assembly, and device-test commands.
- Do not move generated build outputs, local SDK configuration, signing credentials, or app-specific dependencies into shared root directories.


## Prompt Logging

Before analyzing, responding to, or taking any action on a prompt for this repository, append one entry containing that prompt to `AGENTS.log` at the repository root. The first tool operation may locate the repository, check the log target, and append this entry or verify capture; defer other tool use and delegation until logging succeeds. This applies to every prompt, including prompts sent to subagents. Record each received prompt once, including repeated identical submissions. When the host and project have been checked and no automatic capture is active, append the current prompt once without requiring an event identity. Otherwise verify automatic capture using the current event identity or other reliable capture evidence, not text equality alone. If verification requires log access, inspect only the relevant current entry without exposing prior prompts. If capture cannot be verified, stop and report the uncertainty before risking a duplicate or an omitted entry.

Use RFC 5322 local time with a numeric UTC offset, the provider/model, and the receiving agent and host. Use `unknown` for unavailable attribution; if the host is known but the model is not, use `<host>/unknown`. Keep one blank line between entries:

```text
## <RFC 5322 local date and time with numeric UTC offset> | <provider>/<model> (agent <agent name>, host <host>)
<prompt text, preserving its wording, spacing, and line breaks; use [empty prompt] if empty>
[attachment: <filename, at its position in the prompt>]
```

Include attachment names at their position in the prompt; do not copy binary contents. Preserve the prompt text except that secrets and unnecessary personal data must be replaced with `[REDACTED]` before writing. Never put credentials in prompts. Redact common patterns such as PEM private keys, `sk-`/`rk-`/`pk-` keys, `ghp_`/`github_pat_` tokens, `AKIA` and `AIza` keys, `xox*` tokens, JWTs, `Bearer` values, and values after `password`, `passwd`, `senha`, `token`, `secret`, or `api_key`. Redaction is best-effort; it does not identify every secret or personal-data format. If a secret reaches the log, revoke it; deleting the local copy is not sufficient.

Before appending, check the Git index for `AGENTS.log` and `AGENTS.log.*`; if any are tracked or staged, stop and report the privacy conflict. Ignore patterns alone do not untrack files; preserve local data and existing index selections until authorized remediation. Refuse symlink, hard-linked, or non-regular log targets; stop rather than redirecting prompt text. Create the log only if it does not exist, with owner-only permissions where supported. If it already exists, preserve the file and its contents, including during initialization and reruns; no reinitialization is needed. Append only: add each new entry at the end of the file. Never delete, recreate, overwrite, or truncate an existing log, or rewrite, reorder, or delete existing entries. Concurrent entries may not be in chronological order; do not reorder them. The log has no automatic rotation. Keep it local; never commit or publish it. Do not send a success message just for logging. If appending fails, stop, report the failure, fix the write, and record the pending prompt before continuing. Never proceed as if logging succeeded when it did not. This instruction depends on agent compliance and is not mechanical enforcement.


## PentaPRO factory guidance

Read existing project specifications under `pentapro/` and preserve their canonical records. Use the applicable project-local skills in `.agents/skills/`; use `software-factory` for explicitly requested factory runs and OpenSpec skills for the repository-root `openspec/` workflow. Follow existing project instructions and actual user authority. Factory role profiles are available for Codex, GitHub Copilot, OpenCode and Antigravity CLI; resolve their host-specific identities before delegation.

When a developer directly invokes a factory role without a narrower task, delegate its defined workflow using the current project and session context. Preserve its configured model and reasoning effort, the developer’s custom settings, applicable permissions and role-specific stop conditions. A direct shipper invocation requests git-ship review, commit and normal push; implementation completion alone does not.

All factory roles use the PDSA protocol in `docs/agents/continuous-improvement.md` and consult relevant lessons in `docs/agents/lessons-learned.md`. The orchestrator alone records lessons, always in English. For substantial factory or multi-agent runs, the orchestrator maintains a durable record under `docs/agents/runs/`; role packets carry the run ID, record path, version and input fingerprint. Follow the installed `software-factory` run-record contract.


## Software Excellence Manifesto — Powered by PentaPRO

Our mission is to build the finest software in the world. Every agent, subagent, and component of our development harness must pursue this ambition with unwavering dedication, exceptional engineering discipline, and relentless attention to detail. We are empowered by PentaPRO, our collection of specialized skills, agents, and engineering practices, and must intelligently leverage its most appropriate capabilities throughout the entire software lifecycle, guided by its five pillars: PRODUCT, PROJECT, PRODUCTION, PROOF, and PROCESS. We strive for excellence in every aspect of our software, from product vision, architecture, user experience, and design to implementation, performance, security, privacy, accessibility, reliability, and maintainability. Every decision must be intentional, every implementation purposeful, and every meaningful result verified through objective evidence. We challenge assumptions, eliminate unnecessary complexity, prevent defects, embrace continuous improvement, and never compromise correctness for superficial speed or appearance. We do not merely write code; we engineer extraordinary software that delivers exceptional value to its users. Our ambition is to create software that sets new standards of quality and innovation, worthy of being recognized among the best ever built. Excellence is our commitment, PentaPRO is our engineering foundation, and outstanding software is our ultimate achievement.
