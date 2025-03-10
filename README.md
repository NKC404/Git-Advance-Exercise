# Git Advanced Exercise

## Getting Started

### Initialize a New Git Repository
1. **Initialize the repository**
   ```sh
   git init
   ```
   **Output:**
   ```sh
   Initialized empty Git repository in C:/Users/Clement/Desktop/TheExe/Git-Advance-Exercise/.git/
   ```

2. **Create the first commit (a README.md file)**
   ```sh
   echo "# Git Advance Exercise" > README.md
   git add README.md
   git commit -m "chore: initial commit"
   ```
   **Output:**
   ```sh
   [main (root-commit) aba096a] chore: initial commit
    1 file changed, 1 insertion(+)
    create mode 100644 README.md
   ```

3. **Add a remote repository and push the initial commit**
   ```sh
   git remote add origin https://github.com/NKC404/Git-Advance-Exercise.git
   git push -u origin main
   ```
   **Output:**
   ```sh
   Enumerating objects: 3, done.
   Counting objects: 100% (3/3), done.
   Writing objects: 100% (3/3), 271 bytes | 135.00 KiB/s, done.
   Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
   To https://github.com/NKC404/Git-Advance-Exercise.git
    * [new branch]      main -> main
   ```

   ## Setting Up the Environment

### Creating and Committing Files

1. **Create multiple files**
   ```sh
   New-Item test1.md, test2.md, test3.md, test4.md -ItemType File
   ```
   **Output:**
   ```sh
       Directory: C:\Users\Clement\Desktop\TheExe\Git-Advance-Exercise  

   Mode                 LastWriteTime         Length Name  
   ----                 -------------         ------ ----  
   -a----          3/7/2025  11:48 AM              0 test1.md  
   -a----          3/7/2025  11:48 AM              0 test2.md  
   -a----          3/7/2025  11:48 AM              0 test3.md  
   -a----          3/7/2025  11:48 AM              0 test4.md  
   ```

2. **Add and commit each file**
   ```sh
   git add test1.md
   git commit -m "chore: Create first file"
   ```
   **Output:**
   ```sh
   [main 66ef6a4] chore: Create first file
    1 file changed, 0 insertions(+), 0 deletions(-)
    create mode 100644 test1.md
   ```

## 🏆 Challenges Resolved

- [**Challenge 1: Refining Git History**](./docs/Part1.md)  
  In this challenge, I addressed issues related to refining Git history, including fixing a missing file, editing commit messages, squashing commits, and splitting commits for better clarity.

- [**Challenge 2: Branching Basics**](./docs/Part2.md)  
  Here, I worked on creating, switching, and deleting branches. I also tackled tasks such as merging, rebasing, and working with local and remote branches to better organize my workflow.

- [**Challenge 3: Advanced Workflows**](./docs/Part3.md)  
  In this section, I focused on more advanced Git workflows like stashing changes, resolving merge conflicts, working with tags, and pushing/pulling changes between local and remote repositories.