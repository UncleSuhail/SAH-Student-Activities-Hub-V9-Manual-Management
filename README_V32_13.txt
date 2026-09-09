SAH V32.13 — Annual Budget Zero-Flicker Root Cause Fix
========================================================
ROOT CAUSE FOUND:
renderBudgetDashboard() is outside the V30.9 private IIFE, but it was trying to
read v309AnnualBudget(), which only exists inside that private IIFE.

Because of:
  typeof v309AnnualBudget === 'function' ? ... : 0
the dashboard renderer silently used 0 every time it refreshed.

A later budget renderer then restored the saved value. This is exactly why the
budget visibly changed:
  saved value -> 0 -> saved value

FIXED:
- renderBudgetDashboard() now reads the global authoritative budget store:
  window.SAH_ANNUAL_BUDGET_STORE.get()
- Removed the out-of-scope annual-budget lookup entirely.
- Added synchronous budget pre-hydration in index.html before app.js loads.
- Legacy budget keys are synchronized before the main application starts.
- The annual-budget card is hydrated before it becomes visible, so 0 is not
  flashed during refresh when a saved budget already exists.
- Saving a new Dean budget immediately updates the boot value and canonical store.
- V32.12 backup persistence remains active.
- V32.8 render-loop stability fix remains active.
- Existing centered/editable budget button remains unchanged.

Validation:
- node --check js/app.js PASSED.
- Old out-of-scope v309AnnualBudget lookup is absent.
- No renderAll inside v32Refresh().
