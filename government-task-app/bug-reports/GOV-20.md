# [Mobile] UI/Functional Bug: Date Picker Reopens Highlighting Today's Date Instead of Previously Selected Date

**Severity:** Low
**Priority:** Low

## Description
When a user selects a past date and reopens the date picker, the calendar highlights the current date instead of the previously selected date. This creates an inconsistent user experience, as the date picker does not preserve the user's current selection when reopened.

## Preconditions
The user is logged into the application.
The user has opened a task containing an editable date field.
A past date has been selected and saved (or remains in the field).

## Steps to Reproduce
1. Navigate to a task containing an editable date field.
2. Open the date picker.
3. Select a past date (e.g., 24 July 2026).
4. Confirm the selection.
5. Reopen the same date picker.
6. Observe the highlighted date in the calendar.

## Actual Result
The date picker highlights today's date (e.g., 26 July 2026) instead of the previously selected date, causing the selected value and the calendar focus to be inconsistent.

## Expected Result
The date picker should reopen with the currently selected date (e.g., 24 July 2026) highlighted and focused, regardless of whether it is a past, current, or future date.
