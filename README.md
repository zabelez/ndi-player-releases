# NDI Player — public releases

This repository **only publishes installer builds**. Source code stays in a private repo.

## Download

Latest installer:

**https://github.com/zabelez/ndi-player-releases/releases/latest**

Each release typically includes:

- installer ISO
- `.sha256` checksum

Verify after download:

```bash
sha256sum -c ndi-player-*.iso.sha256
```

## Source

The application source is not here. Do not open pull requests against this repo.

## OTA / catalog

Players can fetch a published asset with:

`https://github.com/zabelez/ndi-player-releases/releases/latest/download/<filename>`
