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


```
