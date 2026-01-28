# Document Redaction Tools

## PDF Redaction

### Adobe Acrobat Pro
**Platform:** Windows, macOS
**Cost:** Subscription

Industry standard with proper redaction:
- Redact tool removes content permanently
- Search and redact feature
- Metadata removal
- **Not just visual overlay** - actually removes data

### PDF-XChange Editor
**Platform:** Windows
**Cost:** Free version available
**Website:** https://www.tracker-software.com/

- True redaction (content removal)
- Whiteout and blackout tools
- Batch processing

### LibreOffice Draw
**Platform:** Windows, macOS, Linux
**Cost:** Free, open source

1. Open PDF in Draw
2. Add black rectangles over sensitive content
3. Export as PDF
4. **Note:** This is overlay-based; consider flattening

### qpdf + Overlay Method
```bash
# Flatten PDF to remove layers
qpdf --flatten-annotations=all input.pdf output.pdf
```

## Important: True vs Visual Redaction

### True Redaction (Safe)
- Content is permanently removed from file
- Cannot be recovered
- Tools: Acrobat Pro "Redact" tool, PDF-XChange

### Visual Redaction (Unsafe)
- Black box drawn over content
- Text still exists and is selectable/searchable
- Can be removed to reveal original
- **Never rely on this for sensitive data**

### Testing Your Redaction
1. Try selecting text under the redaction
2. Use PDF text extraction tools
3. Open in text editor and search for redacted content

## Word/Office Documents

### Microsoft Word
**Track Changes + Final View method (Unsafe):**
- Hidden changes can be revealed
- Metadata contains revision history

**Safe method:**
1. Accept all changes
2. Remove personal info (File > Info > Check for Issues)
3. Save as PDF
4. Redact PDF properly

### LibreOffice Writer
1. Edit document
2. Remove PII directly from text
3. Export as PDF
4. Verify no hidden data

## Metadata Removal

### PDF Metadata
```bash
# View metadata
exiftool document.pdf

# Remove all metadata
exiftool -all= document.pdf

# Or use qpdf
qpdf --linearize --replace-input document.pdf
```

### Office Documents
- Word: File > Info > Check for Issues > Inspect Document
- Remove: Comments, revisions, personal info, hidden text

## Best Practices

1. **Never use highlight** - Use proper redaction tools
2. **Remove metadata** - Author, creation date, revision history
3. **Flatten PDFs** - Remove layers that could hide content
4. **Test the result** - Try to extract redacted content
5. **Work on copies** - Preserve original documents
6. **Document redactions** - Keep record of what was redacted
