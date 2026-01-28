# Additional Metadata Tools

Supplementary tools for metadata extraction and analysis beyond ExifTool and MediaInfo.

## Image Metadata Libraries

### Metadata Extractor
- **Repository**: https://github.com/drewnoakes/metadata-extractor
- **Platforms**: Java, .NET
- **License**: Apache 2.0
- **Description**: Library for extracting metadata from image and video files
- **Supported Formats**: JPEG, TIFF, WebP, PSD, PNG, BMP, GIF, ICO, PCX, QuickTime, MP4, and more
- **Features**:
  - Extracts EXIF, IPTC, XMP, ICC profiles
  - GPS coordinate parsing
  - Makernote support for many camera manufacturers
  - Available for both Java and .NET ecosystems
- **Use Case**: Building custom metadata extraction tools or integrating into larger applications

## AI-Generated Image Tools

### Diffusion Toolkit
- **Repository**: https://github.com/RupertAvery/DiffusionToolkit
- **Platform**: Windows
- **Description**: Tool for browsing and managing AI-generated images with their generation metadata
- **Features**:
  - Browse images with embedded Stable Diffusion parameters
  - View prompts, seeds, samplers, CFG scale, and other generation settings
  - Search and filter by generation parameters
  - Supports multiple AI image generators (Automatic1111, ComfyUI, InvokeAI, etc.)
- **Use Case**: Examining AI-generated images for their creation parameters, useful for verifying claims about image provenance or detecting AI-generated content

### Dataset Tools
- **Repository**: https://github.com/Ktiseos-Nyx/Dataset-Tools
- **Description**: Utilities for working with AI training datasets and associated metadata
- **Features**:
  - Dataset metadata inspection
  - Caption/tag management
  - Training data organisation
- **Use Case**: Analysing datasets for metadata consistency, useful when investigating AI model training data or verifying dataset provenance

## When to Use These Tools

| Tool | Best For |
|------|----------|
| [ExifTool](exiftool.md) | General-purpose metadata for photos, videos, documents |
| [MediaInfo](mediainfo.md) | Detailed video/audio technical metadata |
| Metadata Extractor | Building custom tools, programmatic access |
| Diffusion Toolkit | Investigating AI-generated images |
| Dataset Tools | Analysing AI training datasets |

## Relevance to Evidence Work

As AI-generated content becomes more prevalent, understanding AI metadata is increasingly important:

- **Detecting synthetic media** - AI-generated images often contain telltale metadata
- **Verifying authenticity** - Legitimate photos typically have camera EXIF data that AI images lack
- **Investigating deepfakes** - Tools like Diffusion Toolkit can reveal generation parameters
- **Dataset provenance** - Understanding where training data originated

## Related

- [ExifTool](exiftool.md) - Industry-standard metadata tool
- [MediaInfo](mediainfo.md) - Video/audio metadata analysis
