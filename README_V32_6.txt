SAH V32.6 — Dean Budget Button Critical Fix
==============================================
- Fixed the internal 'تعديل الميزانية' button inside the annual-budget circle.
- The button is now explicitly restricted to role: dean.
- Old/stale click handlers are removed by replacing and rebinding the control at startup.
- The button stops propagation so the parent annual-budget circle cannot steal the click.
- The modal is forced open reliably with correct z-index / pointer-events.
- The Dean can enter, modify, save, and re-save the annual budget.
- Saving recalculates annual, approved spend, requested, and remaining budget immediately.
- Non-Dean accounts cannot see/use the edit control.
- Existing V32.5 functionality is preserved.

Validation:
- node --check js/app.js PASSED.
