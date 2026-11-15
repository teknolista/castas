# Maintaining the repository-root PentaPRO specification

The five pillars are PRODUCT, PROJECT, PRODUCTION, PROOF, and PROCESS. Create pentapro/ at the Git repository root with scripts/init_pentapro.py. The initializer supplies topic files and assets/, preserves existing files, and marks missing project facts as Pending. Populate applicable topics. Split large topics into linked feature or subsystem records inside their pillar. Use stable IDs and relative links.

| Pillar | Canonical ownership |
| --- | --- |
| product/ | Purpose and scope, domain language and relationships, feature behavior, journeys, screens, accessibility, localization, business permissions, quality and ethical outcomes. |
| project/ | Architecture, contracts, data and integrations, trust boundaries, security and privacy design, dependencies, decisions, delivery constraints and tradeoffs. |
| production/ | Environments, configuration, secrets, distribution, observability, support, capacity and costs, compatibility, migrations, incident response, recovery and retirement. |
| proof/ | Requirement-to-check traceability, test and validation plans, actual revision-bound results, security, privacy, accessibility, performance and recovery evidence, and outcome evaluation. |
| process/ | Specification index, coverage and status, change history, tasks, owners, agent authority, decisions needing human input, reviews, gates and next action. |
| assets/ | Supporting images, icons, styles, diagrams, media and other resources; record source, rights, version and consuming records. |

## Change and OpenSpec ownership

For each change, read process/index.md, affected requirements and decisions, the implementation, and the active OpenSpec change if selected. Compare accepted intent with observed behavior. Record the baseline revision and affected IDs in process/change-control.md. Update canonical topic files and cross-pillar links after the decision is settled. Revisit checks and operating instructions. Preserve historical evidence with its tested revision; mark affected checks stale or pending until rerun. Record unfinished multi-file updates and resume from actual contents. Verify links, IDs, acceptance status and next action.

PentaPRO is the maintained specification and navigation source for the software. OpenSpec is a separate change workflow in repository-root openspec/. Its proposal, design, delta, tasks and archived capability remain versioned there. While a change is active, link its accepted scope and scenarios. After reconciliation or archive, update PentaPRO topic files and retain a pointer to the OpenSpec revision. A validated delta does not prove implementation or deployment. Record which definition is canonical when an active change temporarily differs from the maintained baseline.

A screen contract can live in product/experience.md or linked screen files within product/. Existing docs/ui-design.md may remain the detailed owner during migration. Record its link and status in process/index.md, then move and reconcile it when authorized. Business behavior belongs in PRODUCT, technical implementation in PROJECT, operating effects in PRODUCTION, evidence in PROOF, and authority in PROCESS. Cross-cutting concerns have one owner for each kind of fact, with links across pillars.

## Existing projects and migration

Inventory prior five-pillar files, screen specifications, incoming links and accepted change records. Initialize pentapro/. Move each meaningful record to its owning topic file, preserving IDs, status, provenance, decisions and historical evidence. Rewrite relative links and references from callers. Compare old and new material before declaring migration complete. Keep old paths as short redirects when other links may still use them. Until reconciled, mark which original records remain authoritative in process/index.md. An initialized scaffold alone does not make a complete specification. Existing single-file layouts follow the same inventory and reconciliation.

For a first increment, document observable behavior, negative cases, quality criteria, technical constraints, operating needs, feasible checks and authority. Later scope can remain Pending. Exact recreation requires enough concrete assets, environment and dependency versions, algorithms and data contracts to distinguish plausible implementations, followed by verification of the rebuilt product. Do not promise byte-identical artifacts or identical behavior across unverified environments.

### Example with an accepted OpenSpec change

For an approved change named `tenant-receipts`, PRODUCT points to the `Receipt retries` requirement and affected scenarios in the change delta. PROJECT links the change's design decisions. PRODUCTION records any durable storage or rollout constraints that apply to the project. PROCESS links the accepted change, its task list, acceptance decision, and next pending check. PROOF maps the scenarios to the handler checks, their observed results and the tested snapshot. For example, the conflicting replay scenario needs a 409 response and unchanged job state. If the tests have only been planned, record them as pending even when OpenSpec validates the delta and its planning artifacts are complete.

When resuming, reopen the active change and the latest relevant source. If the accepted scenario or implementation changed after the last check, keep the prior result tied to its snapshot and identify what needs rerunning. Update the owning record when the project accepts a changed decision. After the project synchronizes and archives the change, point ongoing PRODUCT references to the maintained capability spec and retain historical evidence against the tested change. [OpenSpec default schema](https://openspec.dev/docs/schemas/spec-driven)

## Coordinated updates and resumption

1. Read `process/index.md` for current scope, next action, shared status, and any unfinished update. Then inspect the affected pillars and their referenced records. For an existing single-file specification, read its equivalent resume section.
2. Identify the changed canonical records and downstream consequences. A requirement change may affect contracts, verification, tasks, and operating procedures. Update only files whose content or references need to change.
3. Before a material multi-file update, record `In progress` in PROCESS with affected IDs/files and remaining reconciliation. Save changes to the owning records, preserve unrelated edits, and reconcile their references. If concurrent edits are detected, inspect and combine them before writing.
4. Check target files and anchors, cross-file IDs, affected acceptance/check links, evidence applicability, and conflicting statuses. Preserve historical evidence and acceptance scope. Mark changed or unreviewed scope accurately.
5. After successful reconciliation, record the shared revision, change summary, and `Consistent` in PROCESS. Reassess readiness for the affected increment and save the next action. Consistency describes the documents and can coexist with pending questions or unverified software.

File writes may complete only partly. If interrupted, leave a durable record of which files were updated and what remains, and disclose partial saving. Resume by inspecting actual contents before completing the pending update. A partially reconciled set cannot be reported as fully updated or newly accepted. Preserve prior acceptance as history tied to its actual scope and revision.

## Baseline and proposed changes

For a material change to existing software, compare the request with accepted requirements, observed behavior, and related work already in progress. Record the baseline revision or state in PROCESS and link any conflict or overlap that could affect delivery. In PROJECT, summarize the intended additions, modifications, and retirements by canonical PRODUCT ID, with the reason, affected consumers or stored data, and compatibility commitments. Link changes to contracts, planned checks, tasks, and operating procedures in their owning pillars.

Keep a pending proposal separate from active requirements within the same files. Apply settled changes to the owning records, retaining stable IDs where identity remains the same and recording supersessions or retirements. Preserve previous acceptance and evidence with their original scope. If a compatibility commitment is still undecided, record who can resolve it and which work depends on it.
