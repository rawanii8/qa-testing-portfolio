# [Mobile] Validation Bug: Registered Notice Number Field Accepts Invalid Characters and Unlimited Length

**Severity:** Medium
**Priority:** Medium

## Description
The "Registered Notice Number" (رقم الإخطار المسجل) field does not enforce any input validation. It accepts emojis, alphabetic characters, special symbols, and excessively long strings without displaying any validation error. This may result in invalid or corrupted data being submitted and compromises data integrity.

## Steps to Reproduce
1. Navigate to the Task Execution (تنفيذ المهمة) screen.
2. Open the Details (التفاصيل) tab.
3. Click on the mandatory "Registered Notice Number" (رقم الإخطار المسجل) field.
4. Enter non-numeric characters, including emojis, alphabetic letters, special symbols, and an excessively long string (e.g., 👆👆🤡😍...yyyyuuhy\).
5. Attempt to save or submit the task.

## Actual Result
The field accepts all input types, including emojis, random text, special symbols, and unlimited character lengths, without any client-side validation or error message.

## Expected Result
The field should enforce the expected input format (numeric or predefined alphanumeric), restrict the maximum allowed length, reject invalid characters such as emojis and special symbols, and display an appropriate validation message when invalid input is entered.
