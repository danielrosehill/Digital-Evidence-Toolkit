# Video Redaction Tools

## Desktop Tools

### Kdenlive
**Platform:** Windows, macOS, Linux
**Cost:** Free, open source
**Website:** https://kdenlive.org/

Full video editor with redaction capabilities.

**Face blur workflow:**
1. Import video
2. Add Transform or Obscure effect
3. Keyframe the position to track movement
4. Export redacted version

### DaVinci Resolve
**Platform:** Windows, macOS, Linux
**Cost:** Free version available
**Website:** https://www.blackmagicdesign.com/products/davinciresolve

Professional editor with face tracking.

**Features:**
- Automatic face tracking in Fusion
- Blur/mosaic effects
- Audio redaction tools

### FFmpeg (CLI)
**Platform:** Windows, macOS, Linux
**Cost:** Free, open source

Command-line video processing.

```bash
# Blur a fixed region (x:y:width:height)
ffmpeg -i input.mp4 -vf "boxblur=10:enable='between(t,5,10)':x=100:y=100:w=200:h=200" output.mp4

# Black box over region
ffmpeg -i input.mp4 -vf "drawbox=x=100:y=100:w=200:h=150:color=black:t=fill" output.mp4

# Mute audio segment (5-10 seconds)
ffmpeg -i input.mp4 -af "volume=enable='between(t,5,10)':volume=0" output.mp4
```

### Shotcut
**Platform:** Windows, macOS, Linux
**Cost:** Free, open source
**Website:** https://shotcut.org/

Simpler editor for basic redaction.

## Specialized Tools

### Briar
**Website:** https://briar.com/ (Note: research current availability)

Purpose-built for video redaction, includes:
- Face tracking
- License plate detection
- Batch processing

### YouTube Studio
For videos you control on YouTube:
- Built-in face blur feature
- Custom blur regions
- Automatic face detection

## Mobile Tools

### CapCut / InShot
Mobile video editors with blur/mosaic effects. Manual tracking required.

## Considerations for Video

1. **Motion tracking** - Faces/objects move; static blur insufficient
2. **Audio** - Voice can identify people; consider muting or bleeping
3. **Background details** - Addresses, signs, reflections can reveal location
4. **File size** - Re-encoding may significantly change file size
5. **Frame-by-frame** - Quick movements may reveal unblurred frames

## Automated Face Detection

Some tools offer automatic face detection:
- DaVinci Resolve (Fusion face tracking)
- YouTube's blur faces feature
- Dedicated anonymization software

**Caution:** Always verify automated detection caught all faces/instances.

## Audio Redaction in Video

```bash
# Mute entire audio track
ffmpeg -i input.mp4 -an output.mp4

# Beep over segment (requires beep audio file)
ffmpeg -i input.mp4 -i beep.wav -filter_complex "[0:a]volume=enable='between(t,5,8)':volume=0[a];[a][1:a]amix=inputs=2" output.mp4
```

## Preserving Evidence Integrity

1. **Work on copies** - Never modify original video files
2. **Document redactions** - Note what was redacted and why
3. **Keep redaction map** - Timestamps of what was obscured
4. **Maintain chain of custody** - Log who made redactions and when
