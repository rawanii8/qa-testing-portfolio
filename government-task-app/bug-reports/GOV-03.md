# [Mobile] Functional/Network Bug: False Download Progress and Missing Offline Error Toast During Offline Map Download Disconnection

**Severity:** High
**Priority:** High

## Description
In the field-task mobile application, under the "تحميل الخرائط بدون اتصال بالإنترنت" (Offline Map Download) feature, there is a critical failure in network connection handling.

When active internet connectivity is lost/disconnected while map tiles are downloading, the application fails to handle the network loss. Instead of pausing the operation and throwing an offline error notification (e.g., "تعذر التحميل، يرجى الاتصال بالإنترنت"), the download progress bar incorrectly accelerates and simulates completing the download (False Progress Indicator). This results in incomplete or corrupted offline map data saved on the device without alerting the user.

## Steps to Reproduce
1. Open the mobile application
2. Go to "تحميل الخرائط بدون اتصال بالإنترنت" (Download Offline Maps) screen
3. Select a region/zoom range and initiate the download process
4. While the progress bar is actively downloading tiles (e.g., at 17%), turn off Wi-Fi and Mobile Data (enable Airplane Mode)
5. Observe the progress bar behavior and application response

## Actual Result
The app does not display any connection error messages. The progress counter unexpectedly accelerates and falsely indicates downloading progress without active internet.

## Expected Result
The download process should immediately halt/pause upon detecting network loss.

An inline validation alert or toast message should appear informing the user that internet connection was lost (e.g., "تم إيقاف التحميل مؤقتاً بسبب انقطاع الاتصال بالإنترنت").

## Environment
App: the application

OS:Android

Screen: Offline Map Download (تحميل الخرائط بدون اتصال)
