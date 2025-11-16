Summarize YouTube Video

Usage: /summarize-yt-video <youtube_url>

This command downloads YouTube video subtitles and creates a summary report.

Requirements:
- yt-dlp must be installed
- A valid YouTube video URL

Process (中文):
1. 创建 yt-subtitle/ 目录（如果不存在）
2. 提取视频信息（标题、频道等）
3. 创建视频专属文件夹 yt-subtitle/{video_name}/
4. 下载中英文字幕文件（.srt 格式）
5. 读取并分析字幕内容
6. 使用 AI 生成中文摘要报告
7. 保存摘要到 yt-subtitle/{video_name}/summary.md

Process (English):
1. Creates directory yt-subtitle/ if it doesn't exist
2. Extracts video information (title, channel, etc.)
3. Creates folder yt-subtitle/{video_name}/ for this video
4. Downloads Chinese and English subtitle files (.srt format)
5. Reads and analyzes the subtitle content
6. Generates Chinese summary report using AI
7. Saves summary to yt-subtitle/{video_name}/summary.md

The summary includes (摘要内容包括):
- Video metadata (视频元数据：标题、频道、时长、URL)
- Key topics and themes (关键主题和话题)
- Important points discussed (讨论的重点内容)
- Timeline of major sections (主要章节的时间线)
- Sentiment or tone analysis (情感或语气分析)

Note (注意): Some videos may not have subtitles available. The command will attempt to download auto-generated subtitles if manual subtitles are not available. This command downloads both Chinese and English subtitles (when available) and generates the summary in Chinese.

Implementation Steps:
1. First, this document will guide Claude to execute the command
2. Extract video title from URL using yt-dlp
3. Create directory structure: yt-subtitle/{sanitized_video_title}/
4. Download subtitles using: yt-dlp --write-subs --write-auto-subs --sub-langs "en.*,zh.*,zh-Hans.*,zh-Hant.*" --skip-download --sub-format srt -o "yt-subtitle/{video_title}/%(title)s.%(ext)s" {youtube_url}
5. Find downloaded .srt file(s) in the directory
6. Read the subtitle file and parse timestamps and text (prefer Chinese if available)
7. Use AI to generate a comprehensive summary in **Chinese (中文)**
8. Create summary.md with video metadata and Chinese summary
9. Present the completed summary to the user

Example usage:
/summarize-yt-video https://www.youtube.com/watch?v=dQw4w9WgXcQ
