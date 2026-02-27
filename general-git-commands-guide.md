# General Git Commands Guide

This guide covers commonly used Git commands for version control,
branching, pushing, pulling, and resolving conflicts.

------------------------------------------------------------------------

# 1. Initial Setup

## Configure Git (First Time Only)

``` bash
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
```

Check configuration:

``` bash
git config --list
```

------------------------------------------------------------------------

# 2. Repository Setup

## Clone a Repository

``` bash
git clone <repository-url>
```

Example (SSH):

``` bash
git clone git@github.com:username/repo.git
```

## Initialize a New Repository

``` bash
git init
```

------------------------------------------------------------------------

# 3. Basic Workflow Commands

## Check Status

``` bash
git status
```

Shows modified, staged, and untracked files.

## Add Files to Staging Area

Add specific file:

``` bash
git add filename
```

Add all files:

``` bash
git add .
```

## Commit Changes

``` bash
git commit -m "Your commit message"
```

------------------------------------------------------------------------

# 4. Branching

## View Branches

``` bash
git branch
```

## Create New Branch

``` bash
git branch branch-name
```

## Create and Switch to New Branch

``` bash
git checkout -b branch-name
```

OR (modern way):

``` bash
git switch -c branch-name
```

## Switch Branch

``` bash
git checkout branch-name
```

OR

``` bash
git switch branch-name
```

## Delete Branch

``` bash
git branch -d branch-name
```

------------------------------------------------------------------------

# 5. Pulling and Pushing

## Pull Latest Changes

``` bash
git pull origin branch-name
```

Fetches and merges latest changes from remote.

## Push Changes

``` bash
git push origin branch-name
```

Push new branch first time:

``` bash
git push -u origin branch-name
```

------------------------------------------------------------------------

# 6. Merging

## Merge a Branch

First switch to target branch:

``` bash
git checkout main
```

Then merge:

``` bash
git merge branch-name
```

------------------------------------------------------------------------

# 7. Handling Merge Conflicts

When conflict occurs, Git will mark the file like:

    <<<<<<< HEAD
    Your changes
    =======
    Incoming changes
    >>>>>>> branch-name

## Steps to Resolve:

1.  Open the conflicted file.
2.  Edit and remove conflict markers.
3.  Keep correct code.
4.  Add resolved file:

``` bash
git add filename
```

5.  Commit:

``` bash
git commit -m "Resolved merge conflict"
```

------------------------------------------------------------------------

# 8. Viewing History

## View Commit History

``` bash
git log
```

Compact view:

``` bash
git log --oneline --graph --all
```

------------------------------------------------------------------------

# 9. Undo Changes

## Unstage File

``` bash
git restore --staged filename
```

## Discard Local Changes

``` bash
git restore filename
```

## Reset Last Commit (Keep Changes)

``` bash
git reset --soft HEAD~1
```

## Reset Last Commit (Delete Changes)

``` bash
git reset --hard HEAD~1
```

------------------------------------------------------------------------

# 10. Stashing

Temporarily save changes:

``` bash
git stash
```

Apply stash:

``` bash
git stash apply
```

List stashes:

``` bash
git stash list
```

------------------------------------------------------------------------

# 11. Useful Shortcuts

``` bash
git fetch        # Download changes without merging
git remote -v    # View remote repositories
git diff         # View changes
git rebase       # Reapply commits on top of another base tip
```

------------------------------------------------------------------------

# Recommended Daily Workflow

``` bash
git pull origin main
git checkout -b feature-branch
git add .
git commit -m "Add feature"
git push -u origin feature-branch
```

------------------------------------------------------------------------

**You are now ready to use Git efficiently for version control and
collaboration.**
