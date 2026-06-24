# Fixes Summary

Name: RAJARAJAN K R
Registration number: 73152321042
Time spent: 

## Bugs fixed

For each item, include the broken behavior, files changed, and how you verified the fix.

1. Issue: Application failed to start and    dashboard rendering was broken.

Files changed:
- package.json
- src/App.jsx

Explanation:
- Added missing Vite development script.
- Added missing react-dom dependency.
- Fixed incorrect assignment operator in dashboard conditional rendering.

Verification:
- Application starts successfully with npm run dev.
- Dashboard renders without runtime errors.

2. Issue: Sidebar navigation always opened Dashboard regardless of selected menu item.

Files changed:
- src/components/Sidebar.jsx

Explanation:
- Updated navigation click handler to use the selected item's id instead of hardcoding 'dashboard'.
- Closed the sidebar after selecting a menu item for better mobile usability.

Verification:
- Dashboard, Assignments, and Announcements tabs now open correctly.
- Active tab highlighting works as expected.
- Sidebar closes after navigation on mobile.

3. Issue: Student search was case-sensitive and did not handle extra spaces.

Files changed:
- src/App.jsx

Explanation:
- Normalized both the search query and student names using trim() and toLowerCase() before comparison.

Verification:
- Search now works with uppercase, lowercase, mixed case, and leading/trailing spaces.

4. Issue: Department filter did not correctly filter students.

Files changed:
- src/App.jsx

Explanation:
- Corrected department comparison logic to compare the selected department with each student's department.

Verification:
- Confirmed each department option displays only the relevant students.
- Verified "All" displays all students.

5. Issue: Open Assignments displayed completed assignments instead of pending ones.

Files changed:
- src/App.jsx

Explanation:
- Updated filtering logic to show only incomplete assignments in the Open Assignments section.

Verification:
- Confirmed completed assignments are excluded.
- Confirmed pending assignments remain visible.

6. Issue: Incorrect average project progress calculation.

Files changed:
- src/App.jsx

Fix:
- Replaced student-based calculation with assignment completion ratio.
- Calculated percentage as completed assignments / total assignments * 100.
- Added safe check for empty assignment list.

Verification:
- Progress updates correctly when toggling assignments.
- Value always stays between 0 and 100.

7. Issue: General quality, stability, and UX improvements.

Files changed:
- src/App.jsx

Fixes:
- Improved student search to be case-insensitive and whitespace-safe.
- Fixed department filter trimming issues.
- Eliminated all direct state mutations in assignment toggle.
- Added predictable assignment sorting by due date.
- Fixed theme persistence to avoid overwriting body classes.
- Improved safety checks for empty datasets.
- Ensured average progress calculation is stable and non-breaking.

Enhancements:
- Added ESC key support for closing student modal.
- Improved overall React rendering stability and data safety.

Verification:
- Search works with any casing and spacing.
- Assignments update instantly without reload issues.
- UI remains stable across navigation and refresh.

8. Issue: Assignment creation via form

Files changed:
- src/components/NewAssignmentForm.jsx
- src/App.jsx 

Fixes:
- Fixed form fields not overwriting each other while typing.
- Corrected validation for required fields.
- Reset form after successful submission.
- Fixed state update for adding new assignments safely.

Enhancements:
- Added proper success/error messages.
- New assignments appear instantly in UI.
- Improved overall form stability and UX.

Verification:
- Form works correctly without input issues.
- Validation blocks empty submissions.
- Form resets after create.
- New assignment shows immediately in list.

## UI improvements made

Only list improvements that directly support the assignment requirements.

-
-
-

## Out-of-scope changes

List any intentional refactors or behavior changes that were not directly required. Write `None` if you did not make any.

-

## Testing performed

- Desktop: 
- Tablet:
- Mobile:
- Browser console checked:
- Refresh/persistence checked:

## Known limitations

-
