# Part 1: Refining Git History (10 Challenges)

## Challenge 1: Missing File Fix

1. **Check the current repository status**
   ```bash
   git status
   ```

## OUTPUT:

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

## Challenge 2: Editing Commit History:

```
git rebase -i HEAD~2
[main 61e76c9] Saving changes before rebase
 2 files changed, 30 insertions(+)
 create mode 100644 test4.md
```

## Challenge 3:Keeping History Tidy - Squashing Commits:

```
git rebase -i HEAD~2
```

## Challenge 4: 4. Splitting a Commit:

```

```
