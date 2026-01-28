# ExifTool

**Platform:** Windows, macOS, Linux (CLI)
**Cost:** Free, open source
**Website:** https://exiftool.org/

## Overview

ExifTool is the industry-standard command-line utility for reading, writing, and editing metadata in images, audio, video, and document files. Essential for examining evidence authenticity and extracting hidden information.

## Installation

**Linux (Debian/Ubuntu):**
```bash
sudo apt install libimage-exiftool-perl
```

**macOS:**
```bash
brew install exiftool
```

**Windows:**
Download from https://exiftool.org/ and add to PATH.

## Basic Usage

**View all metadata:**
```bash
exiftool photo.jpg
```

**View specific tags:**
```bash
exiftool -DateTimeOriginal -GPSLatitude -GPSLongitude photo.jpg
```

**Export to JSON:**
```bash
exiftool -json photo.jpg > metadata.json
```

**Process entire directory:**
```bash
exiftool -r /path/to/evidence/
```

## Key Metadata Fields for Evidence

### Photos
- `DateTimeOriginal` - When photo was taken
- `CreateDate` - File creation time
- `ModifyDate` - Last modification
- `GPSLatitude` / `GPSLongitude` - Location coordinates
- `Make` / `Model` - Camera/phone used
- `Software` - Editing software (indicates modification)

### Videos
- `CreateDate` / `MediaCreateDate`
- `Duration`
- `VideoFrameRate`
- `AudioChannels`

### Documents
- `Author`
- `Creator`
- `CreateDate` / `ModifyDate`
- `Producer` (PDF)

## Detecting Manipulation

Signs a file may have been edited:
- `Software` tag shows editing application (Photoshop, GIMP)
- `ModifyDate` differs significantly from `CreateDate`
- Missing EXIF data that should be present
- Inconsistent metadata between similar files

```bash
# Check for editing software
exiftool -Software -Creator -Producer file.jpg
```

## Preserving Original Metadata

When copying files, preserve metadata:
```bash
exiftool -TagsFromFile original.jpg -all:all copy.jpg
```

## GUI Alternatives

- **ExifToolGUI** (Windows) - https://exiftool.org/gui/
- **jExifToolGUI** (Cross-platform) - Java-based GUI
- **Metapho** (iOS) - Mobile metadata viewer
- **Photo Exif Editor** (Android)

## Web-Based Tools

- **Jeffrey's Exif Viewer** - https://exif.regex.info/exif.cgi
- **Exif.tools** - https://exif.tools/
- **FotoForensics** - https://fotoforensics.com/ (also does ELA analysis)

## Resources

- [ExifTool Tag Names](https://exiftool.org/TagNames/)
- [ExifTool FAQ](https://exiftool.org/faq.html)
