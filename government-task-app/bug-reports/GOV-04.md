# [Mobile] Functional/Location Bug: Offline Map Download Continues Without Handling Disabling GPS Location Services

**Severity:** Medium
**Priority:** High

## Description
In the field-task mobile application, under the "تحميل الخرائط بدون اتصال بالإنترنت" (Offline Map Download) feature, when the user selects the "تنزيل حول موقعي الحالي (20 كم)" (Download around current location - 20 km) option, the app enforces GPS location services to be enabled prior to starting.

However, if the user disables device location services (GPS) mid-way through the downloading process, the app fails to pause or restrict the download workflow. It silently continues the map download process without triggering a validation prompt or halting the operation due to missing location coordinates.

## Steps to Reproduce
1. Open the mobile application
2. Navigate to "تحميل الخرائط بدون اتصال بالإنترنت" (Download Offline Maps) screen
3. Toggle ON "تنزيل حول موقعي الحالي (20 كم)" (Ensure device GPS is turned ON when prompted)
4. Tap to start downloading the offline map tiles
5. While downloading, turn off the device Location / GPS service from system settings or quick settings bar
6. Return to the app and observe download behavior

## Actual Result
The map download continues uninterrupted despite disabling GPS, with no blocking validation error or pause handling triggered for the current location dependency.

## Expected Result
The application should actively monitor location service changes during active current-location downloads.

Upon disabling GPS, the app should pause/cancel the download and display a proper validation alert (e.g., "تم إيقاف التحميل، يرجى تفعيل خدمات الموقع للمتابعة" / "Location services disabled, please enable GPS to proceed").

## Environment
App: the application

OS:Android

Screen: Offline Map Download (تحميل الخرائط بدون اتصال)
