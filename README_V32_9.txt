SAH V32.9 — Budget Button Visible + Dean Permission Lock
=========================================================
- Fixed the annual-budget internal button disappearing.
- The 'تعديل الميزانية' button now remains visible in the annual budget circle.
- Legacy render functions are no longer allowed to hide/disable the control.
- Permission is enforced when opening/saving:
  only the Dean of Student Affairs can edit the annual budget.
- For non-Dean roles, clicking the control shows the permission warning and does not open the modal.
- For the Dean role, clicking opens the annual budget modal normally.
- The V32.8 infinite render-loop hotfix is preserved.
- All V32.5/V32.4 features remain included.

Validation:
- node --check js/app.js PASSED.
- No renderAll inside v32Refresh().
