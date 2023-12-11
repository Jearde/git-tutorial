# Working with Branches

## What is a Branch?

**Definition:** A branch is a separate line of development within a repository.

**Key Concepts:**
- Branches are lightweight and easy to create.
- Branches are used to develop features or bug fixes.
- Branches are merged back into the main line of development when complete.

### Branching Workflow

- Create a branch to try out an idea and switch back, patch
- New branches for each new feature (switch back and forth)
- Branch to experiment

![An Optimal Git Branching Model](https://mergebase.com/blog/git-v-branching-model/images/git-V.webp)

## Creating a Branch
- `git branch`
    - Lists all of the branches in the repository.
    - `git branch <branch>`
        - Creates a new branch.
    - `git branch -d <branch>` (alternative)
        - Deletes a branch.
- `git switch <branch>`
    - Switches to an existing branch.
    - `git switch -c <branch>` (alternative)
        - Creates a new branch and switches to it.

## Merging Branches
- `git merge <branch>`
    - Merges the specified branch into the current branch.
    - `git merge --abort` (alternative)
        - Aborts the merge and restores the state before the merge.
- `git rebase <branch>`
    - Reapplies commits from the specified branch onto the current branch.
    - `git rebase --abort` (alternative)
        - Aborts the rebase and restores the state before the rebase.
    - `git rebase --continue` (alternative)
        - Continues the rebase after resolving conflicts.

## Branching Exercises

### Exercise 1: Creating a Branch
```bash	
# Create a new branch named "feature"
git branch feature

# Show all branches
git branch

# Switch to the new branch
git switch feature

# Create a new file
echo "Hello 2nd World" > world_2.txt

# Add the new file to the staging area
git add world_2.txt

# Commit the new file
git commit -m "Add world_2.txt"

# Show the commit history
git log --oneline --graph --all
```

### Exercise 2: Merging Branches
```bash
# Switch to the main branch
git switch main

# Create a new file
echo "Hello 3rd World" > world_3.txt

# Add the new file to the staging area
git add world_3.txt

# Commit the new file
git commit -m "Add world_3.txt"

# Show the commit history
git log --oneline --graph --all

# Merge the feature branch into the main branch
git merge feature

# Show the commit history
git log --oneline --graph --all

# Reset the main branch to the previous commit
git reset --hard HEAD~1

# Show the commit history
git log --oneline --graph --all
```

### Exercise 3: Rebasing Branches

```bash
# Rebasing the feature branch onto the main branch
git switch feature
git rebase main

# Show the commit history
git log --oneline --graph --all

# Get back to the main branch
git switch main
git rebase feature

# Show the commit history
git log --oneline --graph --all
```