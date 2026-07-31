# [Mobile] Functional Bug: Task Execution Progress Bar Displays Completed/Total Step Counter in Reversed Order

**Severity:** Medium
**Priority:** Medium

## Description
On the Task Execution (تنفيذ المهمة) screen, the progress bar step counter is displayed in reverse order. Instead of showing the number of completed steps out of the total steps (e.g., 31/33 مكتمل), the application displays 33/31 مكتمل. This makes it appear that the number of completed steps exceeds the total number of steps, resulting in a logical inconsistency and conflicting with the displayed 93% progress indicator.

## Preconditions
The user is assigned to a task with multi-step execution (e.g., Task #[Task ID]).

## Steps to Reproduce
1. Navigate to the Task Execution (تنفيذ المهمة) screen.
2. Open the details of Task #[Task ID].
3. Observe the progress bar and the numeric step counter displayed above it.

## Actual Result
The step counter is displayed as 33/31 مكتمل instead of 31/33 مكتمل, making it appear that the completed steps exceed the total number of steps and creating an inconsistency with the 93% progress indicator.

## Expected Result
The step counter should correctly display the number of completed steps out of the total number of steps in the standard format (e.g., 31/33 مكتمل). The completed steps should never exceed the total number of steps and should be consistent with the displayed progress percentage.
