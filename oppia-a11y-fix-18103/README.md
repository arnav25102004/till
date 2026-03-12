# [Oppia #18103] Accessibility Fix: Schema-Based List Editor

**Link to Issue:** [Issue #18103](https://github.com/oppia/oppia/issues/18103)  
**Branch Name:** `fix-issue-18103-accessibility`

###  Problem
* **Duplicate IDs:** The `e2e-test-schema-based-list-editor-table-row` ID was duplicated because it was used inside an `*ngFor` loop without unique identifiers.
* **Missing Labels:** The "Add" and "Delete" buttons lacked descriptive labels, making them unusable for screen reader users.

###  Solution
* **Dynamic IDs:** Implemented Angular property binding `[id]` to append the loop index (`idx`) to the ID string.
* **ARIA Labels:** Added `aria-label` for the Delete button and a translated `[aria-label]` for the Add button.

###  Status & Comments
* **Current Status:** Awaiting Assignment / PR Submission.
* **Reviewer Comments:** None yet; issue was self-identified as a priority for GSoC '26.
* **Verification:** 19/19 Frontend tests passed; HTML linting passed.
