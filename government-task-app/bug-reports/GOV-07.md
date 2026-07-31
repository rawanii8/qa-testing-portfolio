# [Mobile] Functional/UI Bug: Drawn Boundary Overlay Persists on Map Canvas After Download and Area Deletion

**Severity:** Medium
**Priority:** Medium

## Description
In the field-task mobile application, under the "تحميل الخرائط بدون اتصال بالإنترنت" (Offline Map Download) feature, the custom map drawing canvas fails to auto-clear its UI state following completed transactions or item deletions:

Persistent Overlay After Download: After successfully defining and downloading a custom-drawn boundary, the polygon points and lines remain actively rendered on the map selection overlay instead of resetting to a clean state.

Persistent Overlay After Deletion: Even when a user deletes the downloaded map region from the "المناطق المحملة حالياً" list and navigates back to the map drawing screen, the old drawn polygon/points are still retained on the map canvas, forcing the user to manually remove each drawn node.

## Steps to Reproduce
1. Open the mobile application
2. Navigate to "تحميل الخرائط بدون اتصال بالإنترنت" (Download Offline Maps)
3. Tap on the map to draw a custom polygon region (e.g., placing nodes 1, 2, 3) and confirm selection
4. Complete the download process
5. Observe the map interface after download completion
6. Delete the downloaded map from the "المناطق المحملة حالياً" section
7. Re-open the map selection interface

## Actual Result
The previously drawn polygon overlay and node points persist continuously on the map interface after download and deletion, requiring manual clearing.

## Expected Result
Completing a map download or deleting a downloaded region should automatically reset the map drawing state and clear all rendered polygon nodes/overlays from the interface.

## Environment
App: the application

OS:Android

Screen: Offline Map Download > Select Region Canvas (تحديد منطقة التحميل)
