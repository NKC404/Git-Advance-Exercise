# Part 1: Refining Git History

## Git Challenges: Enhancing Your Workflow

### 1. Fixing a Missing File
   ```sh
   git add test4.md
   git commit --amend -m "chore: Create third and fourth files"
   ```

   **Output:**
   ```sh
    Date: Fri Mar 7 11:50:01 2025 +0200
    2 files changed, 0 insertions(+), 0 deletions(-)
    create mode 100644 test3.md
    create mode 100644 test4.md
   ```

### 2. Editing Commit Messages
   ```sh
   git rebase -i HEAD~2
   ```
   **Output:**
   ```sh
    [detached HEAD aad832a] chore: Create second file
    1 file changed, 0 insertions(+), 0 deletions(-)
    Successfully rebased and updated refs/heads/main.
    HEAD~2
    Successfully rebased and updated refs/heads/main.
   ```

### 3. Squashing Commits
   ```sh
   git rebase -i HEAD~2
   ```
   **Output:**
   ```sh
    # chnge the pick in from of the "Create second file" commit with a squash, save and close and choose with commit message to put, save and close.
   ```


### 4. Splitting a Commit
   ```sh
   git reset HEAD~1
   git add test3.md
   git commit -m "chore: Create third file"
   git add test4.md
   git commit -m "chore: Create fourth file"
   ```
   **Output:**
   ```sh
    [main d57b6f5] chore: Create third file
    1 file changed, 0 insertions(+), 0 deletions(-)
    create mode 100644 test3.md

    [main e7187c1] chore: Create fourth file
    1 file changed, 0 insertions(+), 0 deletions(-)
    create mode 100644 test4.md
   ```
   

### 5. Advanced Squashing
   ```sh
   git rebase -i HEAD~2
   ```
   **Output:**
   ```sh
    [detached HEAD 1934339] chore: Create third and fourth files
    Date: Fri Mar 7 11:59:57 2025 +0200
    2 files changed, 0 insertions(+), 0 deletions(-)
    create mode 100644 test4.md
    Successfully rebased and updated refs/heads/main.
   ```

### 6. Removing an Unwanted Commit
   ```sh
   New-Item unwanted.txt -ItemType File
   git add unwanted.txt
   git commit -m "chore: Unwanted commit"
   git rebase -i HEAD~2
   ```
   **Output:**
   ```sh
   [main 83ebba5] chore: Unwanted commit
    1 file changed, 1 insertion(+)
    create mode 100644 unwanted.txt
   Successfully rebased and updated refs/heads/main.
   ```

### 7. Reordering Commits
   ```sh
   git rebase -i HEAD~3
   ```

   ```sh
   # commit order before reorder
    1934339 (HEAD -> main) chore: Create third and fourth files
    59fccd7 chore: Create initial file
    aba096a (origin/main) chore: initial commit
   ```
   ```sh
   # commit order after reorder
    Successfully rebased and updated refs/heads/main.

    82572a9 (HEAD -> main) chore: Create initial file
    bee7795 chore: Create third and fourth files
    aba096a (origin/main) chore: initial commit
   ```

### 8. Cherry-Picking Commits
   ```sh
   git branch ft/branch
   git switch ft/branch
   New-Item test5.md -ItemType File
   git add test5.md
   git commit -m "chore: Implement test 5"
   git switch main
   git cherry-pick --no-commit e5578d7
   git commit -m "chore: Implement test 5"
   ```

   **Output:**
   ```sh
    create mode 100644 test5.md

    Switched to branch 'main'

    [main 7db1d46] chore: Implemented test 5
    1 file changed, 1 insertion(+)
    create mode 100644 test5.md
   ```

### 9. Viewing Commit History
   ```sh
   git log --graph --oneline --all
   ```
   **Output:**
   ```sh
   * 7db1d46 (HEAD -> main) chore: Implement test 5
   | * e5578d7 (ft/branch) chore: Implement test 5
   |/
   * 82572a9 chore: Create first file
   * bee7795 chore: Create third and fourth files
   * aba096a (origin/main) chore: initial commit
   ```

### 10. Understanding Reflogs
   ```sh
   git reflog
   ```
   **Output:**
   ```sh
   7db1d46 (HEAD -> main) HEAD@{0}: commit: chore: Implement test 5
   82572a9 HEAD@{1}: checkout: moving from ft/branch to main
   e5578d7 (ft/branch) HEAD@{2}: checkout: moving from main to ft/branch    
   82572a9 HEAD@{3}: checkout: moving from ft/branch to main
   e5578d7 (ft/branch) HEAD@{4}: commit: chore: Implement test 5
   82572a9 HEAD@{5}: checkout: moving from main to ft/branch
   82572a9 HEAD@{6}: rebase (finish): returning to refs/heads/main
   82572a9 HEAD@{7}: rebase (pick): chore: Create first file
   bee7795 HEAD@{8}: rebase (pick): chore: Create third and fourth files    
   aba096a (origin/main) HEAD@{9}: rebase (start): checkout HEAD~2
   ```