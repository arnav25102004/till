# [Oppia #14966] Apache Beam Migration

**Link to Issue:** [Issue #14966](https://github.com/oppia/oppia/issues/14966)  
**Branch Name:** `migration-beam-job-14966`

### Problem
Migrating legacy Python "One-Off" audit jobs to the Apache Beam framework to support parallel processing and better data validation at scale.

###  Solution
* Created a Beam pipeline to audit exploration models.
* Implemented `PTransforms` to filter and validate data structures.
* Handled cleanup logic for non-compliant models.

###  Status & Comments
Currenlty waiting for assignment 
