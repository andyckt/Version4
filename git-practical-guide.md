# Practical Git Guide for Solo Development

This guide provides step-by-step instructions for common Git operations you'll use while developing your social media app.

## Daily Workflow

### Starting a New Feature

```bash
# Make sure you're on the develop branch
git checkout develop

# Pull the latest changes
git pull origin develop

# Create a new feature branch
git checkout -b feature/user-authentication

# Work on your feature...
# (Make changes to files)

# Add your changes
git add .

# Commit your changes with a descriptive message
git commit -m "Add user login and registration forms"

# Push your feature branch to GitHub
git push -u origin feature/user-authentication
```

### Continuing Work on a Feature

```bash
# Switch to your feature branch
git checkout feature/user-authentication

# Pull any changes if you're working from multiple computers
git pull origin feature/user-authentication

# Make more changes...

# Add and commit changes
git add .
git commit -m "Add password reset functionality"

# Push changes
git push origin feature/user-authentication
```

### Completing a Feature

```bash
# Make sure your feature branch is up to date
git checkout feature/user-authentication
git pull origin feature/user-authentication

# Switch to develop branch
git checkout develop

# Pull latest changes from develop
git pull origin develop

# Merge your feature branch into develop
git merge feature/user-authentication

# Push the updated develop branch to GitHub
git push origin develop

# Optional: Delete the feature branch locally and remotely
git branch -d feature/user-authentication
git push origin --delete feature/user-authentication
```

## Common Git Commands Explained

### Basic Commands

- `git status`: Check the status of your working directory
- `git log`: View commit history
- `git diff`: See changes between commits, branches, etc.

### Branching

- `git branch`: List all local branches
- `git branch -a`: List all branches (local and remote)
- `git checkout -b branch-name`: Create and switch to a new branch
- `git checkout branch-name`: Switch to an existing branch

### Undoing Changes

- `git reset --hard HEAD`: Discard all local changes
- `git reset --soft HEAD~1`: Undo the last commit but keep the changes
- `git checkout -- filename`: Discard changes to a specific file

### Resolving Merge Conflicts

When you encounter merge conflicts:

1. Git will mark the conflicts in the affected files
2. Open the files and look for the conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`)
3. Edit the files to resolve the conflicts
4. Add the resolved files with `git add`
5. Complete the merge with `git commit`

## Releasing Your App

```bash
# Create a release branch from develop
git checkout develop
git pull origin develop
git checkout -b release/1.0.0

# Make any final adjustments and fixes
# ...

# Merge to main when ready
git checkout main
git pull origin main
git merge release/1.0.0
git tag -a v1.0.0 -m "Version 1.0.0"
git push origin main --tags

# Also merge back to develop
git checkout develop
git pull origin develop
git merge release/1.0.0
git push origin develop

# Delete the release branch
git branch -d release/1.0.0
git push origin --delete release/1.0.0
``` 