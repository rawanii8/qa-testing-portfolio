# [Mobile] Validation Bug: Date Fields Accept Past Dates Without Validation

**Severity:** Medium
**Priority:** Medium

## Description
The application allows users to select dates in the past for date fields that should only accept the current date or future dates. No validation is performed to prevent the selection or submission of an invalid past date, which may lead to incorrect task execution data.

## Preconditions
The user is logged into the application.
The user has opened a task containing a date field (e.g., Execution Date (تاريخ التنفيذ) or Actual Move Date (تاريخ الانتقال الفعلي)).
The date picker is available.

## Steps to Reproduce
1. Navigate to a task containing an editable date field.
2. Open the date picker.
3. Select a date earlier than the current date (e.g., 2026-07-24 when the current date is 2026-07-26).
4. Save or continue with the selected date.
5. Observe the behavior.

## Actual Result
The application accepts past dates without any validation, allowing users to save or proceed with an invalid date.

## Expected Result
The application should prevent users from selecting or submitting past dates for fields that are restricted to the current date or future dates. An appropriate validation message should be displayed if an invalid date is selected.
