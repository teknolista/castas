# PROOF · Requirement and source traceability

Scope: accepted Android questionnaire/release contracts and the newly captured web observations. Source/test existence was inspected on 2026-11-23; this matrix is not a new execution result. [Historical verification](verification.md) retains original tested revisions and limits.

| Accepted contract | Source and existing check owner | Evidence or remaining gate |
| --- | --- | --- |
| Native screens, questionnaire and supported languages | [Main source](../../android/app/src/main/java/com/teknolista/castas/), [journey tests](../../android/app/src/androidTest/java/com/teknolista/castas/CastasJourneyTest.kt) | Historical emulator results; new source/toolchain changes require affected checks |
| Scores and emoji thresholds/share formatting | [Domain](../../android/app/src/main/java/com/teknolista/castas/data/CastasDomain.kt), [scoring tests](../../android/app/src/test/java/com/teknolista/castas/data/CastasScoringTest.kt) | Independent boundary vectors exist; not rerun here |
| One accepted answer, cancellation and failed-write recovery | [ViewModel tests](../../android/app/src/test/java/com/teknolista/castas/CastasViewModelTest.kt), including failedWriteKeepsOldResultAndRetriesTheSameCompletedAttempt | Existing source tests, historical verification only |
| Persist completed result/language | [Preferences](../../android/app/src/main/java/com/teknolista/castas/data/CastasPreferences.kt), [reopen test](../../android/app/src/androidTest/java/com/teknolista/castas/CastasPreferencesTest.kt) | Historical device evidence; actual update/backup gates remain separate |
| Adaptive and accessible UI | [Adaptive test](../../android/app/src/androidTest/java/com/teknolista/castas/CastasAdaptiveTest.kt), [journey tests](../../android/app/src/androidTest/java/com/teknolista/castas/CastasJourneyTest.kt) | Automated layout evidence is not human assistive-technology acceptance |
| API support and reproducible packaging | [Release contract](../production/environments.md), [current Android guide](../../android/README.md), [CI configuration](../../.github/workflows/android.yml) | CI config covers API 36; minimum API 26 and release/device gates retain their recorded scope |
| WEB-OBS-01–05 | [Web draft PRODUCT](../changes/document-web-baseline/product.md), [planned web checks](../changes/document-web-baseline/proof.md) | Source observations only; no new web behavior-test evidence |

The accepted requirements and scenarios remain owned by [Android features](../product/features.md) and [release environments](../production/environments.md). Web recovery differs from Android and requires a product decision; source similarity does not establish parity. Physical-device, signing, asset-rights and store gates remain Pending where documented.
