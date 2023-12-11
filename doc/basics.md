# Git Basics
Next section: [Working with Branches](branches.md)
## What is Git?
_Git is a distributed version control system_ (http://git-scm.com/about)

- Frictionless Context Switching
    - Create a branch to try out an idea and switch back, patch
- Role-Based Codelines
    - Production, testing, features
- Feature Based Workflow
    - New branches for each new feature (switch back and forth)
- Disposable Experimentation
    - Branch to experiment

![An Optimal Git Branching Model](https://mergebase.com/blog/git-v-branching-model/images/git-V.webp)

## Installing Git

- Test if Git is already installed
    - `git --version`

### Linux
- Debian/Ubuntu: `sudo apt install git`
### Windows
- [Download Git](https://git-scm.com/downloads)
- Follow instructions in installer

## Configuring Git
The follwoing commands configure Git on your machine.
They alter the file `~/.gitconfig` (Linux) or `C:\Users\<username>\.gitconfig` (Windows).

- `git config --global user.name "Your Name"`
    - Sets the name attached to your commits.
- `git config --global user.email "your.name@example.com"`
    - Sets the email attached to your commits.
- `git config --global core.editor "vim"` (optional)
    - Sets the default editor for commit messages.
    - `git config --global core.editor "code-insiders --wait"` (optional)
- `git config --global color.ui auto` (optional)
    - Enables helpful colorization of command line output.
- `git config --list`
    - Displays all of your Git configuration settings.

## Baisc Git Commands (I)
- `git init`
    - Initializes a new Git repository.
    - Creates a hidden subfolder .git
- `git add <file>`
    - Adds a file to the staging area.
    - Files in the staging area will be included in the next commit.
    - `git mv <old> <new>` (alternative)
        - Renames a file and stages the change.
    - `git rm <file>` (alternative)
        - Removes a file and stages the change.
- `git commit`
    - Creates a new commit from the files in the staging area.
    - Opens the default editor to enter a commit message.
    - `git commit -m "Commit message"` (alternative)
- `git status`
    - Displays the current status of the repository.
    - Shows which files are staged, unstaged, and untracked.
- `git log`
    - Displays the commit history of the current branch.
    - `git log --oneline --graph` (alternative)
- `git diff`
    - Shows the differences between the working directory and the staging area.
    - `git diff --staged` (alternative)
- `git reset`
    - Resets the staging area to the last commit without changing the working directory.
    - `git reset --hard`
        - Resets the staging area and the working directory to the last commit.
    - `git reset --hard <commit>`
        - Resets the staging area and the working directory to the specified commit.
- `git checkout <file>`
    - Discards changes to a file in the working directory.
    - `git checkout .`
        - Discards changes to all files in the working directory.
    - `git checkout <commit> <file>`
        - Restores a file from the specified commit.

![](https://miro.medium.com/v2/resize:fit:720/format:webp/1*YtHZxDoRGyFi7RVqD8sk9g.png)

## Ignoring Files
Gitignore files specify intentionally untracked files that Git should ignore. Files already tracked by Git are not affected.

### Local
```bash
touch .gitignore
```

The content can look like this:
```bash
# Ignore all files with the extension .txt
*.txt

# Ignore all files in the directory build
build/

# Ignore all files in the directory build and all its subdirectories
build/**

# Ignore all files in the directory build and all its subdirectories except the file build/README.md
build/**
!build/README.md
```

This allows you to use `git add .` or `git commit -a` to add all files except the ones specified in the gitignore file, when configured correctly.

## Basic Exercises
### Exercise 1: Creating a Repository
```bash	
# Open a terminal and create a new directory
mkdir git-tutorial
cd git-tutorial

# Initialize a new Git repository
git init

# View the contents of the .git folder
ls -a .git
```

### Exercise 2: Creating a Commit
```bash
# Create a new file
echo "Hello World" > hello.txt
git status

# Add the file to the staging area
git add hello.txt
git status

# Commit the file
git commit -m "Initial commit"

# Change the file
nano hello.txt 
git status
git diff

# Add the file to the staging area
git add hello.txt

# Commit the file
git commit

# View the commit history
git show
git log
```

### Exercise 3: Discarding Changes

```bash
# Change the file
nano hello.txt 

# Reset the staging area
git status
git reset --hard HEAD
git status

git reset HEAD~1
git log
```

### Exercise 4: Ignoring Files
```bash
# Create a file that should be ignored
echo "This file should be ignored" > ignored.log

# Check the status of the repository
git status

# Exclude all .log files from the repository
echo "*.log" > .gitignore

# Add the .gitignore file to the repository
git add .gitignore
git commit -m "Add .gitignore"

# Check the status of the repository
git status
```
