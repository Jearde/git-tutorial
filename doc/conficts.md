# Handeling Conflicts

## Merge Conflicts

- Occur when merging branches
- Git cannot determine which changes to keep
- Must be resolved manually

- `git mergetool <file>`
    - Opens a tool to resolve merge conflicts in the specified file.

### Exercise 1: Creating a Merge Conflict

```bash
# Create a new branch named "feature"
git branch feature_conflict

# Switch to the new branch
git switch feature_conflict

# Create a new file
echo "Hello 2nd World" > world_2.txt

# Add the new file to the staging area
git add world_2.txt

# Commit the new file
git commit -m "Add world_2.txt"

# Switch to the main branch
git switch main

# Create a new file
echo "Hello 3rd World" > world_2.txt

# Add the new file to the staging area
git add world_3.txt

# Commit the new file
git commit -m "Add world_3.txt"

# Merge the feature branch into the main branch
git merge feature_conflict
```

### Exercise 2: Resolving a Merge Conflict

```bash
# Open the file in a text editor
code world_2.txt

# Edit the file to resolve the conflict

# Add the file to the staging area
git add world_2.txt

# Commit the file
git commit -m "Resolve merge conflict"
```

## Rebase Conflicts

- Occur when rebasing branches
- Git cannot determine which changes to keep
- Must be resolved manually
