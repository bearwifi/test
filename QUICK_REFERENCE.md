# Git Repository Quick Reference

A cheat sheet for common Git operations when working with repositories.

## Creating Repositories

```bash
# Create new local repository
git init

# Create repository in specific directory
git init my-repo-name

# Clone existing repository
git clone https://github.com/username/repo.git
```

## Basic Commands

```bash
# Check status
git status

# Add files to staging
git add filename.txt        # Specific file
git add .                   # All files
git add *.js                # Pattern matching

# Commit changes
git commit -m "Message"
git commit -am "Message"    # Add and commit tracked files

# View history
git log
git log --oneline          # Compact view
git log --graph            # Visual branch graph
```

## Remote Operations

```bash
# Add remote
git remote add origin https://github.com/username/repo.git

# View remotes
git remote -v

# Push changes
git push origin main
git push -u origin main    # Set upstream and push

# Pull changes
git pull origin main
git pull                   # From current tracking branch

# Fetch changes (without merging)
git fetch origin
```

## Branching

```bash
# List branches
git branch
git branch -a              # Include remote branches

# Create new branch
git branch feature-name

# Switch to branch
git checkout feature-name

# Create and switch in one command
git checkout -b feature-name

# Merge branch
git checkout main
git merge feature-name

# Delete branch
git branch -d feature-name
```

## Undoing Changes

```bash
# Discard changes in working directory
git checkout -- filename.txt

# Unstage file
git reset HEAD filename.txt

# Undo last commit (keep changes)
git reset --soft HEAD~1

# Undo last commit (discard changes)
git reset --hard HEAD~1

# Revert a commit (create new commit)
git revert commit-hash
```

## Configuration

```bash
# Set user name
git config --global user.name "Your Name"

# Set email
git config --global user.email "your.email@example.com"

# View all settings
git config --list

# Set default branch name
git config --global init.defaultBranch main
```

## Stashing

```bash
# Save changes temporarily
git stash

# List stashes
git stash list

# Apply latest stash
git stash apply

# Apply and remove stash
git stash pop

# Drop stash
git stash drop
```

## Viewing Differences

```bash
# See unstaged changes
git diff

# See staged changes
git diff --staged

# Compare branches
git diff branch1..branch2

# See changes in specific file
git diff filename.txt
```

## Repository Information

```bash
# Show remote URLs
git remote -v

# Show current branch
git branch --show-current

# Show last commit
git log -1

# Show repository status
git status -sb             # Short format
```

## GitHub Specific

```bash
# Clone with SSH
git clone git@github.com:username/repo.git

# Change remote URL
git remote set-url origin new-url

# Fork workflow
git remote add upstream https://github.com/original/repo.git
git fetch upstream
git merge upstream/main
```

## Common Workflows

### Starting a New Project

```bash
mkdir my-project
cd my-project
git init
echo "# My Project" > README.md
git add README.md
git commit -m "Initial commit"
git remote add origin https://github.com/username/my-project.git
git push -u origin main
```

### Making Changes

```bash
# Make your changes to files
git status                 # Check what changed
git add .                  # Stage changes
git commit -m "Description of changes"
git push                   # Push to remote
```

### Feature Branch Workflow

```bash
git checkout -b feature/new-feature
# Make changes
git add .
git commit -m "Add new feature"
git push -u origin feature/new-feature
# Create pull request on GitHub
# After merge:
git checkout main
git pull
git branch -d feature/new-feature
```

## Tips

- **Commit often**: Small, frequent commits are better than large ones
- **Write good messages**: Clearly describe what and why, not how
- **Pull before push**: Always pull latest changes before pushing
- **Use branches**: Keep main branch stable, develop in feature branches
- **Review before commit**: Use `git status` and `git diff` before committing

## Help

```bash
# Get help for any command
git help <command>
git <command> --help

# Quick reference
git <command> -h
```

---

For more detailed information, see the [complete guide](HOW_TO_CREATE_EMPTY_REPOSITORY.md).
