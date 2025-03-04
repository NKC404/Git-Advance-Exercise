# Git-Advance-Exercise

## Getting Started:

    1. Create a New Git Repository :

    ```
    iMac Git-Advance % echo "# Git-Advance-Exercise" >> README.md
    iMac Git-Advance % git init                                  
    Initialized empty Git repository in /Users/gymigitangaza/Desktop/nkc/Exercises/Git-Advance/.git/
    iMac Git-Advance % git add README.md
    iMac Git-Advance % git commit -m "first commit"
    [main (root-commit) b09b641] first commit
    1 file changed, 1 insertion(+)
    create mode 100644 README.md
    iMac Git-Advance % git remote add origin https://github.com/NKC404/Git-Advance-Exercise.git
    iMac Git-Advance % git push -u origin main
    Enumerating objects: 3, done.
    Counting objects: 100% (3/3), done.
    Writing objects: 100% (3/3), 236 bytes | 236.00 KiB/s, done.
    Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
    To https://github.com/NKC404/Git-Advance-Exercise.git
    * [new branch]      main -> main
    branch 'main' set up to track 'origin/main'.
    ```

    2. Set Environment:

    ```
    gymigitangaza@Igitangazas-iMac Git-Advance % touch test{1..4}.md
    gymigitangaza@Igitangazas-iMac Git-Advance % git add test1.md && git commit -m "chore: Create initial file"
    [main 8eb3fb1] chore: Create initial file
    1 file changed, 0 insertions(+), 0 deletions(-)
    create mode 100644 test1.md
    gymigitangaza@Igitangazas-iMac Git-Advance % git add test2.md && git commit -m "chore: Create another file"
    [main 31aaea3] chore: Create another file
    1 file changed, 0 insertions(+), 0 deletions(-)
    create mode 100644 test2.md
    gymigitangaza@Igitangazas-iMac Git-Advance % git add test3.md && git commit -m "chore: Create third and fourth files"

    [main 9bedd6d] chore: Create third and fourth files
    1 file changed, 0 insertions(+), 0 deletions(-)
    create mode 100644 test3.md
    ```

## Part 1: Refining Git History

    1. Missing File Fix:

    **current state of the repository:**

    ```
    gymigitangaza@Igitangazas-iMac Git-Advance % git status
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

    ```
    gymigitangaza@Igitangazas-iMac Git-Advance % git log
    commit 9bedd6d2648e5813164ee3e11668392c84a9a21a (HEAD -> main)
    Author: NKC404 <upwizzard@gmail.com>
    Date:   Tue Mar 4 12:50:11 2025 +0200

        chore: Create third and fourth files

    commit 31aaea36950ad2a05a516b696b07b4d3c2d966d2
    Author: NKC404 <upwizzard@gmail.com>
    Date:   Tue Mar 4 12:50:01 2025 +0200

        chore: Create another file

    commit 8eb3fb13c3e6d91d1de11c8042da9b0cf38a6bef
    Author: NKC404 <upwizzard@gmail.com>
    Date:   Tue Mar 4 12:49:48 2025 +0200

        chore: Create initial file

    commit b09b64141c505616354e8c1b2af298ed6982d8de (origin/main)
    Author: NKC404 <upwizzard@gmail.com>
    Date:   Tue Mar 4 12:46:41 2025 +0200

        first commit
    ```

    * From the status we see that we forgot to add test4.md in the last commit :

    **Challenge:** Recover from this error by staging/adding test4.md and amending the commit message with an appropriate description.

