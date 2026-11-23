# PRODUCT · Observed web baseline

Source inspection on 2026-11-23; these observations are not newly accepted requirements or runtime evidence. Existing Android requirements stay in [features](../../product/features.md).

| Observation ID | Current source behavior | Source |
| --- | --- | --- |
| WEB-OBS-01 | Home, test, result, about, political-fanatic, terms and privacy routes; unknown routes return home | [App](../../../web/src/App.tsx) |
| WEB-OBS-02 | 40 questions, five groups of eight, four answer choices; unfinished answers are component memory and a new mounted test starts from the beginning | [Test page](../../../web/src/pages/Test.tsx), [question data](../../../web/src/data/questions.ts) |
| WEB-OBS-03 | Each group scores round(sum of 3/2/1/0 response points divided by 24 times 100); emoji thresholds are 0, 1–24, 25–50, 51–74, 75–99 and 100 | [Scoring](../../../web/src/utils/scoring.ts) |
| WEB-OBS-04 | Completed scores and timestamp use browser localStorage key castas_struct; Result loads that value; no result shows a start-test path | [Test](../../../web/src/pages/Test.tsx), [Result](../../../web/src/pages/Result.tsx) |
| WEB-OBS-05 | A positive emoji can be selected; clipboard success sets a copied indicator for two seconds; copy failure is logged to the console | [Result](../../../web/src/pages/Result.tsx) |

## Cross-platform differences and unresolved quality

Android's accepted failed-write scenario preserves the previous result, offers retry, and navigates only after a successful write. The web Test page catches a localStorage write exception, logs it, and still navigates to Result; it does not provide the Android retry contract. Failed/invalid Result reads are logged and fall through to the no-result view. These are observed differences, not approved equivalent recovery. Decide the intended web recovery behavior before requiring parity.

The web no-result message is currently hardcoded in English in Result; complete localization of that error/empty state is not established by having three locale catalogs. Browser accessibility, narrow layouts, emoji renderer coverage, clipboard denial and corrupt saved-data behavior require actual checks. Preserve current behavior while defining any corrective increment separately.
