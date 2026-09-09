SAH V32.12 — Annual Budget Persistence Hard Fix
=================================================
Problem addressed:
The entered annual budget could appear correctly immediately after save, then return to zero after browser refresh/update.

What changed:
- Replaced competing annual-budget persistence logic with ONE authoritative store.
- Main record: sah-v3212-annual-budget
- Backup record: sah-v3212-annual-budget-backup
- Browser cookie backup: sah_annual_budget_v3212
- Every read self-heals all compatibility keys from the newest authoritative copy.
- Old raw/stale zero values cannot override a newer timestamped budget.
- V32.11 / V30.9 old keys remain mirrors only for compatibility.
- Save is still Dean-only.
- The annual budget caption now explicitly distinguishes:
  approved annual budget / spent / remaining.
- pageshow and storage events refresh the display without creating render loops.

Important:
The large number shown in the circle is REMAINING annual budget, not the original annual ceiling.
Example:
Annual = 500,000
Approved spend = 10,700
Circle = 489,300

Validation:
- node --check js/app.js PASSED.
- V32.8 render-loop fix preserved.
