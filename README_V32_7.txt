SAH V32.7 — Dean Budget Modal Hard Fix
=======================================
Critical correction:
- Removed the previous V32.6 budget controller entirely.
- Removed the attribute MutationObserver that could repeatedly retrigger itself.
- Added one standalone controller that does not depend on private functions from older IIFEs.
- The internal 'تعديل الميزانية' button is hidden by default and shown only when the verified role is Dean.
- Role verification supports the active role selector AND the displayed user role text for legacy synchronization cases.
- Clicking 'تعديل الميزانية' now forcibly opens #annualBudgetModal.
- The modal uses deterministic fixed positioning, z-index, visibility, opacity and pointer-events.
- Dean can set 0 -> any annual budget, edit it later, and save repeatedly.
- Saving writes BOTH historical storage keys:
  sah-v309-annual-budget
  sah-v30-annual-budget
  so old/new builds remain compatible.
- Saving directly refreshes annual, spent, requested, remaining values.
- Non-Dean users cannot see or use the edit button.
- Existing V32.5 functionality is retained.

Validation:
- node --check js/app.js PASSED.
- Old recursive MutationObserver removed.
