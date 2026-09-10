SAH V32.14 — Event Cancellation / Early End / Pending Request Editing
======================================================================
EVENT END FLOW
- Clicking "إنهاء الحدث" now checks event timing BEFORE report availability.
- If the event date is still in the future:
  popup action = "إلغاء الحدث"
  mandatory cancellation reason, maximum 15 words.
- If the event is on its active day/range and scheduled end time has not arrived:
  popup action = "إنهاء الحدث باكرًا"
  mandatory early-end reason, maximum 15 words.
- Normal report-gated completion remains for the normal completion flow.
- Cancelled events are marked "ملغي", do not require an execution report,
  and are excluded from Reports & Analytics > Add Activity.
- Early-ended events are marked finished and become available for reporting.
- Participant applications are closed on cancellation without satisfaction survey.

PENDING EVENT REQUEST EDITING
- Added "تعديل الطلب" only while request status is "تحت المراجعة".
- Once approved or rejected, the edit control is unavailable.
- Supported request scopes:
  Sports event request -> sports_manager
  Club event request -> faculty
  Volunteer opportunity -> activities_manager
  Student Council activity -> student_council
- Edit loads the existing request into its original form.
- Submit button becomes "حفظ التعديلات".
- Added "إلغاء التعديل".
- Saving updates the SAME request ID; it does not create a duplicate.
- Existing request status remains pending.
- New-event outstanding-report gate does not block editing an existing pending request.

PRESERVED
- V32.13 annual-budget no-zero-flicker fix.
- V32.8 render-loop stability fix.
- Event days, start/end time, automatic completion, participant search/swipe.
- Budget PDF/Excel export and Student Council redesign.

VALIDATION
- node --check js/app.js PASSED.
- No renderAll inside v32Refresh().
