# ndi-player-releases (v0.17.1)

Public install images and signed OTA updates for **NDI Player**.

**v0.17.1** is the current release on this channel. Use the ISO for new machines; use OTA from the web UI for upgrades. One ISO fits all supported PCs.

## Downloads

| File | Purpose |
|------|---------|
| `ndi-player-0.17.1.iso` | Fresh install (Debian + NDI Player). **Erases target disk.** |
| `ndi-player-0.17.1.iso.sha256` | Verify ISO |
| `ndi-player-0.17.1.tar.gz` | OTA update (Device → Updates) |
| `ndi-player-0.17.1.tar.gz.sha256` | Verify OTA |
| `latest.json` + `latest.json.sig` | Signed update manifest |

```bash
sha256sum -c ndi-player-0.17.1.iso.sha256
sha256sum -c ndi-player-0.17.1.tar.gz.sha256
```

## ISO install

1. `sudo dd if=ndi-player-0.17.1.iso of=/dev/sdX bs=4M status=progress conv=fsync`
2. Boot from USB; unattended install completes automatically.
3. Press **SPACE** on a display to read the IP; open `https://<IP>`.
4. Activate license (**Device**), assign sources (**Displays**).

## OTA update

**Device → Updates → Check → Apply.** Reboot if prompted (kernel display fix).

## What is in 0.17.1

Playback is more reliable on mixed graphics hardware (single GPU and dual-GPU PCs) from the same image:

- Renderer chosen per GPU (OpenGL or OpenGL ES)
- Linear display gamma so the picture is not crushed to black
- NDI region-capture / scan-converter frame sizes (not 16-pixel aligned) upload correctly
- Last frame held instead of flashing black when a source is briefly late
- Loopback ignored for hostname collision checks
- Multi-GPU workers staggered; quiet boot; nouveau Mini-DP kernel fix where needed

See `docs/CHANGELOG-v0.17.1.md` in the source repo for the same summary.

## What you get

- Dedicated NDI player appliance (no desktop for operators).
- Multi-display routing, bandwidth, Auto/fixed output modes.
- Multi-GPU, Wi-Fi/Ethernet, health panel, remote support.

See the source repo `docs/SYSTEM.md` for full architecture and ISO vs OTA behavior.

Issues: https://github.com/zabelez/ndi-player-releases/issues
