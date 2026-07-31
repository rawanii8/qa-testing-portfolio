# QA Testing Portfolio

A collection of hands-on Software Quality Assurance and Testing work across real-world web and mobile applications — active, in-development products, not sample or practice exercises.

**Note on project names:** Project names below are generalized rather than using real company/product names or client-identifying details, to respect confidentiality of the platforms tested.

This portfolio demonstrates:
- Manual testing across web and mobile platforms
- API testing (Postman)
- Functional, regression, and exploratory testing
- Arabic localization/RTL testing
- Structured defect reporting and full defect lifecycle management
- Test design using Boundary Value Analysis (BVA) and Equivalence Partitioning (EP)

## Projects

### [Agricultural Management Platform](./agri-management-platform)
Agricultural/farm management system — iOS mobile app and web portal, Arabic-first interface.
**Testing:** Functional, regression, exploratory, Arabic localization/RTL, UI/UX, data integrity, security-related validation, cross-platform testing.

### [Workforce Management Portal](./workforce-management-portal)
Workforce management web platform covering attendance, tasks, leaves, communication, meetings, reports, and project management.
**Testing:** Functional, regression, exploratory, Arabic localization/RTL, session validation, data-isolation validation, permission/access validation, UI/UX, cross-browser.

### [Workforce Management Platform — Public Site](./workforce-management-public-site)
Public-facing marketing and pricing website for the platform above.
**Testing:** Functional testing, Arabic localization, RTL, navigation, buttons, links, page transitions, UI consistency.

### [Government Field-Task Management System](./government-task-app)
Government mobile application for field-task / process-server workflow management.
**Mobile Testing:** Functional, validation, negative testing, UI behavior, user workflows.
**API Testing:** Postman — REST API validation, authentication, request/response validation, HTTP status codes, input validation, negative/edge cases, endpoint debugging, error handling.

## My QA Approach

**Understand → Design → Execute → Report → Retest → Verify**

- Understand requirements and expected behavior before testing begins.
- Identify positive, negative, boundary, and edge cases.
- Execute functional and exploratory testing across the target platform.
- Report defects with clear reproduction steps and supporting evidence.
- Collaborate during triage to clarify root cause and expected fix.
- Retest fixes and perform regression checks on related areas.
- Verify closure before marking a defect resolved.

## Bug Reporting

Each defect is documented with a consistent structure:

- **Bug ID**
- **Title**
- **Severity**
- **Priority**
- **Description**
- **Preconditions** (where applicable)
- **Steps to Reproduce**
- **Actual Result**
- **Expected Result**
- **Environment**
- **Evidence** (where applicable)

**Defect lifecycle:** Discovery → Documentation → Triage → Fix Verification → Retesting → Closure

## Security-Related Wording

Testing described in this portfolio refers to **security-related validation** performed as part of standard QA activity — such as session validation, permission/access-control validation, and authentication testing. This is not penetration testing, vulnerability assessment, or advanced security/cybersecurity testing.

## Tools

| Category | Tools |
|---|---|
| Bug Tracking | Jira, Trello, Zephyr Scale |
| API Testing | Postman |
| Version Control | Git, GitHub |
| Database | SQL |
| Automation (in progress) | Selenium WebDriver |
| Documentation | Excel, Google Sheets |

## Repository Structure

```
project/
├── README.md
└── bug-reports/
    ├── BUG-001.md
    ├── BUG-002.md
    └── ...
```

Each project's `README.md` covers its scope, modules/features tested, testing types, defect categories, and key findings. The `bug-reports/` folder contains a representative, sanitized sample of documented defects — not the complete internal log, and with any client-identifying or system-sensitive details removed or generalized.

**Note:** Full bug logs are maintained privately in structured spreadsheets and are available on request. They are not published here.
