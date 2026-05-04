# config-sanitize

**Strip secrets from your configs — 100% local, nothing sent anywhere.**

Paste your Frigate, Home Assistant, Docker Compose, .env files, or any other config containing credentials. Get back a redacted version safe to share.

[Try it live →](https://veezuhz.github.io/config-sanitize)

## Features

✅ **100% Local Processing** — All redaction happens in your browser  
✅ **No Network Requests** — Your config never leaves your computer  
✅ **No Storage** — Nothing is saved or cached  
✅ **Open Source** — Audit the logic yourself  
✅ **Multi-Format Support** — YAML, Docker Compose, .env, JSON, Proxmox, WireGuard, and more  
✅ **Smart Redaction** — Detects 25+ credential patterns  
✅ **Side-by-Side Diff** — See exactly what changed  
✅ **Scan Report** — Detailed stats on redactions  

## Supported Patterns

Detects and redacts:
- URL-embedded credentials (rtsp://user:pass@host)
- Database connection strings
- API keys (OpenAI, GitHub, Anthropic, etc.)
- JWT tokens
- SSH private keys & PEM blocks
- Discord & Slack webhook URLs
- WireGuard & Tailscale keys
- Zigbee/Z-Wave network keys
- HTTP Basic Auth headers
- And 15+ more patterns

## Why Trust This?

**No Network Requests** — Open DevTools → Network tab stays empty  
**Works Offline** — Turn off WiFi after loading; tool keeps working  
**Nothing Stored** — Run `Object.keys(localStorage)` in console; returns empty  
**Source Visible** — Right-click → View Source; read the redaction logic  

## How It Works

Each line is processed through regex patterns:
- `scheme://user:pass@host` → `scheme://<REDACTED>:<REDACTED>@host`
- `API_KEY=abc123` → `API_KEY=<REDACTED>`
- `password: secret` → `password: <REDACTED>`
- And 25+ more patterns...

## Keyboard Shortcuts

- **Ctrl+−** / **Cmd+−** — Decrease font size
- **Ctrl++** / **Cmd++** — Increase font size
- **Ctrl+0** / **Cmd+0** — Reset font size

## Self-Hosting

This is a single HTML file:

1. Download `index.html`
2. Place on any web server
3. Open in a browser

Or use locally: open `index.html` directly in your browser.

## Contributing

Found a missing pattern? Have a config format we don't support?

1. Fork this repo
2. Edit the `patterns` array in `index.html`
3. Test with sample configs
4. Open a Pull Request

## License

MIT — Use freely, modify, and share.

## Disclaimer

While designed to redact common secrets, **no sanitizer is 100% perfect**. Always manually review before sharing publicly. Look for:
- Custom or unusual secret formats
- API keys in comments
- Hostnames or IPs you want private
- Any other sensitive data

**When in doubt, don't share it.**

---

Built for homelabbers by homelabbers. 🏠
