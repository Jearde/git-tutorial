# Work with remotes (e.g. GitHub, GitLab)

## Differences between local and remote repositories
- Local repositories are on your computer
- Remote repositories are on a server (e.g. GitHub, GitLab)

## Basic commands
- `git remote add <name> <url>`
    - Adds a remote with the specified name and url
    - The name is usually "origin"
    - The url is usually the url of a remote repository
    - Example HTTPS: `git remote add origin https://<url>`
    - Example SSH: `git remote add origin git@<url>`
- `git remote -v`
    - Lists all of the remotes
- `git remote set-url <name> <url>`
    - Changes the url of the remote named "origin"
    - Example HTTPS: `git remote set-url origin https://<url>`
    - Example SSH: `git remote set-url origin git@<url>`
- `git push <remote> <branch>`
    - Pushes the specified branch to the specified remote
    - Example: `git push origin main`
- `git pull <remote> <branch>`
    - Pulls the specified branch from the specified remote
    - Example: `git pull origin main`
- `git clone <url>`
    - Clones the specified remote repository into a new local repository
    - Example: `git clone <url>`
- `git fetch <remote>`
    - Fetches the latest changes from the specified remote
    - Example: `git fetch origin`
- `git merge <remote>/<branch>`
    - Merges the specified remote branch into the current branch
    - Example: `git merge origin/main`
- `git branch -r`
    - Lists all of the remote branches
- `git branch -a`
    - Lists all of the local and remote branches
- `git switch <remote>/<branch>`
    - Switches to the specified remote branch
    - Example: `git switch origin/main`

## Differences between https and ssh
- HTTPS
    - Requires a username and password for authentication
- SSH
    - Requires an SSH key pair (public and private key) for authentication

### Creating an SSH key pair
- `ssh-keygen -t ed25519 -C "your_email@example.com"`
    - Creates a new SSH key pair in the default location (`~/.ssh`)
    - (Optional) Specify a different location for the key pair
        - `-f ~/.ssh/id_ed25519`
    - `-t ed25519` specifies the type of key to create
    - `-C "your_email@example.com"` specifies the email address to use
- Add the SSH key to your GitHub account
    - Copy the contents of the public key file (e.g. `id_ed25519.pub`)
    - Go to your GitHub account settings
    - Click on "SSH and GPG keys"
    - Click on "New SSH key"
    - Paste the contents of the public key file into the "Key" field
    - Click on "Add SSH key"

![](https://miro.medium.com/v2/resize:fit:720/format:webp/1*YtHZxDoRGyFi7RVqD8sk9g.png)

## Remote Exercises

### Exercise 1: Pushing to a new Remote Repository
- Create a new repository on GitHub
```bash
# Create a new repository on GitHub
# Copy the repository url

# Add the remote repository
git remote add origin <url>

# Push the main branch to the remote repository
# -u sets the upstream branch to origin/main so that you can use "git push" and "git pull" without specifying the remote and branch
git push -u origin main
```

### Exercise 2: Cloning a Remote Repository
- Clone a remote repository
```bash
# Clone the remote repository
git clone <url>

# Switch to the new repository
cd <repository_name>
```