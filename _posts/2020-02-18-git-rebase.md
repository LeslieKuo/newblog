
When you forget to new a branch and make some changes in the existing branch.
you can do this

```
git stash.  // save changes to stash and recover the branch
git checkout master//
git pull --rebase // prevent merge the remote commit and local commit. And the commit line will be a string.
git checkout -b xxxx. // Now new your branch
git stash pop // restore the stash to new branch

```
Example below
```
guoliang@guoliangs-MacBook-Pro:~/my-workspace/metering/repo/HCDataManager (13a30db*) % g stash    Saved working directory and index state WIP on (no branch): 13a30db separate iam
guoliang@guoliangs-MacBook-Pro:~/my-workspace/metering/repo/HCDataManager (13a30db$) % gco master
Previous HEAD position was 13a30db separate iam
Switched to branch 'master'
Your branch is up to date with 'origin/master'.
guoliang@guoliangs-MacBook-Pro:~/my-workspace/metering/repo/HCDataManager (master$=) % gl -r     
Already up to date.
Current branch master is up to date.
guoliang@guoliangs-MacBook-Pro:~/my-workspace/metering/repo/HCDataManager (master$=) % gcb fix-IAM-redundant-logging
Switched to a new branch 'fix-IAM-redundant-logging'
guoliang@guoliangs-MacBook-Pro:~/my-workspace/metering/repo/HCDataManager (fix-IAM-redundant-logging$) % git stash pop
Auto-merging lib/iam-token-manager.js
Auto-merging lib/iam-pap-manager.js
On branch fix-IAM-redundant-logging
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   lib/iam-pap-manager.js
        modified:   lib/iam-token-manager.js
        modified:   lib/iam-util.js
        modified:   lib/version-manager.js
        modified:   routes/index.js

no changes added to commit (use "git add" and/or "git commit -a")
Dropped refs/stash@{0} (db9304d2e0680ec9e9882aa76423420b708f67c8)
guoliang@guoliangs-MacBook-Pro:~/my-workspace/metering/repo/HCDataManager (fix-IAM-redundant-logging*) % git status   
On branch fix-IAM-redundant-logging
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   lib/iam-pap-manager.js
        modified:   lib/iam-token-manager.js
        modified:   lib/iam-util.js
        modified:   lib/version-manager.js
        modified:   routes/index.js

```
