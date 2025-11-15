Commit and push changes to remote repository

Usage: /commit-and-push

This command automates the process of committing and pushing changes:
1. Shows git status to see what files have changed
2. Shows git diff to display the actual changes
3. Stages all changes (modified and new files)
4. Creates a commit with an appropriate message
5. Pushes the commit to the remote repository

Requirements:
- Changes must be tracked (either modified files or new files to be added)
- Must be in a git repository with a configured remote
- User will be prompted for a commit message if needed

The command follows the project's commit message template format if configured.
