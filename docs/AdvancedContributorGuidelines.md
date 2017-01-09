# Advanced Contributor Guidelines

## Choosing issues

* Follow issue priorities. Prefer to take higher priority issues over lower priority issues.
* Favor issues related to certain features/aspects/techs to deepen expertise in those areas. 
 
## Updating a PR in response to a review
  
* If the `master` has progressed beyond the root of the PR branch, rebase the PR branch 
  (instead of merging `master` to PR branch). This will keep the PR branch free of merge commits.
* Commits done to fix problems mentioned in the review should be squashed onto the relevant existing commits in the 
  branch (if applicable).
* Post a new commit summary (if applicable) when the PR is ready for another review. Here is an example.

  ```
  v2
  Rework tests so that they do not depend on new Task().
  
  [1/5] TaskBook::resetData(): replace floating/event/deadline task data as well - Unchanged
  [2/5] logic: remove non-TaskTracker related commands - Unchanged
  [3/5] testutil: remove SerializableTestClass - Unchanged
  [4/5] testutil: unify two equality methods - New
  [4/5] testutil: remove TaskBookBuilder - Updated
  ```