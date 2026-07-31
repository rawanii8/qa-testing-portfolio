# [Mobile] Localization Bug: Task Status Badge Displayed in English ("received") Instead of Arabic During Offline Mode

**Severity:** Low
**Priority:** Medium

## Description
When the application is used in Offline Mode, the task status badge is not localized according to the selected application language. Instead of displaying the status in Arabic, the badge shows the English text "received", resulting in a language inconsistency within the Arabic user interface.

## Preconditions
The device is disconnected from the internet, causing the application to enter Offline Mode ("أنت تعمل حالياً بدون اتصال بالإنترنت").

## Steps to Reproduce
1. Disable both Wi-Fi and Mobile Data on the testing device.
2. Open the application.
3. Navigate to the Daily Tasks (مهامي اليومية) screen.
4. Observe the status badge displayed on the task cards (e.g., Tasks #[Task ID] and #[Task ID]).

## Actual Result
During Offline Mode, the task status badge displays the English text "received" instead of its Arabic translation, causing a localization inconsistency within the Arabic UI.

## Expected Result
The task status badge should be fully localized based on the application's selected language. In the Arabic interface, it should display the appropriate Arabic status (e.g., "مستلمة" or "تم الاستلام") while maintaining consistency with the RTL layout.
