# [Mobile] Functional Bug: Search on Daily Tasks Screen Does Not Trigger on Single-Character Input

**Severity:** Low
**Priority:** Low

## Description
The search functionality on the Daily Tasks (مهامي اليومية) screen does not start filtering results when the user enters a single character. Instead, the search is only triggered after entering two or more characters. This prevents users from performing searches with a single-letter query and results in inconsistent search behavior.

## Preconditions
The user is logged into the application.
The user has accessed the Daily Tasks (مهامي اليومية) screen.
The task list contains items that can be searched.

## Steps to Reproduce
1. Navigate to the Daily Tasks (مهامي اليومية) screen.
2. Tap on the search field.
3. Enter a single character (e.g., "ل").
4. Observe the search results.
5. Enter a second character.

## Actual Result
The search is not triggered after entering a single character. Results are filtered only after the user enters two or more characters.

## Expected Result
The search should start filtering and displaying matching results immediately after the user enters the first character.
