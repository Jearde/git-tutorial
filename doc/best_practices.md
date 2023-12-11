# Best Practices
Next section: [Tips and Tricks](additions.md)

## Naming the repository
Repository name: 
`<companyshort>_<project>-<module>_<type>`

Types can be:
- `doc` for documentation
- `sw` for software
- `hw` for hardware
- `fw` for firmware

Examples:
- `ai_git-tutorial_doc`

## Commit messages
- Use the imperative mood
- Limit the first line to 50 characters
- Capitalize the first letter
- Do not end the first line with a period
- Use the body to explain what and why vs. how

Examples:
```
Add world_2.txt

Add a new file named world_2.txt to the repository.
```

## Implementation Workflow
- Create an issue with the description of what to implement in GitHub/GitLab
- (Optional) Add tasks to the description
- Assign task (to yourself)
- Select label (e.g. bug, enhancement, ...)
- (Optional) Add milestone
- (Optional) Add due date
- Create a new branch which is connected to the issue (In GitLab it might not be possible to connect an existing branch to the issue)
- Switch to the new branch
```bash
git fetch origin
git switch <branch>
```
- Implement the feature
- Commit the changes
- Rebase with the main branch
```bash
git fetch origin
git rebase origin/main
```
- Push the changes to the remote repository
- Create a merge request
- Assign merge request to reviewer
- Review the changes
- Approve the merge request
- Merge the changes into the main branch
    - Squash commits (if )
- Close the issue