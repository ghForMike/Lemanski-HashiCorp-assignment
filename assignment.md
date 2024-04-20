## Content for Completed Assignment

### Using <code>push</code>, <code>pull</code>, <code>fetch</code>, and <code>merge</code>

Transfer file changes/updates between your local workspace and a remote repository with the following commands:

- [**`git push`**](https://git-scm.com/docs/git-push) – updates the remote repository with changes from your local or tracking branch
- [**`git pull`**](https://git-scm.com/docs/git-pull) – retrieves changes from one branch and merges them into the current branch
- [**`git fetch`**](https://git-scm.com/docs/git-fetch) – imports the latest updates in a remote repository to your tracking branch
- [**`git merge`**](https://git-scm.com/docs/git-merge) – combines specified changes from the tracking branch into the remote branch

> **Note**: A tracking branch is a local branch that has a direct origin/master relationship with a remote branch. When you use the commands listed above on a tracking branch, Git automatically knows from where to fetch and the target to merge it with.

The **push** command fetches the latest changes from the remote repository, then compares these with your local branch. If there is divergence —— the commits are out of sync, i.e. the local branch is missing changes in the remote branch —— the push fails, throwing an error, and the conflicts identified must first be reconciled before merging can proceed.

The **pull** command, by contrast, runs `git fetch` with any parameters you specify. Then, depending on the configuration options or command line flags you include, either `git rebase` or `git merge` is called automatically to reconcile any divergence between the two branches. However, merging divergent branches may lead to conflicts that cannot be resolved automatically, especially if changes have been made to the same file in both branches. When this happens, Git will ask you to resolve the conflicts manually.

Invoking `git fetch` updates the local repository with the latest changes from the remote repository. Although the changes are not merged into the current working branch, they are available for merging. Use the **fetch** command when you want to see any changes made to the remote repository since you last fetched or you want to update your local repository with the latest changes from a remote repository that you are not currently working on.

Using `git merge` combines changes from two or more branches into a single branch or multiple sequences of commits into one unified history. When you merge two branches, Git creates a new commit that represents the merge —— a merge commit —— which allows you to track the history of your repository. Merge conflicts that are not resolved automatically require you to manually edit the content before then committing your changes.
