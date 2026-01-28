# Browser Extensions for Web Evidence Capture

Browser extensions for capturing and preserving web page content as evidence.

## Chrome Extensions

### SingleFile
- **Chrome Web Store**: https://chromewebstore.google.com/detail/singlefile/mpiodijhokgodhhofbcjdecpffjipkle
- **Description**: Saves a complete web page into a single HTML file, including images, styles, and scripts
- **Why It's Useful**:
  - One of the simplest yet most effective tools for web archiving
  - No external dependencies or accounts required
  - Preserves page exactly as rendered
  - Single file output is easy to store and share
- **Features**:
  - Saves entire page as single .html file
  - Embeds images as base64
  - Preserves CSS styling
  - Optional: remove hidden elements, scripts
  - Batch save multiple tabs
  - Annotations support
- **Also Available For**: Firefox, Edge, Opera, Safari

### ImageEye (Image Downloader)
- **Chrome Web Store**: https://chromewebstore.google.com/detail/image-downloader-imageye/agionbommeaifngbhincahgmoflcikhm
- **Website**: https://www.imageye.net/
- **Description**: Bulk download all images from a web page with filtering options
- **Why It's Useful**:
  - Quickly capture all images from a page as separate files
  - Useful when you need original image files rather than embedded in HTML
  - Filter by size, type, or URL pattern
- **Features**:
  - Detects all images on page (including background images)
  - Filter by dimensions, file type
  - Bulk select and download
  - Preview before downloading
  - Rename files during download
- **Use Case**: Capturing image evidence from social media, websites, or galleries where you need individual files

## Best Practices for Web Evidence

1. **Capture immediately** - Web content can change or disappear at any time
2. **Save the URL** - Document the original URL alongside the saved file
3. **Note the timestamp** - Record when you captured the page
4. **Calculate checksum** - Generate SHA-256 hash of saved file for integrity
5. **Consider multiple methods** - Use both browser extension and archive services (e.g., archive.org) for redundancy
6. **Capture full page** - Ensure scrolling content is fully loaded before saving

## Limitations

- Dynamic content (e.g., infinite scroll) may not fully capture
- Login-required pages capture your authenticated view
- Some sites block or detect archiving attempts
- JavaScript-heavy sites may not render correctly when reopened offline

## Complementary Tools

- **Hunchly** - Professional web capture for investigations (see [investigations/hunchly.md](../../investigations/hunchly.md))
- **archive.org Wayback Machine** - Public web archiving service
- **archive.today** - Alternative archiving service
