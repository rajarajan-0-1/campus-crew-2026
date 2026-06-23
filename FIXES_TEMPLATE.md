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
