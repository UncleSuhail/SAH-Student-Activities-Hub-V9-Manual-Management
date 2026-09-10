SAH V32.18 — Add Activity Manual/Automatic Entry + Early Cancel Modal Polish
=============================================================================
1) Reports & Analytics > Add Activity
- Added a professional mode switch in the Add Activity modal header:
  * تعبئة تلقائية
  * تعبئة يدوية
- Automatic mode remains the default.
- Automatic mode requires selecting a finished approved event and keeps event-derived fields read-only.
- Manual mode hides the event-source selector and allows direct entry of:
  activity name, date, days, beneficiaries, players, game/activity type, and budget.
- Point calculation remains synchronized with the KPI Officer calculator in BOTH modes.
- Switching back to Automatic restores the event-source workflow.
- Closing/reopening Add Activity returns to Automatic mode by default.

2) Early event cancellation / early finish modal
- Rebuilt the modal layout to eliminate title overlap.
- Separated platform label, action title, and UBT mark.
- Improved spacing, textarea layout, word counter, and button alignment.
- Cancel button now matches the navy UI; destructive action remains burgundy/red.
- Responsive layout improved for mobile.

Preserved
- V32.17 submission confirmation, fully grey closed participant cards, white budget header, points sync.
- V32.16 event submission fix and removed 3-day rule.
- V32.15 event ordering.
- V32.14 cancellation/early-end/pending edit.
- V32.13 budget persistence.
- V32.8 stability hotfix.

Validation
- node --check js/app.js PASSED.
- No renderAll inside v32Refresh().
