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
# Rebase the last 3 commits
git rebase -i <commit>
```

### Edit Commit
```bash
# Edit the commit
git commit --amend
```

## Deploy Keys
Deploy keys allow read-only or read-write access to a repository. They are useful for automated deployments or continuous integration systems.