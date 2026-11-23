# PROJECT · Web design and boundaries

Observed: React 18 and TypeScript/Vite app with React Router and i18next. Exact dependencies are owned by [package.json](../../../web/package.json) and its lockfile. Route components own rendered behavior; the generic useTestState hook is not the actual Test page's state owner. Scoring is in a shared web utility; Android has separate Kotlin domain/state/storage implementations.

Browser localStorage and clipboard are platform boundaries. No app backend is required by the current source. A blocked browser storage operation can leave a previous result or no result visible after completion; do not claim the Android atomic persistence guarantee for web. Define schema validation, user-visible recovery and compatibility only in a separately accepted behavioral change.
