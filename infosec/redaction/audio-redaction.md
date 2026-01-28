# Audio Redaction

## Desktop Tools

### Audacity
**Platform:** Windows, macOS, Linux
**Cost:** Free, open source
**Website:** https://www.audacityteam.org/

Best free tool for audio redaction.

**Redaction workflow:**
1. Open audio file
2. Select region to redact
3. Generate > Silence (or Generate > Tone for beep)
4. Export as new file

**Keyboard shortcuts:**
- `Ctrl+L` - Silence selection
- `Ctrl+Shift+E` - Export

### FFmpeg (CLI)
**Platform:** Windows, macOS, Linux
**Cost:** Free, open source

```bash
# Silence a segment (e.g., 10-15 seconds)
ffmpeg -i input.mp3 -af "volume=enable='between(t,10,15)':volume=0" output.mp3

# Replace segment with beep tone
ffmpeg -i input.mp3 -i beep.wav -filter_complex \
  "[0:a]volume=enable='between(t,10,15)':volume=0[main]; \
   [1:a]adelay=10000|10000[beep]; \
   [main][beep]amix=inputs=2" output.mp3
```

### Adobe Audition
**Platform:** Windows, macOS
**Cost:** Subscription

Professional audio editor with:
- Spectral editing
- Noise reduction
- Batch processing

## Online Tools

### TwistedWave Online
**Website:** https://twistedwave.com/online
Simple browser-based audio editing for quick redactions.

## Mobile Apps

### Lexis Audio Editor (Android/iOS)
Free app with cut/silence features for basic redaction.

## Redaction Methods

### 1. Silence
- Replace segment with silence
- Clean, professional
- Makes redaction location obvious

### 2. Beep/Tone
- Replace with tone (typically 1kHz)
- Common in broadcast
- Clear indication of censorship

### 3. Noise
- Replace with static/white noise
- Less jarring than silence
- Still indicates redaction

### 4. Music/Sound Effect
- Cover with background sound
- Less obvious redaction
- May not be appropriate for formal evidence

## Considerations

### Timing
- Note exact timestamps of redactions
- Document what was redacted and why
- Keep redaction log with evidence file

### Voice Identification
Voices can identify people even if:
- Name not mentioned
- Face not visible in video
- Consider if voice itself is identifying

### Background Audio
- Conversations in background
- TV/radio playing
- Other voices in room

### Metadata
Audio files contain metadata (artist, title, recording date, software used). Remove after redaction:

```bash
# Remove metadata from audio file
ffmpeg -i input.mp3 -map_metadata -1 -c:a copy output.mp3

# Or with exiftool
exiftool -all= audio.mp3
```

## Transcript Alternative

For highly sensitive audio:
1. Create written transcript
2. Redact transcript (easier and more verifiable)
3. Use transcript as evidence instead of audio
4. Reference original exists under seal if needed

## Best Practices

1. **Work on copies** - Never modify original recordings
2. **Document everything** - Timestamps, what was redacted, who did it
3. **Verify playback** - Listen to full redacted file
4. **Remove metadata** - Strip identifying file information
5. **Consistent method** - Use same redaction style throughout
