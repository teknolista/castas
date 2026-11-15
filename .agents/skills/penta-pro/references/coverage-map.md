# Coverage across the five pillars

Use this map to check cross-cutting coverage when creating or revising a specification. Each row identifies where a fact is maintained. A project can split a topic into smaller linked records. Do not add a sixth pillar or duplicate the same requirement in several files.

| Concern | Owning topic and linked evidence |
| --- | --- |
| Problem, users, goals, hypotheses, non-goals and affected non-users | PRODUCT overview; validation of outcomes in PROOF validation. |
| Domain concepts, glossary, entities, invariants and worked examples | PRODUCT domain; data representation in PROJECT architecture. |
| Journeys, feature availability, business rules, permissions and negative constraints | PRODUCT features; implementation guards in PROJECT and checks in PROOF. |
| Screens, navigation, content, visual language, accessibility and localization | PRODUCT experience and linked screen records; files in assets; checks in PROOF. |
| Measurable performance, reliability, compatibility, usability and safety expectations | PRODUCT quality; design tradeoffs in PROJECT, operating thresholds in PRODUCTION and measures in PROOF. |
| Privacy purposes, consent, retention, deletion and ethical constraints | PRODUCT quality; data and threat design in PROJECT security; operating handling in PRODUCTION; checks in PROOF. |
| Threats, authentication, authorization, trust boundaries and residual risk | PROJECT security; observable denial behavior in PRODUCT and effect checks in PROOF. |
| Legal, contractual and licensing applicability | PROJECT delivery and security, with responsible decision owner in PROCESS; do not invent legal conclusions. |
| Architecture, data model, external services, failure contracts and portability | PROJECT architecture and decisions; relevant degradation in PRODUCT and PRODUCTION; contract checks in PROOF. |
| Resources, delivery constraints, cost and dependency exit plans | PROJECT delivery; runtime capacity and costs in PRODUCTION operations. |
| Environments, installation, configuration, secrets and audit signals | PRODUCTION environments and operations; corresponding controls in PROJECT security and PROOF verification. |
| Version compatibility, upgrade, migration, release, rollback, recovery and retirement | PRODUCTION evolution; user-visible guarantees in PRODUCT and rehearsal evidence in PROOF. |
| Acceptance, traceability, representative and adversarial inputs | PROOF traceability and verification, linked to PRODUCT requirement IDs and PROJECT decisions. |
| User research, outcome follow-up and escaped-defect learning | PROOF validation; changed requirements and decisions in their owning pillar; action ownership in PROCESS. |
| Decision history, change control, approvals, agent autonomy, handoffs and resumption | PROCESS change-control, execution and index; solution decisions in PROJECT decisions. |

For each material change, follow its requirement from PRODUCT to the relevant PROJECT and PRODUCTION decisions, planned PROOF checks and PROCESS authority. Record actual results against a revision. Missing information remains Pending with its decision owner and effect on readiness.
