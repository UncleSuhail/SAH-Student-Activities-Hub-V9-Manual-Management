SAH V32.15 — Participant Cards Status + Automatic RTL Order
================================================================
Applied to all participant-event indexes:
- Sports
- Clubs
- Volunteer
- Student Council

Behavior:
- Active/new approved events begin from the RIGHT.
- Newer active events remain closest to the right edge.
- Finished and cancelled events move automatically toward the LEFT end.
- Horizontal swipe remains enabled for large numbers of events.

Card status:
- Active: الحدث قائم
- Finished: الحدث منتهي
- Cancelled: الحدث ملغي
- Cancellation reason appears when available.

Closed cards:
- Finished cards show final accepted participant count.
- Cancelled cards show participation closed.
- Historical participant lists remain selectable/searchable/exportable.

Preserved:
- V32.14 cancellation / early ending / pending request editing.
- V32.13 budget no-zero-flicker fix.
- V32.8 stability fix.
- Timing, search, PDF/Excel export, Student Council redesign.

Validation:
- node --check js/app.js PASSED.
- No renderAll inside v32Refresh().
