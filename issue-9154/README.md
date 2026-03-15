# [Oppia #9154] Refactor: Removing Static Variables from Core Services

**Link to PR:** [PR #24995](https://github.com/oppia/oppia/pull/24995)  
**Branch Name:** `fix-9154-submission`  
**Status:**  Approved (LGTM) |  Merge Queue Battle

###  Problem
As part of the Angular migration, legacy services used static class variables to maintain state. This caused "state leakage" and made unit testing difficult because static variables persist across tests. Issue #9154 required transitioning these to instance-based properties.

###  Solution
* **Refactored Core Services:** Removed static variables from `LoaderService`, `i18nLanguageCodeService`, `CollectionCreationService`, and `AlertsService`.
* **Singleton Pattern:** Transitioned services to use proper Angular dependency injection, ensuring they act as true singletons without relying on the `static` keyword.
* **TODO(8472) Integration:** Successfully integrated the cleanup of alert messages and warnings using getters, as requested during the review process.

###  Challenges & Resolution
* **The Merge Queue Struggle:** The PR has entered the Merge Queue three times. It faced timeouts and "higher priority" sync issues in the CI pipeline.
* **Sync Issues:** Addressed a massive sync pollution (16,000 commits) by carefully updating the branch from `upstream/develop`.
* **Technical Persistence:** Worked closely with maintainers (@Nik-09, @KartikSuryavanshi) to verify that backend shard failures were pre-existing and unrelated to my refactor.

###  Status & Comments
* **Nik-09:** "LGTM" (Looks Good To Me).
* **KartikSuryavanshi:** "If it fails a third time, we’ll go ahead and force merge it."
* **Learning:** Gained deep experience in Angular service lifecycles, CI/CD pipeline management, and handling complex PR synchronization in large-scale repositories.
** MERGED AND CLOSED **
  ** THANKYOU**
