# Government Field-Task App — API Testing Report

**Scope:** API Functional Testing, Validation Testing, Authentication Testing, Negative Testing & Error Handling  
**Tool:** Postman  
**Test Scenarios:** 20+  
**Confirmed Defects:** 8  
**Severity:** 4 High · 3 Medium · 1 Low

---

## Overview

This report documents API testing performed on the backend services supporting a government field-task mobile application.

Testing covered authentication, task management, lookup data, field-agent status updates, and location history.

The testing approach combined **positive, negative, validation, boundary, and edge-case scenarios** to evaluate:

- Request and response correctness
- Authentication behavior
- Input validation
- HTTP status codes
- Error handling
- Backend exception handling
- Data validation
- API consistency

---

## Testing Coverage

| Area | Coverage |
|---|---|
| Authentication | Login, invalid credentials, authorization |
| Task Management | Task retrieval, creation/update flows, status updates |
| Lookups | Lookup data retrieval and validation |
| Location History | Single and multiple location records, coordinate validation |
| Validation | Missing fields, invalid values, malformed payloads |
| Error Handling | 4xx/5xx behavior, validation responses, backend exceptions |
| Headers | Content-Type, Accept, Authorization |
| Negative Testing | Invalid tokens, missing data, invalid IDs, out-of-range values |

---

# Confirmed Defects

## API-001 — Incorrect HTTP Status Codes Returned for Failed Requests

**Severity:** Medium  
**Affected Areas:** Authentication, task management, lookups, status updates, location history

### Description

Failed requests consistently return `HTTP 200 OK`, while the actual application-level error code is returned inside the JSON response body.

This means a client, monitoring system, or integration relying only on the HTTP status code may incorrectly interpret failed requests as successful.

### Examples

| Scenario | Expected HTTP | Actual HTTP |
|---|---:|---:|
| Invalid login | 401 | 200 |
| Missing required field | 422 | 200 |
| Invalid token | 401 | 200 |
| Invalid status value | 422 | 200 |
| Invalid request parameters | 422 | 200 |

### Expected Result

HTTP status codes should accurately represent the outcome of the request.

### Actual Result

Failed requests return `200 OK`, while the actual error code is embedded in the response body.

### Impact

This can affect client-side error handling, API integrations, monitoring, and automated systems that rely on standard HTTP semantics.

---

## API-002 — Backend Exception Triggered by Valid Status Update

**Severity:** High  
**Endpoint:** `POST /tasks/task_status`

### Description

A request containing valid task and status information triggers an unhandled backend exception instead of successfully updating the task status.

### Expected Result

The task status should be updated successfully.

### Actual Result

The request triggers an unhandled server-side exception.

### Impact

The endpoint fails for a valid request and prevents the intended task status operation from completing.

---

## API-003 — Missing Task Identifier Causes Server Error

**Severity:** High  
**Endpoint:** `POST /tasks/update`

### Description

Removing the required task identifier from the request should result in a validation response.

### Expected Result

`422 Unprocessable Entity` with a clear validation message.

### Actual Result

`500 Internal Server Error`.

### Impact

Invalid client input causes a server-side failure instead of being handled through normal validation.

---

## API-004 — Missing Location Date Causes Server Error

**Severity:** High  
**Endpoint:** `POST /location_history/create`

### Description

Removing the required date field from a location-history request results in a server error instead of a validation response.

### Expected Result

`422 Unprocessable Entity` with a clear validation message.

### Actual Result

`500 Internal Server Error`.

### Impact

The backend does not gracefully handle missing required input.

---

## API-005 — Invalid Base64 Image Causes Server Error

**Severity:** Medium  
**Endpoint:** `POST /tasks/update`

### Description

An invalid value supplied for an image field is not handled through normal input validation.

### Expected Result

The request should be rejected with a clear validation error.

### Actual Result

`500 Internal Server Error`.

### Impact

Malformed client input can trigger an unexpected backend failure.

---

## API-006 — Invalid Latitude Accepted

**Severity:** Medium  
**Endpoint:** `POST /tasks/update`

### Description

An out-of-range latitude value was accepted instead of being rejected through coordinate validation.

### Test Input

`latitude = 999`

### Expected Result

The API should reject coordinates outside the valid geographic range.

### Actual Result

The request was accepted and processed successfully.

### Impact

Invalid geographic data can enter the system and potentially affect downstream location-related functionality.

---

## API-007 — Internal Backend Error Exposed for Invalid Task Identifier

**Severity:** High  
**Endpoint:** `POST /tasks/task_status`

### Description

A request referencing a non-existent task identifier results in an unhandled backend response rather than a controlled client-facing error.

### Expected Result

A clean response such as:

- `404 Not Found`, or
- `422 Unprocessable Entity`

with a meaningful message such as "Task not found."

### Actual Result

A raw backend error is returned instead of a controlled API response.

### Security Consideration

The response exposed internal implementation details that should not normally be returned to API consumers.

### Impact

This represents an information-disclosure risk and can provide unnecessary insight into backend implementation details.

> Sensitive implementation details, identifiers, payloads, and reproduction information have been intentionally omitted from this public report.

---

## API-008 — Generic Validation Message Contains Spelling Error

**Severity:** Low  
**Endpoint:** `POST /tasks/task_status`

### Description

An empty request parameter object returns a generic validation message instead of identifying the missing required data.

### Expected Result

The API should return a clear field-level validation message identifying the missing input.

### Actual Result

A generic validation message is returned with a spelling error and without identifying the missing field.

### Impact

The message reduces clarity for API consumers and makes troubleshooting more difficult.

---

# Passed Scenarios

The following scenarios were tested successfully and were not classified as defects:

- Successful authentication
- Invalid authentication handling at the application level
- Response header validation
- `Content-Type` validation
- Token handling
- Task retrieval
- Lookup retrieval
- Invalid field-agent status rejection
- Missing description validation
- Multi-task update
- Empty task-array handling
- Multiple location records upload
- Invalid latitude rejection in the location-history endpoint
- Missing Authorization header handling at the application level

> Note: Some successful application-level validations still exhibited related HTTP status-code issues covered by **API-001**.

---

# Observations

The following were documented as observations rather than defects:

### POST Used for Read Operation

The task retrieval operation uses `POST` rather than the conventional `GET` method.

This is unconventional from a REST design perspective but may be intentional based on the API architecture.

### JSON-RPC Style Response Format

The API consistently uses a JSON-RPC-style response structure rather than conventional REST response conventions.

### Automated Token Handling

Postman Collection Variables were used to automatically handle authentication tokens across requests.

### Centralized Lookup Data

Lookup values are retrieved through a centralized lookup endpoint.

### Request Headers

`Content-Type` and `Accept` headers were configured consistently across tested endpoints.

---

# Postman Testing Approach

The API testing workflow followed:

**Request Design → Positive Testing → Negative Testing → Validation → Response Analysis → Defect Reporting → Retesting**

### Positive Testing

Validated expected successful behavior using valid requests and expected data.

### Negative Testing

Intentionally supplied invalid or incomplete input, including:

- Missing required fields
- Invalid credentials
- Invalid authorization
- Invalid identifiers
- Invalid data types
- Out-of-range values
- Malformed payloads
- Empty parameters

### Response Validation

Validated:

- HTTP status codes
- Response body
- Response structure
- Error messages
- Headers
- Authentication behavior
- Backend error handling

---

# Test Results

| Metric | Result |
|---|---:|
| Test Scenarios | 20+ |
| Confirmed Defects | 8 |
| High Severity | 4 |
| Medium Severity | 3 |
| Low Severity | 1 |

### Defect Distribution

**High:** 4  
**Medium:** 3  
**Low:** 1

---

# Key QA Findings

The API testing exercise identified several areas requiring attention:

- Incorrect use of HTTP success status codes for failed requests
- Missing backend validation for certain inputs
- Server-side exceptions caused by invalid or incomplete requests
- Insufficient validation of geographic data
- Inconsistent error handling
- Exposure of internal backend information
- Non-specific validation messages

These findings demonstrate the value of combining **positive API testing with systematic negative and edge-case testing**.

---

# Confidentiality

This report has been sanitized for public portfolio use.

The following information has been intentionally excluded:

- Internal URLs
- Credentials and authentication tokens
- User or customer data
- Internal identifiers
- Sensitive payloads
- Detailed security-sensitive reproduction information
- Internal implementation details

Project and product names have been generalized to protect confidentiality.

The report is intended to demonstrate **API testing methodology, defect analysis, validation techniques, and QA practices**, not to disclose confidential system information.
