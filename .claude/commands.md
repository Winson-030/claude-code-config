# Claude Code Custom Commands

This file defines custom slash commands for Claude Code.

## Available Commands

### /config-info
Display current configuration information.

### /update-readme
Update the README.md with current project information.

### /git-status
Show detailed git status and recent commits.

### /project-summary
Provide a summary of the current project structure and files.

### /ipinfo
Check my ip using command `curl https://ipinfo.io`

### /commit-and-push
Commit and push changes to remote repository.

### /summarize-yt-video
Summarizes YouTube videos by downloading subtitles and creating a report.

## Usage

Type `/command-name` to execute any of these custom commands.

## Adding New Commands

To add a new command:
1. Add the command definition to this file
2. Create a corresponding implementation in the commands directory
3. Restart Claude Code to load the new command