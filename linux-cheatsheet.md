# Linux Cheat Sheet

My personal notes from Week 1 of learning DevOps.

## Navigation

| Command | What it does |
|---|---|
| `pwd` | Show where I am |
| `cd ~` | Go to home folder |
| `cd ..` | Go up one level |
| `cd folder` | Go into a folder |
| `ls` | List files |
| `ls -l` | List with details (permissions, size, date) |
| `ls -a` | List including hidden files |

## Files and folders

| Command | What it does |
|---|---|
| `mkdir` | Make a folder |
| `touch` | Make an empty file |
| `cp` | Copy a file |
| `mv` | Move or rename a file |
| `rm` | Delete a file (permanent!) |
| `rmdir` | Delete an empty folder |

## Reading and editing

| Command | What it does |
|---|---|
| `cat` | Print the whole file |
| `less` | Scroll through a file (`q` to quit) |
| `head` | First 10 lines |
| `tail` | Last 10 lines |
| `nano` | Edit a file (`Ctrl+O` save, `Ctrl+X` exit) |

## Permissions

| Number | Symbolic | Use for |
|---|---|---|
| `644` | `-rw-r--r--` | Normal files |
| `755` | `-rwxr-xr-x` | Scripts, folders |
| `600` | `-rw-------` | Private files |

| Command | What it does |
|---|---|
| `chmod +x file` | Make a file executable |
| `chmod 644 file` | Set standard file permissions |

## Searching

| Command | What it does |
|---|---|
| `find . -type f -size 1033c` | Find files by size and type |
| `find / -user X 2>/dev/null` | Search whole system, hide errors |
| `grep "word" file` | Search inside a file for text |
| `strings file` | Pull readable text from binary |
| `sort file` | Sort lines |
| `uniq -u` | Show only unique lines |

## The pipe `|`

Sends output of one command into the next.

```bash
cat file.txt | grep "error" | sort | uniq -c
Reads as: "show the file, keep only errors, sort them, count duplicates."

Things I learned the hard way
rm has no undo. No trash can. Be careful.

cat - doesn't work — use cat ./- for files named -.

Filenames with spaces need quotes: cat "my file.txt"

Hidden files start with a dot. Use ls -a to see them.

2>/dev/null throws away error messages — useful when find gets noisy.

Never chmod 777. Ever.

# Git Learning

I am learning version control with Git.
Git tracks changes to files and allows me to maintain project history.


# Git Commands

git status
git add
git commit
git log
git push
GitHub is a remote hosting platform for Git repositories.


# Branch Learning

I am practising Git branches.
This change is currently on the testing branch.

# GIT VERSION CONTROL

Git is a version control system used to track changes in files and manage project history.

GitHub is an online platform for hosting Git repositories.

## 1. Basic Git Commands

| Command | Function |
|---|---|
| `git init` | Initializes a new Git repository. |
| `git status` | Shows the current state of the repository. |
| `git log` | Displays commit history. |
| `git log --oneline` | Displays commit history in a compact format. |
| `git diff` | Shows changes that have not been staged. |
| `git diff --staged` | Shows changes that have been staged. |

## 2. Staging and Committing

| Command | Function |
|---|---|
| `git add filename` | Stages a specific file. |
| `git add .` | Stages all changes in the current directory. |
| `git commit -m "message"` | Saves staged changes as a commit. |
| `git restore --staged filename` | Removes a file from staging without deleting its changes. |
| `git restore filename` | Discards unstaged changes and restores the last committed version. |

**Basic workflow:**
```bash
git status
git add .
git commit -m "Describe your changes"
```

## 3. Local and Remote Repositories

- **Local repository:** The Git repository on your computer.
- **Remote repository:** A copy of your repository hosted online, usually on GitHub.
- **origin:** The default nickname for a remote repository.

| Command | Function |
|---|---|
| `git remote -v` | Displays configured remote repositories. |
| `git remote add origin URL` | Connects a local repository to a remote repository. |
| `git clone URL` | Downloads an existing remote repository to your computer. |

## 4. Pushing and Pulling

| Command | Function |
|---|---|
| `git push` | Uploads local commits to the remote repository. |
| `git push -u origin main` | Pushes the main branch and sets its upstream tracking branch. |
| `git pull` | Downloads and integrates changes from the remote repository. |

**Remember:**
- `push` = Local → Remote.
- `pull` = Remote → Local.

## 5. Branch Creation and Switching

A branch is an independent line of development that allows you to work on changes without directly affecting another branch.

| Command | Function |
|---|---|
| `git branch` | Lists local branches. |
| `git branch testing` | Creates a branch named testing. |
| `git switch testing` | Switches to an existing branch. |
| `git switch -c testing` | Creates and switches to a new branch. |

The `*` symbol in `git branch` identifies the currently active branch.

## 6. Merging and Deleting Branches

| Command | Function |
|---|---|
| `git merge testing` | Merges the testing branch into the current branch. |
| `git branch -d testing` | Deletes the local testing branch if it has been safely merged. |
| `git branch -D testing` | Force-deletes a local branch, even if it has unmerged changes. |

**Typical merging workflow:**
```bash
git switch main
git merge testing
git push
git branch -d testing
```

**Important:**
- Merge a branch while positioned on the branch that should receive the changes.
- Deleting a merged branch does not delete its changes from the branch it was merged into.
- `git branch -d` deletes a local branch, not the remote branch.

## 7. Git Workflow Summary

```text
EDIT FILES
    ↓
git status
    ↓
git add .
    ↓
git commit -m "message"
    ↓
git push
    ↓
CHANGES UPLOADED TO GITHUB
```
