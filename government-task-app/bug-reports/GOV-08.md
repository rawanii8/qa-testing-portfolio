# [Mobile] UI/Validation Bug: Required Field Not Visually Marked as Mandatory in Execute Task Screen (Contact Name Field)

**Severity:** Medium
**Priority:** Medium

## Description
On the "تنفيذ المهمة" screen (مهمة رقم #[Task ID]), the "إسم المخاطب" (Contact Name) field is required — confirmed by the validation error message "هذا الحقل مطلوب ويجب تعبئته" that appears when the field is left empty and the user attempts to save — but the field label has no visual indicator (such as an asterisk or "إجباري" label) showing the user it's mandatory before they attempt to submit.

## Steps to Reproduce
1. Navigate to تنفيذ المهمة (Execute Task) for any task (e.g., مهمة رقم #[Task ID])
2. Under "مخاطبا مع", observe the "إسم المخاطب" field label before entering any input
3. Attempt to save without filling in the field

## Actual Result
The "إسم المخاطب" field label shows no indicator that the field is required, and the error "هذا الحقل مطلوب ويجب تعبئته" only appears after attempting to save.

## Expected Result
Required fields, including "إسم المخاطب", should be clearly marked as mandatory (e.g., with an asterisk or "إجباري" label) before the user starts filling out the form.
