SAH V32.5 — Final Operational Update
====================================
1) Participant Events Index
- Converted event cards from stacked/wrapped cards to a horizontal swipe/scroll rail.
- Suitable for dozens or hundreds of events without vertical card accumulation.
- Added exact event-index search by event name.
- Added exact date filter and Clear Search button.
- Participant row search now also matches event name and event date.

2) Event Timing / Duration — all event departments
- Sports events: event days + start time + end time.
- Club activities: event days + start time + end time.
- Volunteer opportunities: event days + start time + end time.
- Student Council activities: event days + start time + end time.
- Existing stored events automatically migrate to 1 day, 09:00–17:00 if timing data is missing.
- Same-day end time must be later than start time.

3) Automatic Event Completion
- Approved events are automatically marked finished when their registered end date/time is reached.
- For multi-day events, end time applies to the last event day.
- Accepted participants receive survey eligibility automatically.
- Unresolved applications are closed automatically.
- Only finished events without reports appear in Reports & Analytics > Add Activity.
- The report form automatically receives Number of Days from the event.

4) Student Portal
- Event card now displays start date, number of days, start time, and end time.
- Automatically finished events no longer appear as available for new applications.

5) Annual Budget
- Hardened Edit Budget button for the Dean of Student Affairs.
- Dean can open the annual budget modal, set a budget, edit it, and save/recalculate immediately.
- Added Budget Ledger export to Excel-compatible CSV.
- Added Budget Ledger PDF print/export.
- Budget details remain connected to approved/pending/rejected activity budgets.

Validation
- node --check js/app.js PASSED.
- V32.5 is built on V32.4 and includes all previous consolidated features.
