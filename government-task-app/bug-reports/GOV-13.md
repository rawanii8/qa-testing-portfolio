# [Mobile] Functional Bug: Uploaded Photo in Shared Lawsuit Photo Section Is Lost When Navigating Away Before Submitting

**Severity:** High
**Priority:** Medium

## Description
When a user uploads a photo in the Shared Lawsuit Photo (صورة صحيفة الدعوى (مشترك)) section, the attachment is not preserved if the user navigates away from the screen before submitting the task. Upon returning to the same screen, the uploaded photo is lost and the section resets to its default empty state. This results in data loss, forcing users to upload the attachment again and negatively impacting the task completion workflow.

## Preconditions
The user has accessed a Grouped Task containing multiple associated tasks (e.g., Tasks #[Task ID], #[Task ID], #[Task ID]).

## Steps to Reproduce
1. Navigate to the Grouped Tasks (المهمة المجمعة) screen.
2. Open Shared Lawsuit Details (تفاصيل الدعوى المشتركة).
3. Scroll to the Shared Lawsuit Photo (صورة صحيفة الدعوى (مشترك)) section.
4. Upload or capture a photo using Gallery (معرض الصور) or Camera (التقاط صورة).
5. Verify that the photo is successfully added (e.g., the indicator displays "1 صور مضافة").
6. Navigate away from the screen (e.g., press the Back button or switch to another screen/tab) without submitting the task.
7. Reopen the same Shared Lawsuit Details screen.

## Actual Result
The uploaded photo is removed after navigating away from the screen. When the user returns, the attachment section is reset to its default empty state and displays "لا توجد صور مضافة حالياً" (No photos currently added).

## Expected Result
The uploaded photo should remain available when the user returns to the screen before submitting the task. The application should preserve the attachment by maintaining the current state or saving it as a temporary draft until the task is submitted or explicitly discarded.
