# MediaInfo

**Platform:** Windows, macOS, Linux (CLI and GUI)
**Cost:** Free, open source
**Website:** https://mediaarea.net/en/MediaInfo

## Overview

MediaInfo provides detailed technical information about video and audio files. Useful for verifying file authenticity, checking encoding details, and extracting timestamps from media evidence.

## Installation

**Linux (Debian/Ubuntu):**
```bash
sudo apt install mediainfo mediainfo-gui
```

**macOS:**
```bash
brew install mediainfo
```

**Windows:**
Download from https://mediaarea.net/en/MediaInfo/Download

## Basic Usage

**View all information:**
```bash
mediainfo video.mp4
```

**Specific output format:**
```bash
mediainfo --Output=JSON video.mp4
mediainfo --Output=XML video.mp4
```

**Key fields only:**
```bash
mediainfo --Inform="General;%Duration%\n%FileSize%\n%Encoded_Date%" video.mp4
```

## Key Fields for Evidence

### General
- `Encoded_Date` - When file was encoded
- `Tagged_Date` - Tagging timestamp
- `File_Modified_Date` - Last modification
- `Duration` - Length of recording

### Video Stream
- `Format` - Codec (H.264, HEVC, etc.)
- `Width` / `Height` - Resolution
- `FrameRate` - Frames per second
- `BitRate` - Quality indicator

### Audio Stream
- `Format` - Audio codec
- `Channels` - Mono/Stereo
- `SamplingRate` - Audio quality

## Detecting Re-encoding

Signs a video may have been re-encoded or edited:
- `Encoded_Date` much later than claimed recording date
- Encoding software metadata present
- Unusual codec for the claimed source device
- Bitrate inconsistent with original recording

## Comparison with ExifTool

| Tool | Best For |
|------|----------|
| ExifTool | Photos, documents, broad format support |
| MediaInfo | Video/audio technical details, codec info |

Use both for comprehensive media analysis.

## GUI Version

MediaInfo-GUI provides a user-friendly interface for non-technical users:
- Tree view of all metadata
- Export to text/HTML reports
- Drag-and-drop support
