# Government Field-Task Management System — Mobile App Testing

**Platform:** Mobile application (government field-task / process-server workflow system)
**Testing scope:** Manual functional testing and API testing

## Categories Covered

- **Authentication / Session-Related Validation** — password-change flow validation gaps
- **Functional** — offline map download handling, search not triggering on single-character input, lost photo attachment on navigation, progress bar step counter shown in reversed order
- **Validation** — unrestricted input on identity fields and date fields accepting past dates
- **Localization** — task status badge left in English during Offline Mode
- **UI/UX** — missing required-field indicators, low-contrast active navigation state, inconsistent icon states, missing month names in date picker

## Manual Testing

Performed functional testing on the mobile application, documenting defects with a bug report format adapted for a mobile-only app. Bug reports followed the same structure used across other projects: Description, Preconditions (where relevant), Steps to Reproduce, Actual Result, Expected Result, Environment.

## API Testing (Postman)

Tested backend REST endpoints supporting the mobile app using Postman — covering functional, validation, authentication, error-handling, and negative testing across login, task management, lookups, status updates, and location history endpoints.

Key findings included a task update endpoint failing due to a request sending task IDs as integers instead of the strings the API expected, along with several validation gaps and unhandled backend exceptions surfaced through negative testing.

See [`api-testing.md`](./api-testing.md) for the full API test report.

## Sample Bug Reports

See [`bug-reports/`](./bug-reports) for a representative sample of documented defects. A small number of higher-sensitivity findings (e.g., a critical authentication issue that was reported and remediated) are intentionally excluded from this public sample and summarized only at a high level, without reproduction detail, out of caution given the nature of this system.
