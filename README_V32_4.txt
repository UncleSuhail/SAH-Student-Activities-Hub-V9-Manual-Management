SAH V32.4 — Budget + Responsive Event Index + Student Council Redesign
======================================================================

FIXED — Budget system
- Rebuilt budget aggregation from all event request stores:
  sports events, club activities, volunteer opportunities, student council activities.
- Supports legacy/current approved status labels including:
  مقبول، معتمد، معتمد نهائيًا، تمت الموافقة.
- Annual remaining budget is always:
  Dean Annual Budget - Total Approved Event Budgets.
- Pending budgets appear under Requested Budget but do not reduce the annual balance.
- Rejected budgets do not reduce the annual balance.
- Budget details buttons now always open a populated operational ledger.
- Annual budget circle opens the full ledger; its internal Edit Budget button remains Dean-only.
- Added a four-part financial summary: annual, spent, requested, remaining.
- Existing stored events are included automatically.

FIXED — Event / participant cards
- Event cards now wrap in a controlled 3 / 2 / 1 column responsive grid.
- No card is allowed to compress until content overlaps.
- Remaining-seat panel was converted to a compact vertical internal layout.
- Participant tables scroll horizontally inside their own container.
- Adding more events creates clean new rows instead of crushing existing cards.

REDESIGNED — Student Council
- Entire page changed from competing two-column panels to a full-width vertical workflow.
- Sections now appear one below another:
  01 Members
  02 Activity submission
  03 Participant requests
  04 Meetings
  05 Student suggestions
  06 Permissions
- Forms use responsive internal grids while each operational section remains full width.
- Every table has an isolated horizontal scroll area.
- Added stronger visual separation, spacing, borders, and section numbering.

VALIDATION
- node --check js/app.js: PASSED
- No Storage.prototype patching.
- Package includes all V32.3 / V32.2 functionality and this V32.4 repair.
