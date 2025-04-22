# Git Basic Commands

## Initialization

- `git init`: Initialize a new Git repository.

## Configuration

- `git config --global user.name "Your Name"`: Set the global username.
- `git config --global user.email "your.email@example.com"`: Set the global email.

## Cloning

- `git clone <repository-url>`: Clone a repository to your local machine.

## Staging and Committing

- `git add <file>`: Stage a specific file.
- `git add .`: Stage all changes in the current directory.
- `git commit -m "Commit message"`: Commit staged changes with a message.

## Branching

- `git branch`: List all branches.
- `git branch <branch-name>`: Create a new branch.
- `git checkout <branch-name>`: Switch to a specific branch.
- `git checkout -b <branch-name>`: Create and switch to a new branch.

## Merging

- `git merge <branch-name>`: Merge a branch into the current branch.

## Pull and Push

- `git pull`: Fetch and merge changes from the remote repository.
- `git push`: Push local changes to the remote repository.

## Status and Logs

- `git status`: Show the working directory status.
- `git log`: Show the commit history.

## Undoing Changes

- `git reset <file>`: Unstage a file.
- `git reset --hard`: Reset the working directory and staging area to the last commit.

## Deleting

- `git branch -d <branch-name>`: Delete a branch locally.
- `git rm <file>`: Remove a file from the repository and working directory.

## Remote Repositories

- `git remote -v`: List remote repositories.
- `git remote add <name> <url>`: Add a new remote repository.

## Tagging

- `git tag <tag-name>`: Create a new tag.
- `git tag`: List all tags.

## Help

- `git help <command>`: Get help for a specific Git command.
