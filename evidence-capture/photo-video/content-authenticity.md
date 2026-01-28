# Content Authenticity Initiative (CAI)

**Type:** Industry Standard
**Cost:** Free (verification), varies (hardware)

## Overview

The Content Authenticity Initiative is an industry coalition developing open standards for certifying the origin and history of digital media. It embeds cryptographic provenance data directly into image files.

## How It Works

1. Capture device signs the image at creation time
2. Metadata records capture details, edits, and chain of custody
3. Cryptographic signatures verify authenticity
4. Verification tools validate the provenance chain

See: [How It Works - Content Authenticity](https://contentauthenticity.org/how-it-works)

## Hardware with Built-in Support

Some cameras and phones now include hardware-level content authenticity certification:

### Cameras

- **Leica M11-P** - First camera with built-in Content Credentials
- **Leica SL3** - Content Credentials support
- **Sony (select models)** - In-camera signing capability
- **Nikon (select models)** - Image authentication features

### Camcorders

- **Sony PXW-Z300** - First camcorder with C2PA signing support

### Smartphones

- **Google Pixel** - C2PA support available
  - **Note:** You must use the official Google Camera app for C2PA signing to work. Third-party camera apps will not include content credentials.

Hardware-level signing provides stronger guarantees than software-only solutions since the signature is created at the moment of capture.

For current lists of supported devices, see:
- [C2PA Viewer - Supported Devices](https://c2paviewer.com/supported-devices)
- [Digital Cameras with C2PA Support](https://c2pa.camera)

## Verification

Use the official verification tool to check content credentials:

**[Content Authenticity Verify Tool](https://verify.contentauthenticity.org/)**

Upload an image to:
- Check if it has content credentials
- View the provenance chain
- Verify signatures

## Use for Evidence

Content Credentials can strengthen evidence by:
- Proving capture device and time
- Showing edit history (or lack thereof)
- Providing cryptographic verification
- Creating chain of custody from capture

## Considerations

- Requires compatible hardware for strongest guarantees
- Standard is still evolving
- Not all platforms preserve credentials
- Verification requires the credentials to remain intact

## Resources

- [Content Authenticity Initiative](https://contentauthenticity.org/)
- [Verify Tool](https://verify.contentauthenticity.org/)
- [C2PA Technical Specification](https://c2pa.org/)

## Related

- [ProofMode](proofmode.md) - Software-based alternative for mobile
