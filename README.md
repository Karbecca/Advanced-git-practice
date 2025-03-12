# Part 1: Refining Git History (10 Challenges)

## Challenge 1: Missing File Fix

1. **Check the current repository status**
   ```bash
   git status
   ```

# OUTPUT:

```
$ git status
On branch main
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test4.md

no changes added to commit (use "git add" and/or "git commit -a")
```

## 2.Stage the missing file

To stage the missing file (test4.md):

```
git add test4.md
```

## 3.Amend the last commit

amend the previous commit to include the missing file:

```
git commit --amend -m "Add missing test4.md file"
```

## Challenge 1: Editing Commit History:

```
git rebase -i HEAD~2
[main 61e76c9] Saving changes before rebase
 2 files changed, 30 insertions(+)
 create mode 100644 test4.md
```

## Challenge 2:Keeping History Tidy - Squashing Commits:

```
git rebase -i HEAD~2
```

## Challenge 3:Splitting a Commit:

```
git reset HEAD~1
git add test3.md
git commit -m "chore: Create third file"
git add test4.md
git commit -m "chore: Create fourth file"

```

## Challenge 4: Advanced Squashing:

```
git rebase -i HEAD~2
```

## Challenge 5:

```
git rebase -i HEAD~2
```

## Challenge 6:Dropping a Commit:

```
touch unwanted.txt
git add unwanted.txt
git commit -m "Unwanted commit"
git rebase -i HEAD~1
```

# OUTPUT:

```
[detached HEAD 99b4913] Unwanted commit
 2 files changed, 65 insertions(+)
 create mode 100644 unwanted.txt
fatal: It seems that there is already a rebase-merge directory, and
I wonder if you are in the middle of another rebase.  If that is the
case, please try
        git rebase (--continue | --abort | --skip)
If that is not the case, please
        rm -fr ".git/rebase-merge"
and run me again.  I am stopping in case you still have something
valuable there.
```

## Challenge 7: Reordering Commits:

```
git rebase -i HEAD~3

```

## Challenge 8:Cherry-Picking Commits

```

git checkout -b ft/branch
touch test5.md
git add test5.md
git commit -m "Implemented test 5"
git checkout main
git cherry-pick <commit-hash>

```

## Challenge 9: Visualizing Commit History (Bonus)

```
git log --graph --oneline --all

```

# OUTPUT:

```
 8669561 (HEAD -> ft/branch) Implemented test 5
* 99b4913 Unwanted commit
* 585442d chore: Create fourth file
| * 61e76c9 (origin/main, main) Saving changes before rebase
|/
* 20280db chore: Create third and fourth files
* 8810785 chore: Create another file
* 886e745 chore: Create initial file
:
```

## Challenge 10: Understanding Reflogs (Bonus):

```

git reflog
git reset --hard HEAD@{n}

```

# OUTPUT:

```

8669561 (HEAD -> ft/branch) HEAD@{0}: commit: Implemented test 5
99b4913 HEAD@{1}: checkout: moving from 99b4913f30bc5731405cab6205becbfef176e737 to ft/branch
99b4913 HEAD@{2}: commit: Unwanted commit
585442d HEAD@{3}: commit: chore: Create fourth file
20280db HEAD@{4}: reset: moving to HEAD~1
61e76c9 (origin/main, main) HEAD@{5}: rebase (start): checkout HEAD~2
61e76c9 (origin/main, main) HEAD@{6}: commit: Saving changes before rebase
20280db HEAD@{7}: commit: chore: Create third and fourth files
:
```

### Part 2: Branching Basics (10 Challenges)

## 1. Feature Branch Creation:

OUTPUT:

```
$ git checkout -b ft/new-feature
Switched to a new branch 'ft/new-feature'
```

## 2.Working on the Feature Branch:

OUTPUT:

```
$ echo "Feature content" > feature.txt
git add feature.txt
git commit -m "Implemented core functionality for new feature"
warning: in the working copy of 'feature.txt', LF will be replaced by CRLF the next time Git touches it
[ft/new-feature 99ec44e] Implemented core functionality for new feature
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt

```

## 3.Switching Back and Making More Changes:

OUTPUT:

```
git checkout main
echo "Project Introduction" > readme.txt
git add readme.txt
git commit -m "Updated project readme"
 1 file changed, 1 insertion(+)
 create mode 100644 readme.txt
```

## 4.Local vs. Remote Branches:

OUTPUT:

```
git push origin ft/new-feature

Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 4 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (6/6), 545 bytes | 272.00 KiB/s, done.
Total 6 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (2/2), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/new-feature' on GitHub by visiting:
remote:      https://github.com/Karbecca/Advanced-git-practice/pull/new/ft/new-feature
remote:
To https://github.com/Karbecca/Advanced-git-practice.git
 * [new branch]      ft/new-feature -> ft/new-feature
```

## 5.Branch Deletion:

OUTPUT:

```bash
 git branch -d ft/new-feature
Deleted branch ft/new-feature (was f989d92).
```

git branch -d ft/new-feature
Deleted branch ft/new-feature (was f989d92).

````
## 6.Creating a Branch from a Commit:

OUTPUT:

```bash
$ git checkout -b ft/new-branch-from-commit f989d92
Switched to a new branch 'ft/new-branch-from-commit
````

## 7. Branch Merging:

OUTPUT:

```bash
git merge ft/new-branch-from-commit

```

## 8. Branch Rebase:

OUTPUT:

```bash
$ git rebase --continue
Successfully rebased and updated refs/heads/ft/new-branch-from-commit.
```

## 9.Renaming Branches:

OUTPUT:

```bash
git branch -m ft/new-branch-from-commit ft/improved-branch-name

```

### Part 3

## 1. Stashing Changes:

OUTPUT:

```bash
$ git stash
Saved working directory and index state WIP on main: c574ec8 edited read me
```

## 2. Retrieving Stashed Changes:

OUTPUT:

```bash
no changes added to commit (use "git add" and/or "git commit -a")
Dropped refs/stash@{0} (9866661162c5aeb119cf2c4a5ae916936a2ef974)
```

## 3.Simulating a Merge Conflict

OUTPUT:

```bash
$ git checkout -b feature-branch
Switched to a new branch 'feature-branch

$ echo "Hello from feature branch" >> conflict.txt
git add conflict.txt
git commit -m "Feature branch changes"
warning: in the working copy of 'conflict.txt', LF will be replaced by CRLF the next time Git touches it
[feature-branch fcb62a0] Feature branch changes
 1 file changed, 1 insertion(+)

 $ git add conflict.txt
git commit -m "Resolved merge conflict"
[main a8d4f05] Resolved merge conflict

```

## 4. Resolving Merge Conflicts with a Merge Tool:

OUTPUT:

```bash

This message is displayed because 'merge.tool' is not configured.
See 'git mergetool --tool-help' or 'git help config' for more details.
'git mergetool' will now attempt to use one of the following tools:
opendiff kdiff3 tkdiff xxdiff meld tortoisemerge gvimdiff diffuse diffmerge ecmerge p4merge araxis bc codecompare smerge emerge vimdiff nvimdiff
No files need merging
```

## 5.Understanding Detached HEAD State:

OUTPUT:

```bash
Merge: f353615 b6a1892
Author: karbecca <karbecca3@gmail.com>
Date:   Wed Mar 12 12:02:21 2025 +0200

    Merge branch 'ft/Newimproved-branch-name'
```

## 6. Ignoring Files/Directories:

OUTPUT:

## 7. Working with Tags

```bash
*.log
bash: /tmp: Is a directory

$ git push origin v1.0
Enumerating objects: 10, done.
Counting objects: 100% (10/10), done.
Delta compression using up to 4 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (6/6), 843 bytes | 843.00 KiB/s, done.
Total 6 (delta 4), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (4/4), completed with 2 local objects.
To https://github.com/Karbecca/Advanced-git-practice.git
 * [new tag]         v1.0 -> v1.0

```

## 8.Listing and Deleting Tags:

OUTPUT:

```bash
 git tag -d v1.0
git push origin --delete v1.0  # Remove from remote
Deleted tag 'v1.0' (was ea4e745)
To https://github.com/Karbecca/Advanced-git-practice.git
 - [deleted]         v1.0

```

## 9. Pushing Local Work to Remote:

OUTPUT:

```bash
git push origin main
Enumerating objects: 10, done.
Counting objects: 100% (10/10), done.
Delta compression using up to 4 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (6/6), 843 bytes | 843.00 KiB/s, done.
Total 6 (delta 4), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (4/4), completed with 2 local objects.
To https://github.com/Karbecca/Advanced-git-practice.git
   f353615..ea4e745  main -> main
```

## 10. Pulling Changes from Remote:

OUTPUT:

```bash
$ git pull origin main
From https://github.com/Karbecca/Advanced-git-practice
 * branch            main       -> FETCH_HEAD
Already up to date.
```
