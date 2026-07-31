# [Mobile] Security/Validation Bug: System Allows Reusing Current Password as New Password During Change Password Flow

**Severity:** Medium
**Priority:** High

## Description
In the field-task mobile application, the "تغيير كلمة المرور" (Change Password) feature lacks password history/reuse validation. When a user enters their existing password in both the "Current Password" field and the "New Password" / "Confirm New Password" fields (e.g., setting current password 123 and new password 123), the system accepts the input and returns a success notification ("تم تغيير كلمة المرور بنجاح").

This violates standard security policy guidelines, which should prevent reusing the immediate active password.

## Steps to Reproduce
1. Open the mobile application
2. Navigate to "الملف الشخصي" (Profile) screen
3. Tap on "تغيير كلمة المرور" (Change Password) button
4. Enter the active current password in "كلمة المرور الحالية" (e.g., 123)
5. Enter the exact same value in "كلمة المرور الجديدة" and "تأكيد كلمة المرور الجديدة"
6. Tap "تغيير" (Change)

## Actual Result
The application accepts the same password and displays a success toast message ("تم تغيير كلمة المرور بنجاح").

## Expected Result
The system should trigger a validation error message preventing the operation (e.g., "كلمة المرور الجديدة لا يمكن أن تكون مطابقة لكلمة المرور الحالية" / "New password cannot be the same as the current password").

## Environment
App: the application

OS:Android

Screen: Profile > Change Password Modal (الملف الشخصي - تغيير كلمة المرور)
