# Government Field-Task App — API Testing Report

**Scope:** API Functional Testing, Validation Testing, Authentication Testing, Error Handling, Negative Testing
**Tool:** Postman
**Test scenarios executed:** 20+
**Confirmed bugs:** 8 (4 High, 3 Medium, 1 Low)

## Summary

API testing covered the endpoints supporting the field-task mobile application — login/authentication, task management, lookups, field agent status updates, and location history. Testing combined positive-path validation with negative and edge-case scenarios (invalid tokens, missing required fields, malformed payloads, out-of-range values) to surface validation gaps, incorrect error handling, and backend exceptions before they reached production.

## Confirmed Bugs

### API-001 — Incorrect HTTP Status Codes Returned for Failed Requests
**Severity:** Medium
**Affected endpoints:** `POST /user/login`, `POST /tasks`, `POST /lookups`, `POST /tasks/task_status`, `POST /tasks/update`, `POST /location_history/create`

The API consistently returns `HTTP 200 OK` even when a request fails due to authentication or validation errors. The real error code is only available inside `result.code` in the response body, not in the HTTP status line — meaning any client or monitoring tool that checks the HTTP status alone will treat failed requests as successful.

| Scenario | Expected HTTP | Actual HTTP |
|---|---|---|
| Invalid login | 401 | 200 |
| Missing username | 422 | 200 |
| Invalid token | 401 | 200 |
| Invalid field agent status | 422 | 200 |
| Empty params | 422 | 200 |

**Expected:** Proper HTTP status codes reflecting the actual outcome.
**Actual:** Always returns 200.

---

### API-002 — Backend Exception in `/tasks/task_status`
**Severity:** High
**Endpoint:** `POST /tasks/task_status`

A fully valid request (valid task ID, valid field agent status, valid description) triggers an unhandled backend exception rather than completing successfully.

**Expected:** Task status updated successfully.
**Actual:** The request triggers an unhandled server-side exception referencing an internal object attribute, instead of completing the update.
**Impact:** The endpoint cannot be used at all, even with valid input.

---

### API-003 — Missing Task ID Causes Internal Server Error
**Severity:** High
**Endpoint:** `POST /tasks/update`

Removing the `id` field from the task object should trigger a validation error, not a server crash.

**Expected:** 422 Validation Error
**Actual:** 500 Internal Server Error

---

### API-004 — Missing Location Date Causes Internal Server Error
**Severity:** High
**Endpoint:** `POST /location_history/create`

Removing the `date` field from the location object should trigger a validation error, not a server crash.

**Expected:** 422 Validation Error
**Actual:** 500 Internal Server Error

---

### API-005 — Invalid Base64 Image Causes Server Error
**Severity:** Medium
**Endpoint:** `POST /tasks/update`

Sending an invalid value (`"invalid-base64"`) for `addressed_id_image` should be rejected with a validation error.

**Expected:** Validation error.
**Actual:** 500 Internal Server Error.

---

### API-006 — Invalid Latitude Accepted
**Severity:** Medium
**Endpoint:** `POST /tasks/update`

Sending an out-of-range coordinate (`latitude = 999`) is accepted and processed instead of being rejected.

**Expected:** Reject invalid coordinate.
**Actual:** Task updated successfully — no coordinate validation is applied.

---

### API-007 — Internal Backend Exception Exposed for Invalid Task ID
**Severity:** High
**Endpoint:** `POST /tasks/task_status`

Requesting a non-existent task ID (`id = 9999999`) surfaces a raw backend error instead of a clean client-facing response.

**Expected:** 404 Not Found or 422 Validation Error (e.g., "Task not found").
**Actual:** A raw, unhandled server error is returned instead of a clean client-facing response, exposing internal implementation details (exception internals, backend framework identifiers, and an internal identifier) that should never reach an API consumer.

**Impact:** Minor information-disclosure risk — internal implementation details are exposed to any client that triggers this error.

---

### API-008 — Generic Validation Message Contains a Spelling Error
**Severity:** Low
**Endpoint:** `POST /tasks/task_status`

Sending an empty params object returns a generic, misspelled validation message instead of identifying the missing field.

**Expected:** A specific message (e.g., "Missing required field: data") or field-level validation.
**Actual:** "Messing required data!" — a generic message with a spelling error, and no indication of which field is missing.

## Scenarios That Passed

The following areas were tested and behaved correctly, so were not classified as bugs: successful login, response headers, `Content-Type` verification, token handling, retrieving tasks and lookups, rejecting an invalid field agent status, rejecting a missing description, multi-task update, handling an empty tasks array, uploading multiple locations, rejecting invalid latitude in `/location_history/create`, and returning an unauthorized response when the Authorization header is missing (at the application level — see API-001 for the related HTTP status issue).

## Observations (Not Bugs)

- `/tasks` uses `POST` instead of `GET`, which is unconventional for a read operation.
- The API consistently uses a JSON-RPC style response format.
- Automatic token handling via Postman Collection Variables worked correctly throughout testing.
- Lookup values are centralized through a single `/lookups` endpoint.
- `Content-Type` and `Accept` headers are configured correctly across endpoints.

## Executive Summary

| Category | Count |
|---|---|
| Total test scenarios | 20+ |
| Passed | 12 |
| Failed (confirmed bugs) | 8 |

**Severity distribution:** High 4 · Medium 3 · Low 1
