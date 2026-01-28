# Image Redaction Tools

## Desktop Tools

### GIMP
**Platform:** Windows, macOS, Linux
**Cost:** Free, open source
**Website:** https://www.gimp.org/

Best for precise redaction with full control.

**Redaction workflow:**
1. Open image
2. Select region with rectangle/free select tool
3. Fill with solid color (Edit > Fill with FG Color)
4. Flatten and export as new file

### ImageMagick (CLI)
**Platform:** Windows, macOS, Linux
**Cost:** Free, open source

Batch redaction via command line.

```bash
# Draw black rectangle over region
convert input.jpg -fill black -draw "rectangle 100,100 300,200" output.jpg

# Blur a region instead
convert input.jpg -region 200x100+100+100 -blur 0x8 output.jpg
```

### Photoshop
**Platform:** Windows, macOS
**Cost:** Subscription

Professional option with precise tools.

## Online Tools

### Redacted.app
**Website:** https://redacted.app/
**Platform:** Web, iOS

- Quick browser-based redaction
- Pixelate, blur, or black box
- No account required
- **Note:** Uploads image to server

### Facepixelizer
**Website:** https://www.facepixelizer.com/
**Platform:** Web

- Automatic face detection
- Client-side processing (image not uploaded)
- Blur or pixelate faces

## Mobile Apps

### Photo Editor (Various)
Most photo editing apps include:
- Markup/drawing tools
- Blur brushes
- Solid shape overlays

### Signal
The Signal messaging app has built-in face blur for photos before sending.

## Best Practices

1. **Use solid fills, not blur** - Blur can potentially be reversed
2. **Extend beyond edges** - Cover slightly more than the PII
3. **Check zoomed view** - Ensure nothing visible at edges
4. **Strip metadata after** - Use ExifTool to remove remaining metadata
5. **Save as new file** - Never overwrite original

## Removing Metadata After Redaction

```bash
# Remove all metadata from redacted image
exiftool -all= redacted_image.jpg

# Or copy with no metadata
exiftool -all= -o clean_image.jpg redacted_image.jpg
```
