# [Mobile] Validation Bug: Passport Number and National ID Fields Accept Invalid Characters and Unlimited Length

**Severity:** High
**Priority:** High

## Description
The Passport Number (رقم جواز السفر) and National ID Number (رقم إثبات الشخصية) fields do not enforce any input validation or formatting rules. Both fields accept arbitrary text, emojis, special characters, and excessively long strings without displaying validation errors. This allows invalid identity information to be entered, compromising data integrity and increasing the risk of storing malformed or inaccurate records.

## Steps to Reproduce
1. Navigate to the Task Execution (تنفيذ المهمة) screen.
2. Open the Details (التفاصيل) tab.
3. Scroll down to the Passport Number (رقم جواز السفر) and National ID Number (رقم إثبات الشخصية) fields.
4. Enter arbitrary text containing emojis, uppercase/lowercase letters, special characters, and invalid-length strings (e.g., yyyyuuhyyujhhdz,5433.......).
5. Attempt to save or submit the form.

## Actual Result
Both fields accept arbitrary text, emojis, special characters, and excessively long strings without applying input validation, formatting rules, or displaying validation errors.

## Expected Result
National ID Number: Should accept only numeric digits and enforce the required length (e.g., 14 digits for an Egyptian National ID).
Passport Number: Should accept only valid passport characters based on the application's supported format (e.g., alphanumeric with an appropriate length limit).
Both fields should reject emojis, special characters, and invalid input, displaying an appropriate validation message when necessary.
