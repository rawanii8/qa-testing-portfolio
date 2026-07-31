# Workforce Management Portal — QA Bug Log

**Platform:** Web (HR / workforce management portal)
**Domain:** Employee attendance, tasks, leaves, communication, meetings, reports, and project management
**Bug tracking tool:** Trello

## Categories Covered

- **Localization / RTL** — untranslated English strings ("...Loading", status labels, filter labels), raw i18n translation keys and backend enum values surfaced to users, incorrect RTL text/date ordering, mixed-language corrupted strings
- **Functional** — broken session/logout handling, non-functional buttons and icons, notifications not triggering, infinite loading states, timers resetting unexpectedly, features silently failing after a false "success" message
- **Session/Permission/Access-Control Validation & Data Integrity** — session termination not actually revoking access, one employee's data leaking into another's filtered view, internal technical notes exposed to end users, data being overwritten without warning
- **UI/UX** — overlapping and clipped elements in RTL layout, misaligned components, low-contrast text, inconsistent formatting across pages

## Manual Testing

Testing covered multiple modules across the portal — Communication, Notifications, Shifts, Leaves, Meetings, Reports & Export, Screenshots, Team Dashboard, Projects/Kanban, and Login/Authentication — with bug reports logged directly in Trello following a structured format: Title, Severity, Priority, Description, Steps to Reproduce, Actual Result, Expected Result, and Environment.

## Sample Bug Reports

See [`bug-reports/`](./bug-reports) for a representative sample spanning critical crashes, session/data-isolation validation issues, functional defects, and localization/RTL problems. The full bug log is maintained in a structured Excel workbook and available on request.
