# Git-Bootstrap 
*Git repo initialization helper

A bash script that streamlines the process of initializing a Git repository, setting up remotes, and handling synchronization issues.

## Features

- Initializes a Git repository if one doesn't exist
- Sets up or updates the remote origin
- Handles branch creation and switching
- Automatically resolves common synchronization issues between local and remote repositories
- Supports both rebase and merge strategies when pulling changes

## Usage

```bash
./init-repo.sh <remote-url> [branch]
```

### Parameters

- `remote-url`: The URL of the remote repository (required)
- `branch`: The branch name to use (optional, defaults to `main`)

### Examples

```bash
# Initialize with default branch (main)
./init-repo.sh https://github.com/username/repository.git

# Initialize with a specific branch
./init-repo.sh https://github.com/username/repository.git develop
```

## What It Solves

This script addresses common Git initialization issues:

1. **Remote synchronization**: Automatically pulls remote changes before pushing to avoid "non-fast-forward" errors
2. **Branch management**: Creates and switches to the desired branch
3. **Empty repository setup**: Handles both empty and non-empty repositories
4. **Initial commit**: Creates an initial commit if none exists

## Requirements

- Git installed and configured
- Bash shell

## How It Works

1. Checks if the current directory is a Git repository, initializes if not
2. Ensures the specified branch exists and switches to it
3. Creates an initial commit if needed
4. Sets up or updates the remote origin
5. Fetches from the remote to check for differences
6. Automatically pulls changes using rebase (falls back to merge if needed)
7. Sets upstream tracking and pushes changes

## Common Scenarios Handled

- Initializing an existing project with an empty remote repository
- Cloning a project without using `git clone`

## License

This script is provided as-is for educational and practical use. Feel free to modify and distribute as needed.