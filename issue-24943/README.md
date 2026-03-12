# [Oppia #24943] BUG: Next Lesson Button Style Regression

**Link to Issue:** [Issue #24943](https://github.com/oppia/oppia/issues/24943)  
**Branch Name:** `fix-issue-24943-button-style`

###  Problem
On the lesson completion page, the "Next Lesson" button appears as a blank white square, making it invisible to learners. This is a critical UI bug as it prevents smooth navigation to the next lesson.

###  Investigation (Root Cause)
By inspecting the DOM and the CSS source code, I identified a typo in the stylesheet:
* **File:** `new-conversation-skin.component.css` (or related button stylesheet)
* **Error:** The selector was targeting `.mat-raised-raised`.
* **Actual Class:** Angular Material generates the class `.mat-raised-button`. 
* **Result:** Because of the selector mismatch, the intended background color and contrast styles were never applied.

###  Proposed Solution
* Correct the CSS selector from `.mat-raised-raised` to `.mat-raised-button`.
* Ensure that the `oppia-new-button-raised` class properly overrides the default Angular Material background color to maintain Oppia's brand consistency.

### Status & Comments
* **Current Status:** Investigated / Fix Prepared.
* **Situation:** The issue is currently assigned to another contributor (`tanmaygoyal2007`). I have commented on the issue providing the root cause analysis and am standing by to take over if the current assignee becomes inactive.
* **GSoC Learning:** Improved skills in browser DevTools for debugging CSS selector specificity and Angular Material component styling.
