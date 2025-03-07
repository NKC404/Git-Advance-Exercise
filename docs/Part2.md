# Part 2: Branching Basics

## 1. Feature Branch Creation

**Challenge:** Create a new branch named `ft/new-feature` and switch to that branch.

```sh
PS C:\Users\Clement\Desktop\TheExe\Git-Advance-Exercise> git checkout -b ft/new-feature
Switched to a new branch 'ft/new-feature'
```

## 2. Working on the Feature Branch

**Challenge:** Create a new file named feature.txt in this branch and add some content to it.
Commit these changes with a descriptive message like "Implemented core functionality for new feature".

```sh
PS C:\Users\Clement\Desktop\TheExe\Git-Advance-Exercise> New-Item feature.txt -ItemType File

PS C:\Users\Clement\Desktop\TheExe\Git-Advance-Exercise> git add feature.txt
PS C:\Users\Clement\Desktop\TheExe\Git-Advance-Exercise> git commit -m "feat: Implemented core functionality for new feature"
[ft/new-feature 37f0b5d] feat: Implemented core functionality for new feature
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt
```

3. Switching Back and Making More Changes

**Challenge:** Switch back to the main branch, create a new file named readme.txt, and commit with "Updated project readme".

```sh
PS C:\Users\Clement\Desktop\TheExe\Git-Advance-Exercise> git switch main
Switched to branch 'main'

PS C:\Users\Clement\Desktop\TheExe\Git-Advance-Exercise> New-Item readme.txt -ItemType File

PS C:\Users\Clement\Desktop\TheExe\Git-Advance-Exercise> git add readme.txt
PS C:\Users\Clement\Desktop\TheExe\Git-Advance-Exercise> git commit -m "docs: Updated project readme"
[main 5b1a44d] docs: Updated project readme
 create mode 100644 readme.txt
 ```

4. Local vs. Remote Branches

**Challenge:** Push ft/new-feature to the remote repository.

```sh
PS C:\Users\Clement\Desktop\TheExe\Git-Advance-Exercise> git push origin ft/new-feature
Enumerating objects: 4, done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 338 bytes | 338.00 KiB/s, done.
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote: Create a pull request for 'ft/new-feature' on GitHub by visiting:
remote:      https://github.com/NKC404/Git-Advance-Exercise/pull/new/ft/new-feature
To https://github.com/NKC404/Git-Advance-Exercise.git
 * [new branch]      ft/new-feature -> ft/new-feature
 ```

5. Branch Deletion

**Challenge:** Delete the ft/new-feature branch once it is merged into main.

```sh
PS C:\Users\Clement\Desktop\TheExe\Git-Advance-Exercise> git branch -d ft/new-feature

error: the branch 'ft/new-feature' is not fully merged
hint: Disable this message with "git config advice.forceDeleteBranch false"

PS C:\Users\Clement\Desktop\TheExe\Git-Advance-Exercise> git branch -D ft/new-feature

Deleted branch ft/new-feature (was b367a7d).
To https://github.com/NKC404/Git-Advance-Exercise.git

PS C:\Users\Clement\Desktop\TheExe\Git-Advance-Exercise> git log --oneline

8284aaa (origin/main) docs: adding documentation for Part1(Refining Git History)
7db1d46 chore: Implemented test 5
bee7795 chore: Create third and fourth files
aba096a chore: initial commit
 ```

6. Creating a Branch from a Specific Commit

**Challenge:** Create ft/new-branch-from-commit from the commit two positions back.

```sh
PS C:\Users\Clement\Desktop\TheExe\Git-Advance-Exercise> git checkout -b ft/new-branch-from-commit HEAD~2
Switched to a new branch 'ft/new-branch-from-commit'
```

7. Branch Merging

**Challenge:** Merge ft/new-branch-from-commit into main.

```sh
PS C:\Users\Clement\Desktop\TheExe\Git-Advance-Exercise> git switch main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)
PS C:\Users\Clement\Desktop\TheExe\Git-Advance-Exercise> git merge ft/new-branch-from-commit
Already up to date.
```

8. Branch Rebasing

**Challenge:** Rebase ft/new-branch-from-commit onto main.

```sh
PS C:\Users\Clement\Desktop\TheExe\Git-Advance-Exercise> git switch ft/new-branch-from-commit
Switched to branch 'ft/new-branch-from-commit'

PS C:\Users\Clement\Desktop\TheExe\Git-Advance-Exercise> git rebase main
Successfully rebased and updated refs/heads/ft/new-branch-from-commit.

```

9. Renaming Branches

**Challenge:** Rename ft/new-branch-from-commit to ft/improved-branch-name.

```sh
PS C:\Users\Clement\Desktop\TheExe\Git-Advance-Exercise> git branch -m ft/new-branch-from-commit ft/improved-branch-name
```

10. Checking Out Detached HEAD

**Challenge:** Check out a specific commit in detached HEAD mode.

```sh
PS C:\Users\Clement\Desktop\TheExe\Git-Advance-Exercise> git checkout bee7795
HEAD is now at bee7795 chore: Create third and fourth files
```

To return to a branch:

```sh
PS C:\Users\Clement\Desktop\TheExe\Git-Advance-Exercise> git switch main
Switched to branch 'main'
```