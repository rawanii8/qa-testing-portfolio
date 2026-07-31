# [Mobile] UI Bug: Date Picker Navigation Controls Missing Month Names

**Severity:** Low
**Priority:** Low

## Description
The date picker dialog does not display the month name on the previous/next navigation controls. Only the navigation arrows are shown, while the corresponding previous and next month names are missing. This makes it less clear to users which month they will navigate to when using these controls.

## Preconditions
The user is logged into the application.
A screen containing a date field is accessible.
The date picker dialog is opened.

## Steps to Reproduce
1. Launch the application.
2. Navigate to any screen containing a date input field.
3. Open the date picker.
4. Observe the previous and next month navigation controls at the top of the calendar.

## Actual Result
Only the navigation arrows are displayed. The previous and next month names are missing, making the month navigation unclear.

## Expected Result
The previous and next navigation controls should display both the navigation arrows and the corresponding month names (e.g., June and August) in accordance with the application's design.
