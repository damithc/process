# Reviewing PRs

A typical PR must be reviewed by,
 * one lead member (i.e. the main reviewer)
 * PM

Additional reviewers may be used if the PR involves multiple areas.
Junior members can get their PR peer reviewed by another junior member before submitting to the projects formal 
review process.

## Review procedure

A reviewer must do the following steps.

1. Ensure the the following at the start of the review. If any of them are missing, ask the dev to fix.
  * PR name follows the [PR title convention](FormatsAndConventions.md#pr). 
  * PR description has the correct `Fixes #...` reference.
  * The CI build is successful or any failures are justifiable (e.g. false positives from static analysis tools) 
  * Ensure the branch is up to date with the `master` branch.
  * PR branch name follows the [branch naming convention](FormatsAndConventions.md#branch). 
  
    > 'Incorrect branch name' can be forgiven for those doing their first issue, 
    >  but remind the dev to follow the convention in future PRs.
  
1. Ensure the following:
  * The solution is the best possible solution to the problem under the circumstances.
  * **All five aspects** of a code change are done:
    1. **Code**
    1. **Comments** e.g. header comments
    1. **Tests**:  Almost all code changes to functional code should have changes to test code.
    1. **User docs** e.g. help pages.
    1. **Dev docs** e.g. design diagrams
  * Coding style and best practices are followed (some of these are not detected by static analysis tools)
  * The PR does not contain unrelated changes. 
      e.g. unnecessary formatting changes or commits from other branches.

1. Use [GitHub's review feature] to add comments.
   * Do not use `Approve` unless you are fully satisfied with the current state of the PR. <br>
   i.e. NOT allowed: `Let me approve this first while you fix the remaining minor problems`.

## Tips for reviewers

* **To hide white space changes from being shown in the diff**, 
  append `?w=1` to url of the `/files` page of the pull request (the "Files changed" tab)

* **If the PR is too big**, explore the possibility of breaking the PR into multiple self-containing steps
  as explained in [Creating commits in big PRs](AdvancedContributorGuidelines.md#creating-commits-in-big-prs)here. 
  If the intermediate steps are not releasable, 
  [long-lived feature branches](HowToGuides.md#implement-big-features-using-long-lived-feature-branches)
  should be used instead.

## Canned comments

// TODO: add common comments that can be used when reviewing