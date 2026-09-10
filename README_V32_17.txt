SAH V32.17 — Submission Confirmation / Closed Cards / Budget Header / Points Sync
=================================================================================
1) Participant request cards
- Finished cards are now fully grey, not only partially grey.
- Cancelled cards are also visually closed/grey.
- Existing automatic ordering remains:
  active/new cards right, closed cards left.

2) Event submission confirmation
Applied to:
- Sports event requests
- Club event requests
- Volunteer opportunities
- Student Council activities

After a successful new event request:
- A professional UBT modal appears instead of a small text toast.
- It confirms the event was submitted successfully.
- Status is shown as "تحت المراجعة".
- The creation form is cleared automatically.
- Event-day/start/end defaults are restored so a new event can be entered.

3) Annual budget modal
- All text/icons/buttons inside the blue top header are forced to white.
- This prevents conflicting legacy CSS from showing dark/blue text on blue background.

4) Add Activity points calculator
Root issues fixed:
- The live preview previously omitted activitySubField entirely.
- Therefore subfield calculator values could resolve to zero.
- Select fields were listening only to input; change events are now handled too.
- calculateActivityPoints now uses:
  a) exact subfield calculator settings when selected;
  b) main-field + global calculator settings as fallback.
- When an ended approved event is auto-filled into Add Activity, the platform now
  attempts to match its game/type/category with the KPI Officer's configured
  subfield and main field, then immediately recalculates the live points preview.
- Saving the Sports KPI points calculator dispatches an update event and refreshes
  the Add Activity preview immediately.
- Stored calculator settings remain the single source for points calculation.

Preserved:
- V32.16 submission/timing fixes and removed 3-day rule.
- V32.15 participant ordering.
- V32.14 cancellation/early-end/pending edit.
- V32.13 budget persistence.
- V32.8 stability hotfix.

Validation:
- node --check js/app.js PASSED.
- No renderAll inside v32Refresh().
