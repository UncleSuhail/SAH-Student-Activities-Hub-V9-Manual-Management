SAH V32.8 — CRITICAL STABILITY HOTFIX
========================================
Root cause found:
- renderAll() scheduled window.v32Refresh()
- v32Refresh() called window.renderAll() again
- This created a permanent render loop approximately every 20ms.
- The browser therefore appeared to load forever and the whole GitHub Pages UI became unresponsive.

Fixed:
- v32Refresh() no longer calls renderAll().
- The 60-second event lifecycle timer no longer calls renderAll().
- Removed unnecessary 1.5-second Dean permission polling.
- Dean annual-budget modal from V32.7 is retained.
- All V32.5 timing/search/swipe features are retained.
- Budget export and Student Council redesign are retained.

Validation:
- node --check js/app.js PASSED.
- Static loop check confirms renderAll is absent from v32Refresh().
