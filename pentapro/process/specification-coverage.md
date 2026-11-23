# PentaPRO specification coverage

The Android questionnaire and release contracts are consolidated in their owning pillars. Archived change records remain historical snapshots; this coverage record does not establish new runtime evidence or release acceptance.

| Source | SHA-256 | Canonical owner |
| --- | --- | --- |
| `../changes/archive/2026-11-08-castas-native-android/specs/affective-polarization-test/spec.md` | `32f6b2d1896105a018b5d5aa11b5f98dda6b310a71861861ac61f010376f2269` | [../product/features.md](../product/features.md) |
| `../changes/archive/2026-11-08-prepare-android-play-release/specs/android-release-readiness/spec.md` | `9c031c5494682fb8ed485655c8aca30ef4ce53f0f9eaed08572026280c3a0cbd` | [../production/environments.md](../production/environments.md) |

## Requirement and scenario mapping

- **affective-polarization-test / Native Android experience** → [../product/features.md](../product/features.md); scenarios: Open the application.
- **affective-polarization-test / Home and information screens** → [../product/features.md](../product/features.md); scenarios: Navigate to an informational screen.
- **affective-polarization-test / Supported languages** → [../product/features.md](../product/features.md); scenarios: Change the application language.
- **affective-polarization-test / Questionnaire flow** → [../product/features.md](../product/features.md); scenarios: Answer and advance, Restart an incomplete test, Recreate the activity during a test, Process is recreated during a test, Complete the final question.
- **affective-polarization-test / Result calculation and persistence** → [../product/features.md](../product/features.md); scenarios: Reopen a completed result, A completed result cannot be written, Storage cannot be read, No completed result exists.
- **affective-polarization-test / Result visualization and emoji selection** → [../product/features.md](../product/features.md); scenarios: Choose a positive emoji.
- **affective-polarization-test / Share a result** → [../product/features.md](../product/features.md); scenarios: Copy the result.
- **affective-polarization-test / Adaptive and accessible interface** → [../product/features.md](../product/features.md); scenarios: Use a narrow screen or enlarged text, Navigate with an accessibility service.
- **affective-polarization-test / Local-only test data** → [../product/features.md](../product/features.md); scenarios: Abandon a questionnaire, Complete a questionnaire.
- **android-release-readiness / Android API support** → [../production/environments.md](../production/environments.md); scenarios: Verify the release SDK range.
- **android-release-readiness / Reproducible candidate packaging** → [../production/environments.md](../production/environments.md); scenarios: Build a local release candidate, Inspect packaging and data exposure.

## Five-pillar review

- PRODUCT: Android requirements and scenarios in features; project purpose and UI owner linked. Web-specific requirements are not invented.
- PROJECT: current architecture/security description linked; other topic scaffolds remain Pending.
- PRODUCTION: Android API/package requirements and scenarios included; operational handoff migrated. Physical device, signing and asset rights remain pending where recorded.
- PROOF: historical verification and limits migrated, not rerun. Toolchain discrepancy remains explicit.
- PROCESS: native PentaPRO change workflow, preserved archived records, and pending reconciliations.

## Duplicates and provenance

Consolidated requirements appear once as the current canonical contract. Archived change deltas remain historical snapshots, not competing current specifications. Five existing `docs/` pillar records were moved into the corresponding PentaPRO owners; the original paths remain short navigation redirects. Specialist UI, legal and audit records remain linked as supporting sources. Original archive metadata is preserved with the archived change records. The active workflow and its constraints are recorded in PentaPRO and repository instructions.


Verification before removal: all 9 Android feature requirements and 18 scenarios, plus 2 release requirements and 3 scenarios, match the source headings in order; the full requirement/scenario bodies were transferred. Historical archive destinations were byte-compared to their deleted Git counterparts, and missing metadata was recovered from HEAD. No application tests were run for this documentation migration.


Post-removal validation: exact source requirements/scenario bodies were compared before deletion; archive source bytes were checked against Git HEAD; `git diff --check` passed. Changed-Markdown relative target scan found one pre-existing unrelated `README.md` link to `.etc/LICENSE` missing; active Markdown links resolve to the maintained PentaPRO records. No Android or web application tests were run. A separate review remains appropriate for all five pillars and the historical toolchain discrepancy.

The unrelated pre-existing README license target was corrected to the existing root LICENSE during final documentation validation; this changes navigation only, not licensing terms.
