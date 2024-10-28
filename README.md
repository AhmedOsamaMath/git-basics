# The Complete Git Guide

## Table of Contents
1. [Introduction](#introduction)
2. [Installation & Setup](#installation--setup)
3. [Basic Concepts](#basic-concepts)
4. [Essential Commands](#essential-commands)
5. [Working with Branches](#working-with-branches)
6. [Remote Repository Operations](#remote-repository-operations)
7. [Advanced Git Operations](#advanced-git-operations)
8. [Best Practices](#best-practices)
9. [Useful Tools & Extensions](#useful-tools--extensions)
10. [Additional Resources](#additional-resources)

## Introduction

Git is a distributed version control system created by Linus Torvalds in 2005. It enables developers to track changes in source code, collaborate on projects, and maintain a complete history of their work. Its distributed nature ensures that every developer has a full copy of the project history, providing both reliability and flexibility in workflows.

## Installation & Setup

### Installing Git

- **Windows**: Download from [Git for Windows](https://git-scm.com/download/win)
- **macOS**: Use Homebrew: `brew install git`
- **Linux**: Use package manager (e.g., Ubuntu: `sudo apt-get install git`)

### Initial Configuration

```bash
# Set your identity
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# Set default editor
git config --system core.editor <editor>

# Enable color output
git config --global color.ui auto

# View configuration
git config --list
```

## Basic Concepts

### The Git Workflow

1. Working Directory: Where you modify files
2. Staging Area: Where you prepare changes for commit
3. Repository: Where Git stores the committed history

### Repository Setup

```bash
# Initialize new repository
git init [directory]

# Clone existing repository
git clone <repository-url>
```

## Essential Commands

### Basic Operations

```bash
# Check status
git status

# Stage changes
git add <file>          # Stage specific file
git add .               # Stage all changes

# Commit changes
git commit -m "message" # Commit with message
git commit --amend      # Modify last commit

# View history
git log                 # Full history
git log --oneline      # Condensed history
git log --graph        # Graphical history
```

### File Operations

```bash
# Remove files
git rm <file>          # Remove from Git and filesystem
git rm --cached <file> # Remove from Git only

# Move/rename files
git mv <old-path> <new-path>

# View changes
git diff              # Unstaged changes
git diff --staged     # Staged changes
```

## Working with Branches

### Branch Management

```bash
# List branches
git branch            # List local branches
git branch -r         # List remote branches
git branch -a         # List all branches

# Create and switch branches
git branch <name>     # Create branch
git checkout <name>   # Switch to branch
git checkout -b <name># Create and switch in one command

# Delete branches
git branch -d <name>  # Safe delete
git branch -D <name>  # Force delete
```

### Merging and Rebasing

```bash
# Merge branches
git merge <branch>    # Merge branch into current

# Rebase
git rebase <branch>   # Rebase current branch onto another
git rebase -i <base>  # Interactive rebase
```

## Remote Repository Operations

### Managing Remotes

```bash
# Add and remove remotes
git remote add <name> <url>
git remote remove <name>

# View remotes
git remote -v
```

### Syncing with Remotes

```bash
# Fetch changes
git fetch <remote>
git fetch --all

# Pull changes
git pull <remote> <branch>
git pull --rebase <remote>

# Push changes
git push <remote> <branch>
git push --force      # Force push (use with caution!)
git push --tags       # Push tags
```

## Advanced Git Operations

### Stashing Changes

```bash
git stash             # Save changes temporarily
git stash list        # List stashes
git stash pop         # Apply and remove stash
git stash apply       # Apply but keep stash
git stash drop        # Remove stash
```

### History Modification

```bash
# Reset
git reset --soft HEAD~1  # Undo last commit, keep changes staged
git reset --mixed HEAD~1 # Undo last commit, unstage changes
git reset --hard HEAD~1  # Undo last commit, discard changes

# Revert
git revert <commit>      # Create new commit that undoes changes

# Cherry-pick
git cherry-pick <commit> # Apply specific commit to current branch
```

## Best Practices

1. **Commit Practices**
   - Write clear, descriptive commit messages
   - Make small, focused commits
   - Commit related changes together

2. **Branching Strategy**
   - Use feature branches for new development
   - Keep main/master branch stable
   - Regularly update feature branches with main

3. **Collaboration**
   - Pull regularly to stay up-to-date
   - Don't force push to shared branches
   - Use pull requests for code review

4. **Repository Hygiene**
   - Use .gitignore for build artifacts and dependencies
   - Regularly clean up old branches
   - Tag important releases

## Useful Tools & Extensions

### VS Code Extensions
- GitLens: Enhanced Git integration
- Git History: Visual Git history
- Git Graph: Repository visualization

### Git GUI Clients
- GitHub Desktop
- Sourcetree
- GitKraken

## Additional Resources

- [Official Git Documentation](https://git-scm.com/doc)
- [Pro Git Book](https://git-scm.com/book/en/v2)
- [GitHub Guides](https://guides.github.com/)
- [Visual Git Guide](https://marklodato.github.io/visual-git-guide/index-en.html)
