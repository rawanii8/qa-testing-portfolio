# Government Field-Task Management System — QA Testing

**Platform:** Mobile Application  
**Domain:** Government Field-Task / Process-Server Workflow  
**Testing Scope:** Manual Functional Testing & REST API Testing

Hands-on QA testing performed on a government mobile application supporting field-task and process-server workflows. Testing covered functional workflows, input validation, offline behavior, localization, UI/UX, authentication-related flows, and backend API validation.

---

## Testing Areas

### Authentication & Session Validation

- Authentication flow validation
- Password-change workflow validation
- Session-related behavior
- Negative authentication scenarios

### Functional Testing

- Offline map download behavior
- Search functionality and input handling
- Photo attachment persistence during navigation
- Progress indicator and step-counter behavior
- Task workflow validation

### Input Validation

- Identity field input validation
- Date field validation
- Negative and boundary scenarios
- Required-field validation

### Localization

- Arabic localization
- RTL behavior
- Offline-mode localization
- Task status and UI text consistency

### UI/UX

- Required-field indicators
- Navigation state visibility
- Icon state consistency
- Date-picker behavior
- Visual contrast and usability

---

## Manual Mobile Testing

Manual testing was performed across key mobile workflows using functional, negative, validation, exploratory, and UI/UX testing approaches.

Defects were documented using a consistent structure adapted for mobile testing:

- Description
- Preconditions — where applicable
- Steps to Reproduce
- Actual Result
- Expected Result
- Environment
- Evidence — where applicable

Testing focused on identifying functional defects, validation gaps, usability issues, localization inconsistencies, and unexpected behavior across user workflows.

---

## API Testing — Postman

The backend REST APIs supporting the mobile application were tested using **Postman**.

### API Testing Coverage

- Authentication
- Task Management
- Lookup Data
- Task Status Updates
- Location History
- Request & Response Validation
- HTTP Status Code Validation
- Header Validation
- Input Validation
- Negative & Edge-Case Testing
- Error-Handling Validation
- Backend Exception Handling

### Key Findings

API testing identified issues including:

- Request data-type mismatches between client payloads and backend expectations.
- Input validation gaps.
- Unexpected behavior under invalid or incomplete requests.
- Unhandled backend exceptions exposed during negative testing.
- Inconsistent API error handling and validation responses.

The detailed API testing report is available in [`api-testing.md`](./api-testing.md).

---

## API Testing Approach

The API testing process included:

**Request Design → Positive Testing → Negative Testing → Validation → Response Analysis → Defect Reporting → Retesting**

Tests covered both expected successful requests and intentionally invalid or incomplete inputs to evaluate backend validation and error handling.

---

## Sample Bug Reports

The [`bug-reports/`](./bug-reports) directory contains a representative and sanitized selection of documented defects.

Reports follow a consistent structure including:

- Bug ID
- Title
- Severity
- Priority
- Description
- Preconditions
- Steps to Reproduce
- Actual Result
- Expected Result
- Environment
- Evidence

---

## Sensitive Findings

Due to the nature of the system, certain security-sensitive findings are **intentionally excluded from the public repository**.

Only high-level descriptions are provided where necessary, without reproduction steps, payloads, credentials, internal URLs, identifiers, or other information that could expose the system or its users.

This repository is intended to demonstrate **QA methodology and testing experience**, not to disclose confidential system or security information.

---

## Confidentiality

Project and product names have been generalized to protect confidentiality.

The public repository contains only **sanitized and representative testing artifacts**.

The following are not included:

- Internal URLs
- Credentials or tokens
- User or customer data
- Internal IDs
- API secrets
- Sensitive system information
- Detailed security-sensitive reproduction steps

The detailed internal testing records are maintained privately and are not published publicly.
