SAH V32.16 — Event Submission Fix + Remove 3-Day Rule
========================================================
Fixed event submission buttons across all event modules.

Root cause:
- Sports, Club, Volunteer and Student Council submission handlers called
  validEventTiming() from outside the IIFE where that function was declared.
- This could produce ReferenceError and make a submit button appear dead.

Fix:
- Added one global validator: window.SAH_VALID_EVENT_TIMING(...)
- Sports request verified.
- Club event request verified.
- Volunteer opportunity verified.
- Student Council activity verified.

Removed 3-day rule:
- Removed the visible Sports note requiring 3 days.
- Removed Sports 3-day runtime validation.
- Removed Club-event 3-day runtime validation.
- Removed old later3() helper entirely.
- Start/end time validation remains.

Preserved:
- V32.15 participant card ordering/status.
- V32.14 cancellation / early-end / pending edit.
- V32.13 budget persistence/no-zero flicker.
- V32.8 stability hotfix.

Validation:
- node --check js/app.js PASSED.
- All four creation paths use accessible global timing validation.
- No 3-day restriction remains in submission logic.
