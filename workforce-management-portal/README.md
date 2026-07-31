# Workforce Management Portal — QA Testing

**Platform:** Web Application  
**Domain:** HR / Workforce Management  
**Testing Scope:** Manual Functional, Regression, Exploratory, Localization/RTL, UI/UX & Access-Control Validation  
**Bug Tracking:** Trello

Hands-on QA testing performed across a workforce management web portal covering employee attendance, tasks, leaves, communication, meetings, reports, and project management.

Testing focused on functional correctness, Arabic localization and RTL behavior, session and access-control validation, data integrity, and overall user experience.

---

## Testing Coverage

Testing covered multiple functional modules across the portal:

- Login & Authentication
- Communication
- Notifications
- Shifts & Attendance
- Leaves
- Meetings
- Reports & Export
- Screenshots
- Team Dashboard
- Projects & Kanban

---

## Defect Categories

### Localization & RTL

Testing identified multiple Arabic localization and RTL issues, including:

- Untranslated English strings
- Incorrect or missing status translations
- Incorrect filter labels
- Raw i18n translation keys displayed to users
- Backend enum values exposed directly in the UI
- Incorrect RTL text and date ordering
- Mixed-language and corrupted UI strings
- RTL alignment and layout inconsistencies

---

### Functional Testing

Functional testing covered core workflows and user interactions, including:

- Session and logout behavior
- Non-functional buttons and icons
- Notification behavior
- Infinite loading states
- Timer and duration behavior
- Incorrect success messages
- Features failing silently after apparently successful operations
- Workflow and state-management issues

---

### Session, Permission & Data Integrity Validation

Testing included validation of session termination, access control, and data consistency.

Findings included:

- Session termination not consistently revoking access
- Data-isolation issues between user views
- Access-control validation gaps
- Internal technical information exposed to end users
- Data being overwritten without sufficient user warning

> These findings represent security-related validation performed as part of standard QA testing. They do not represent penetration testing or a formal security assessment.

---

### UI/UX

UI and usability testing covered:

- RTL layout behavior
- Overlapping elements
- Clipped content
- Component alignment
- Text contrast
- Visual consistency
- Cross-page formatting consistency
- State and interaction visibility

---

## Manual Testing Approach

Testing was performed using a combination of:

- Functional Testing
- Regression Testing
- Exploratory Testing
- Positive & Negative Testing
- Validation Testing
- Localization & RTL Testing
- UI/UX Testing
- Session Validation
- Permission & Access-Control Validation
- Data Integrity Validation
- End-to-End Workflow Testing

Test scenarios were designed around expected user behavior, business workflows, validation rules, and edge cases.

---

## Defect Reporting

Defects were documented and tracked in **Trello** using a consistent structure:

- **Title**
- **Severity**
- **Priority**
- **Description**
- **Steps to Reproduce**
- **Actual Result**
- **Expected Result**
- **Environment**
- **Evidence** — where applicable

### Defect Lifecycle

**Discovery → Documentation → Triage → Fix Verification → Retesting → Regression → Closure**

Reports were written with reproducible steps and clear expected/actual results to support efficient investigation and verification.

---

## Sample Bug Reports

The [`bug-reports/`](./bug-reports) directory contains a representative and sanitized selection of documented defects covering different testing areas, including:

- Application crashes
- Session validation issues
- Data-isolation findings
- Access-control validation
- Functional defects
- Localization and RTL issues
- UI/UX inconsistencies

The samples are intended to demonstrate defect analysis, reporting quality, and testing coverage rather than expose the complete internal defect log.

---

## Key QA Findings

Testing identified recurring quality issues across several areas:

- Arabic localization and RTL inconsistencies
- Session and access-control validation gaps
- Data-isolation issues
- Incorrect application state handling
- Silent functional failures
- Inconsistent error and success feedback
- UI layout and usability problems

These findings demonstrate the importance of combining **functional testing with exploratory, localization, session, data-integrity, and access-control validation**.

---

## Confidentiality

Project and product names have been generalized to protect confidentiality.

Only **sanitized and representative** defect reports are included in this public repository.

The following information is intentionally excluded:

- Internal URLs
- Credentials and tokens
- User or customer data
- Internal identifiers
- Sensitive system information
- Client-identifying information
- Detailed security-sensitive reproduction information

The complete internal defect log is maintained privately in a structured Excel workbook and is **not published publicly**.
