# Fast Translation — update channel

This repository is the public update channel for **Fast Translation**. It exists because the
application source lives in a private repository, while update checks must work anonymously.

- `version.json` — the release manifest polled by the app (served via GitHub Pages).
- **Releases** — the installer (`FastTranslation-<version>-Setup.exe`) referenced by that manifest.

## Manifest format

```json
{
  "version": "1.1.0",
  "url": "https://github.com/LYW206817/FTranslation-Updates/releases/download/v1.1.0/FastTranslation-1.1.0-Setup.exe",
  "sha256": "<64 lowercase hex chars>",
  "size": 46303061,
  "notes": "What changed in this version.",
  "releasePage": "https://github.com/LYW206817/FTranslation-Updates/releases/tag/v1.1.0"
}
```

`version`, `url`, `sha256` and `size` are mandatory. `url` must be an absolute http(s) address
whose path ends in `.exe`; the app refuses anything else, and it verifies `size` and `sha256`
before running the installer.

## Privacy

The app fetches `version.json` and, when the user agrees, the installer. Nothing else is sent;
no identifiers, no telemetry.
