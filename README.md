# QA Testing Portfolio

A collection of hands-on **Software Quality Assurance and Testing work** across real-world web and mobile applications.

This portfolio demonstrates practical experience in **manual testing, API testing, test design, Arabic localization/RTL validation, structured defect reporting, and end-to-end defect lifecycle management**.

> **Note on Project Names:** Project names have been generalized to protect company, product, and client confidentiality. The testing activities and QA work represented are based on real-world testing experience.

---

## Projects

### [Agricultural Management Platform](./agri-management-platform)

Agricultural management system consisting of an iOS mobile application and web portal with an Arabic-first interface.

**Testing Areas:**
- Functional Testing
- Regression Testing
- Exploratory Testing
- Arabic Localization & RTL
- UI/UX Validation
- Data Integrity Validation
- Security-Related Validation
- Cross-Platform Testing

---

### [Workforce Management Portal](./workforce-management-portal)

Workforce management web platform covering attendance, tasks, leaves, communication, meetings, reports, and project management.

**Testing Areas:**
- Functional Testing
- Regression Testing
- Exploratory Testing
- Arabic Localization & RTL
- Session Validation
- Data-Isolation Validation
- Permission & Access-Control Validation
- UI/UX Testing
- Cross-Browser Testing

**Key Defect Areas:**
- Functional workflow issues
- Session-related issues
- Data-isolation problems
- Permission and access-control issues
- Arabic localization and RTL inconsistencies

---

### [Workforce Management Platform — Public Site](./workforce-management-public-site)

Public-facing marketing and pricing website associated with the workforce management platform.

**Testing Areas:**
- Functional Testing
- Arabic Localization
- RTL Validation
- Navigation Testing
- Button & Link Validation
- Page Transition Testing
- UI Consistency

---

### [Government Field-Task Management System](./government-task-app)

Government mobile application supporting field-task and process-server workflows.

#### Mobile Testing

- Functional Testing
- Validation Testing
- Negative Testing
- UI Behavior
- User Workflow Testing

#### API Testing

**Postman**
- REST API Validation
- Authentication Testing
- Request & Response Validation
- HTTP Status Code Validation
- Header Validation
- Input Validation
- Negative & Edge-Case Testing
- Endpoint Debugging
- Backend Error-Handling Validation

---

## QA Approach

### Understand → Design → Execute → Report → Retest → Verify

My testing approach focuses on understanding expected behavior, identifying meaningful test scenarios, executing tests systematically, and providing clear feedback throughout the defect lifecycle.

- Understand requirements and expected behavior.
- Identify positive, negative, boundary, and edge-case scenarios.
- Design and execute relevant test cases.
- Perform functional and exploratory testing across the target platform.
- Document defects with clear reproduction steps and supporting evidence.
- Participate in defect triage and clarification.
- Retest fixes and perform regression checks on related areas.
- Verify resolved defects before closure.

---

## Test Design Techniques

I apply structured test design techniques to improve test coverage and identify edge cases, including:

- **Boundary Value Analysis (BVA)**
- **Equivalence Partitioning (EP)**
- Positive & Negative Testing
- Boundary & Edge-Case Testing
- Validation Testing
- End-to-End Workflow Testing

---

## Bug Reporting

Defects are documented using a consistent and developer-friendly structure:

- **Bug ID**
- **Title**
- **Severity**
- **Priority**
- **Description**
- **Preconditions** — where applicable
- **Steps to Reproduce**
- **Actual Result**
- **Expected Result**
- **Environment**
- **Evidence** — where applicable

### Defect Lifecycle

**Discovery → Documentation → Triage → Fix Verification → Retesting → Regression → Closure**

The goal is to provide defects that are **clear, reproducible, actionable, and easy to verify**.

---

## Security-Related Validation

Security-related testing documented in this portfolio refers to validation performed as part of standard QA activities, including:

- Authentication testing
- Session validation
- Permission and access-control validation
- Data-isolation validation

This portfolio does **not** represent penetration testing, vulnerability assessment, or advanced cybersecurity testing.

---

## Tools

| Category | Tools |
|---|---|
| Bug Tracking | Jira, Trello, Zephyr Scale |
| API Testing | Postman |
| Test Design | BVA, EP |
| Version Control | Git, GitHub |
| Database | SQL |
| Automation | Selenium WebDriver — currently learning |
| Documentation | Excel, Google Sheets |

---

## Repository Structure

```text
project/
├── README.md
└── bug-reports/
    ├── BUG-001.md
    ├── BUG-002.md
    ├── BUG-003.md
    └── ...
