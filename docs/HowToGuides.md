# How To ...

### Create a multi-step PR

Big PRs (i.e. PRs touching more than 100 lines) are hard to review. 
Using the _multi-step PR_ format explained below allows the review to be done incrementally.

1. Dev creates the PR branch consisting of a series of commits corresponding to a sequence of logical steps, 
   each step advancing the code base towards the end goal of the PR. The build must pass at each step 
   
   > Build-breaking commits in the version history hinder the ability to use `git bisect` for locating bugs.
   
   <details>
   <summary>Instructions</summary>
   
   * The ideal approach for creating a multi-step commit sequence: 
     * Plan the PR as a sequence of logical steps.
     * Implement each step, committing each step as a separate commit. 
       * Write detailed commit messages as if you were explaining your commit to a future developer.
       
        > Writing detailed commit messages is especially important for multi-step PRs because the commits will be 
        > preserved after merging (i.e. the branch will be merged using a merge commit instead of 'squash and merge')
        
       * You may have to `squash` trivial commits or reorder commits to make the steps more logical. 
   * Alternative approach:
     * Implement the fix, committing after each significant change.
     * After the fix is complete, refactor commits so the you have a commit sequence similar to what you would have 
       achieved in the ideal approach given above.
   </details>
   
1. When the PR is ready for review, dev posts a summary of commits using the 
   [CanIHasReview tool](https://github.com/pyokagan/canihasreview/).
    
    <details>
       <summary>Instructions</summary>
       
       1. Navigate to your PR. e.g. `https://github.com/se-edu/addressbook-level4/pull/237`.
       2. Replace github.com in the PR URL with canihasreview.herokuapp.com. The resulting URL should be 
          something like `https://canihasreview.herokuapp.com/se-edu/addressbook-level4/pull/237`.
       3. Click `Submit new iteration` button. It will post a summary of the PR similar to 
          [this example](https://github.com/se-edu/addressbook-level4/pull/209#issuecomment-270905049)
    </details>
       
1. The reviewer reviews one commit at a time, starting with the earliest commit. If the early commits require lot 
   of changes, she can omit reviewing later commits until the early commits are updated as per review.
      
1. After reach round of review, the dev _updates the existing commits_  (rather than add more commits)
   according to the review comments. 
   
   <details>
   <summary>Instructions</summary>
   
   * Commit your changes in separate commits.
   * Squash the new commits onto the relevant commits in the PR. New commits can remain if they introduce new
     logical changes that were not in the previous version, or if the reviewer recommended splitting existing commits.
   * Post the summary of the new version using the same CanIHasReview tool used earlier.
   </details>

### Hide white space changes from being shown in the GitHub diff 
  
Append `?w=1` to url of the `/files` page of the pull request (the "Files changed" tab)

### Remove unwanted modifications from a branch

// TODO

### Refactor commits

// TODO Reordering, squashing, editing commit message

### Update a PR with upstream changes

1. Update the `master` branch of your local clone. 
[Here](https://help.github.com/articles/syncing-a-fork/) are the instructions.

1. Push your `master` branch to your fork (if you are creating PRs using a fork).

1. Sync your branch with the `master` branch. This can be done in two ways:
   1. Merge `master` to your branch (recommended option for new contributors).
   1. Rebase the PR branch on the `master` branch (recommended option for experienced contributors). 

### Implement big features using long-lived feature branches

// TODO