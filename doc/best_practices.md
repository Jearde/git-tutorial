# Best Practices
Next section: [More Tips and Tricks](additions.md)

## General
1. Commit Often, Commit Thoughtfully:
    - Make small, focused commits with clear and concise commit messages.
    - Commit related changes together to create a meaningful history.
2. Use Descriptive Commit Messages:
    - Write informative commit messages that explain the purpose of the changes.
    - Follow a consistent format for commit messages (e.g., start with a verb in the imperative mood).
3. Create Feature Branches:
    - Use branches for new features, bug fixes, or experiments.
    - Keep the main branch (often master or main) stable.
4. Regularly Pull from Upstream:
    - Keep your local branches up-to-date by pulling changes from the remote repository.
    - Avoid long-lived branches that can diverge significantly from the main branch.
5. Interactive Rebasing:
    - Use interactive rebasing (git rebase -i) to clean up your commit history before pushing.
    - Squash or reword commits to maintain a clean and logical history.
6. Avoid Pushing Directly to Main/Branch:
    - Create a pull request for code review before merging changes into the main branch.
    - This promotes collaboration and helps catch issues early.
7. Code Reviews:
    - Conduct thorough code reviews for all changes.
    - Provide constructive feedback and address issues before merging.
8. Use .gitignore:
    - Utilize a .gitignore file to exclude unnecessary files (build artifacts, logs) from version control.
9. Tag Releases:
    - Tag releases with version numbers to easily reference specific points in your project's history.
10. Use Git Hooks:
    - Implement pre-commit and post-commit hooks to automate checks and tasks.
    - For example, running linters, tests, or formatting tools.
11. Document Your Workflow:
    - Include a README file with instructions for setting up the project and any specific workflow guidelines.
12. Keep Sensitive Information Secure:
    - Avoid committing sensitive information (passwords, API keys).
    - Use environment variables or configuration files outside version control for such information.
13. Backup Important Branches:
    - Regularly backup important branches, especially before performing significant rebases or force-pushes.
14. Use GitHub Issues and Projects:
    - Leverage GitHub Issues for tracking tasks, bugs, and enhancements.
    - Use GitHub Projects to manage and organize work.

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
It implements the second part of the "Hello World" example.
```

## Implementation Workflow
- Create an issue with the description of needs to be implemented in GitHub/GitLab
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
- Rebase with the main branch (best to do this once a day on a busy project)
```bash
git fetch origin
git rebase origin/main
```
- Push the changes to the remote repository
- Create a merge request (when done)
- Assign merge request to reviewer
- Review the changes
- Approve the merge request
- Merge the changes into the main branch
    - Squash commits (if used in the project)
- Close the issue