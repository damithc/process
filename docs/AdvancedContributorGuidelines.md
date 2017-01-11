# Advanced Contributor Guidelines

## Choosing issues

* Follow issue priorities. Prefer to take higher priority issues over lower priority issues.
* Favor issues related to certain features/aspects/techs to deepen expertise in those areas. 
 
## Updating a PR in response to a review
  
* If the `master` has progressed beyond the root of the PR branch, rebase the PR branch 
  (instead of merging `master` to PR branch). This will keep the PR branch free of merge commits.
* If the PR is not in [multi-step](HowToGuides.md#create-a-multi-step-pr) format, commit each requested
  change as a separate commit. That way, the reviewer can compare the new commits against the changes requested.
  
  > The multi-step PR format requires some of the changes to be squashed onto existing commits.