## Content for Completed Assignment

### Using <code>push</code>, <code>pull</code>, <code>fetch</code>, and <code>merge</code>

Transfer file changes/updates between your local workspace and a remote repository with the following commands:

- **`git push`** – updates the remote repository with changes from your local or tracking branch
- **`git pull`** – retrieves changes from one branch and merges them into the current branch
- **`git fetch`** – imports the latest updates in a remote repository to your tracking branch
- **`git merge`** – combines specified changes from the tracking branch into the remote branch

> **Note**: A tracking branch is a local branch that has a direct origin/master relationship with a remote branch. When you use the commands listed above on a tracking branch, Git automatically knows from where to fetch and the target to merge it with.

Often `git push` and `git pull` are described as equivalent. This isn't entirely correct, since under the hood `git pull` does two things. `git push` takes our current branch, and checks to see whether or not there is a tracking branch for a remote repository connected to it. If so, our changes are taken from our branch and pushed to the remote branch. This is how code is shared with a remote repository, you can think of it as "make the remote branch resemble my local branch". This will fail if the remote branch has diverged from your local branch: if not all the commits in the remote branch are in your local branch. When this happens, your local branch needs to be synchronized with the remote branch with git pull or git fetch and git merge.`git fetch` again takes our current branch, and checks to see if there is a tracking branch. If so, it looks for changes in the remote branch, and pulls them into the tracking branch. It does not change your local branch. To do that, you'll need to do `git merge origin/master` (for the "master" branch) to merge those changes into your branch - probably also called "master".`git pull` simply does a `git fetch` followed immediately by `git merge`. This is often what we desire to do, but some people prefer to use git fetch followed by git merge to make sure they understand the changes they are merging into their branch before the merge happens.
