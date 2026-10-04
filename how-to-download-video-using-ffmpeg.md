# Web Video & Image Downloading Guide with FFmpeg and Curl

This document provides a concise guide on how to download web videos (direct links, M3U8, MPD) and handle image downloading/conversion using FFmpeg and Curl, based on the provided PowerShell script commands.

--------------------------------------------------------------------------------

## 1. Downloading Web Videos using FFmpeg

FFmpeg allows direct downloading of video streams, including MP4 files, M3U8 (HLS), and MPD (DASH) playlists.

### Command & Parameter Breakdown:

```bash
ffmpeg -i "<VIDEO_URL>" -c copy -progress pipe:1 "<OUTPUT_PATH>"

# Parameter Breakdown:
# -i "<VIDEO_URL>"     : Input URL of the video (supports HTTP, HTTPS, M3U8, MPD).
# -c copy              : Copies audio and video streams directly without re-encoding (preserves original quality and maximizes speed).
# -progress pipe:1     : Outputs real-time processing progress to standard output (console/terminal).
# "<OUTPUT_PATH>"      : Destination path and filename (e.g., video_20261005_120000.mp4).
```

## 2. Downloading & Converting WEBP Images to JPG
When working with .webp images, processing involves downloading the source file using curl and converting it to .jpg using ffmpeg.

### Step 2.1: Download temporary WEBP file
```bash
curl.exe -s -o "temp_image.webp" "<IMAGE_URL>"

# Parameter Breakdown:
# -s                   : Silent mode (hides progress bars and error messages).
# -o                   : Specifies the output filename.
```

### Step 2.2: Convert WEBP to JPG using FFmpeg
```bash
ffmpeg -i "temp_image.webp" -q:v 2 "image.jpg" -y

# Parameter Breakdown:
# -i "temp_image.webp" : Input file path.
# -q:v 2               : Sets variable bit rate quality for JPEG output (scale 1–31, where 2 represents high quality).
# -y                   : Overwrites output files without asking.
```
