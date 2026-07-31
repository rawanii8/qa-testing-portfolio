# [Mobile] Functional/Validation Bug: Download Map Initiates Without Selecting a Custom Map Area or Enabling Location Toggle

**Severity:** Medium
**Priority:** High

## Description
In the field-task mobile application, under the "تحميل الخرائط بدون اتصال بالإنترنت" (Offline Map Download) feature, missing selection validation allows users to start downloading without specifying a map boundary or setting a default region.

When both conditions are unmet—meaning the user has NOT drawn/selected a custom area on the map AND the "تنزيل حول موقعي الحالي (20 كم)" toggle is kept OFF—tapping the download button still triggers the map tile download process. The system lacks validation logic to block execution or prompt the user to make a valid location selection first.

## Steps to Reproduce
1. Open the mobile application
2. Navigate to "تحميل الخرائط بدون اتصال بالإنترنت" (Download Offline Maps) screen
3. Keep the "تنزيل حول موقعي الحالي (20 كم)" toggle switched OFF
4. Do NOT tap or draw any custom area/boundary on the map interface
5. Tap the "تنزيل الخريطة الآن" (Download Map Now) action button

## Actual Result
The download process starts immediately without any area coordinates defined, missing both default location handling and input validation prompts.

## Expected Result
The download action button should remain disabled until a valid map area is selected or toggled.

Alternatively, tapping the button without a selected area should trigger an inline validation toast message (e.g., "يرجى تحديد منطقة على الخريطة أو تفعيل الخيار حول موقعك الحالي للبدء" / "Please select a map region or enable current location option to proceed").

## Environment
App: the application

OS:Android

Screen: Offline Map Download (تحميل الخرائط بدون اتصال)
