Summarize YouTube Video

Usage: /summarize-yt-video <youtube_url>

This command downloads YouTube video subtitles and creates a summary report.

Requirements:
- yt-dlp must be installed
- A valid YouTube video URL

Process:
1. Creates directory yt-subtitle/ if it doesn't exist
2. Extracts video information (title, channel, etc.)
3. Creates folder yt-subtitle/{video_name}/ for this video
4. Downloads subtitle file (original language, .srt format)
5. Reads and analyzes the subtitle content
6. Generates a summary report as markdown file
7. Saves summary to yt-subtitle/{video_name}/summary.md

The summary includes:
- Video metadata (title, channel, duration, URL)
- Key topics and themes
- Important points discussed
- Timeline of major sections
- Sentiment or tone analysis

Note: Some videos may not have subtitles available. The command will attempt to download auto-generated subtitles if manual subtitles are not available.

Implementation Steps:
1. First, this document will guide Claude to execute the command
2. Extract video title from URL using yt-dlp
3. Create directory structure: yt-subtitle/{sanitized_video_title}/
4. Download subtitles using: yt-dlp --write-subs --write-auto-subs --sub-langs "en.*" --skip-download --sub-format srt -o "yt-subtitle/{video_title}/%(title)s.%(ext)s" {youtube_url}
5. Find downloaded .srt file in the directory
6. Read the subtitle file and parse timestamps and text
7. Use AI to generate a comprehensive summary
8. Create summary.md with video metadata and summary
9. Present the completed summary to the user

Example usage:
/summarize-yt-video https://www.youtube.com/watch?v=dQw4w9WgXcQ
