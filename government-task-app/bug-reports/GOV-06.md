# [Mobile] Functional/UI Bug: "Zoom/Focus" Icon Non-Responsive for Maps Downloaded Via Current Location Option

**Severity:** Medium
**Priority:** Medium

## Description
In the field-task mobile application, under the "تحميل الخرائط بدون اتصال بالإنترنت" (Offline Map Download) feature, an interaction bug occurs inside the "المناطق المحملة حالياً" (Currently Downloaded Regions) list.

When a user downloads an offline map using the "تنزيل حول موقعي الحالي (20 كم)" option, tapping the Zoom/Focus icon next to the downloaded item (e.g., "موقعي الحالي #1") fails to redirect or focus the map view onto the downloaded 20 km coverage radius. Conversely, the same Zoom/Focus action button works as expected for maps downloaded via custom-drawn boundaries.

## Steps to Reproduce
1. Open the mobile application
2. Navigate to "تحميل الخرائط بدون اتصال بالإنترنت" (Download Offline Maps) screen
3. Download an offline map using a custom-drawn region and observe that tapping the Zoom/Focus icon centers the map correctly on that region
4. Download another offline map using the "تنزيل حول موقعي الحالي (20 كم)" option
5. Scroll down to the "المناطق المحملة حالياً" section
6. Tap the Zoom/Focus icon next to the downloaded "موقعي الحالي" entry

## Actual Result
Tapping the Zoom/Focus button for "موقعي الحالي" maps is completely non-responsive and fails to navigate/focus the map view onto the downloaded radius.

## Expected Result
Tapping the Zoom/Focus icon for any downloaded entry (whether custom-drawn or location-based) should consistently navigate to the map view and highlight/center the downloaded 20 km coverage zone around the user's saved location coordinates.

## Environment
App: the application

OS:Android

Screen: Offline Map Download > Downloaded Regions (المناطق المحملة حالياً)
