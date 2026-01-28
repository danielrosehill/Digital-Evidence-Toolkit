# Tor Browser

**Platform:** Windows, macOS, Linux, Android
**Cost:** Free, open source
**Website:** https://www.torproject.org/

## Overview

Tor Browser routes your traffic through multiple encrypted relays, providing stronger anonymity than VPNs for sensitive investigations.

## When to Use Tor

- Investigating subjects who actively monitor visitors
- Accessing .onion sites
- When VPN-level privacy is insufficient
- Research that could put you at risk if identified

## Installation

Download only from official source: https://www.torproject.org/download/

Verify the download signature to ensure authenticity.

## Best Practices

1. **Don't maximize the window** - Screen size can fingerprint you
2. **Don't install extensions** - Can compromise anonymity
3. **Use "Safest" security level** - Disables JavaScript
4. **Don't log into personal accounts** - Links identity
5. **Don't torrent over Tor** - Leaks IP and overwhelms network
6. **New identity frequently** - Use Tor's "New Identity" feature

## Limitations

- Slow compared to direct connections
- Some sites block Tor exit nodes
- Exit node can see unencrypted traffic
- Vulnerable to traffic correlation attacks
- Doesn't protect against browser exploits

## Tor vs VPN

| Factor | Tor | VPN |
|--------|-----|-----|
| Anonymity | Higher | Lower |
| Speed | Slower | Faster |
| Blocked sites | More common | Less common |
| Trust required | None (decentralized) | VPN provider |
| Cost | Free | Usually paid |

## Combining Tor and VPN

- **VPN then Tor**: ISP sees VPN, Tor entry sees VPN
- **Tor then VPN**: ISP sees Tor, destination sees VPN
- Both approaches have tradeoffs; research before implementing

## For Evidence Capture

Tor Browser can be combined with screenshot tools for capturing evidence, but:
- Timestamps should be independently verified
- Page content may differ from non-Tor view
- Some dynamic content may not load
