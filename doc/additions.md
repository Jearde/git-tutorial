# Tips und Tricks
Back to [Readme](../README.md)
* Section [GitHub](github.md)
* Section [GitLab](gitlab.md)

## VS Code Extensions

### GitGraph
The Git Graph extension allows you to visualize your repository's Git history.

![Git Graph](../images/vs_code_git_graph.png)


## Git Submodule
Submodules are a way to keep a Git repository as a subdirectory of another Git repository. This allows you to clone another repository into your project and keep your commits separate.

### Add Submodule
```bash
git submodule add <url> <path>
```

### Update Submodule
```bash
git submodule update --init --recursive
```

### Remove Submodule
```bash
git submodule deinit <path>
git rm <path>
```

## Git Aliases
### Add Alias
```bash
git config --global alias.<alias> <command>
```

### List Aliases
Git stores aliases in the `~/.gitconfig` file.
```ini
[alias]
	update = !git pull && git submodule update --init --recursive
```

## Interactive Rebase
The interactive rebase allows you to edit, squash, delete, and reorder commits.

### Start Interactive Rebase
```bash
# Rebase the last n commits
git rebase -i HEAD~n
```
Explanation:
- Each commit is represented by a line in the editor.
- The first word on each line is the command.
- The second word on each line is the commit hash.
- The third word on each line is the commit message.

Changes:
- `pick` -> `pick`: Keep the commit.
- `pick` -> `drop`: Delete the commit.
- `pick` -> `reword`: Change the commit message.
- `pick` -> `squash`: Combine the commit with the previous commit.
- `pick` -> `fixup`: Combine the commit with the previous commit and discard the commit message.
- `pick` -> `edit`: Stop the rebase to edit the commit (amend).

After changing your git history, it might be necessary to use a force push to origin for the next push.

### Continue Interactive Rebase
```bash
# Continue the rebase
git rebase --continue
```

### Abort Interactive Rebase
```bash
# Abort the rebase
git rebase --abort
```

### Edit Commit
```bash
# Edit the commit
git commit --amend
```

## Deploy Keys
Deploy keys allow read-only or read-write access to a repository. They are useful for automated deployments or continuous integration systems.

## Git Stash
`git stash` is a command in Git that allows you to temporarily save changes that you have made but do not want to commit yet. It takes your modified tracked files and staged changes, saves them away for later use, and then reverts them to your last commit.

The stash is a place where you can store changes that you don't want to commit immediately. You can return to them later and apply them to your working tree.

Basic usage example:
- `git stash save "Your message"`: This command stashes your changes and allows you to add a message describing what the stash is for.
- `git stash list`: This command lists all of your stashes.
- `git stash apply`: This command applies the most recent stash. You can also specify a stash by its name to apply it.
- `git stash drop`: This command deletes the most recent stash. You can also specify a stash by its name to delete it.
- `git stash pop`: This command applies the most recent stash and then immediately drops it from your stash list. You can also specify a stash by its name to pop it.