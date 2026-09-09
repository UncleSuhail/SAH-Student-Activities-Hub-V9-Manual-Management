SAH V32.11 — Budget Persistence + True Center
================================================
FIX 1 — Annual budget returning to zero
- Added one canonical annual-budget state:
  sah-v3211-annual-budget-state
- The Dean's saved budget is written to this canonical state first.
- Old budget keys are kept synchronized only for compatibility.
- On refresh/update, the canonical value wins over stale legacy zero values.
- Existing old budget values are migrated automatically.
- Added post-save verification before closing the modal.
- A legitimate budget value of 0 is still supported if the Dean intentionally saves 0.

FIX 2 — Edit button exact centering
- Removed transform-based centering from the final override.
- Button uses left:0 + right:0 + automatic margins.
- This is stable in both RTL and LTR.
- The button is now horizontally centered inside the annual-budget circle.

Preserved
- Dean-only edit permission.
- V32.8 render-loop stability fix.
- Event timing, event-day duration, swipe index, participant search.
- Budget Excel/PDF export.
- Student Council redesign.

Validation
- node --check js/app.js PASSED.
- No renderAll inside v32Refresh().
