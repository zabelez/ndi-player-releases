# NDI Player

Turn an ordinary PC into a dedicated [NDI](https://ndi.video/) video player.

Power it on. It finds sources on your network. Every screen in the room comes alive — no desktop, no login, no window to drag into place. A browser is the only remote you need.

NDI Player is built for control rooms, classrooms, houses of worship, studios, and any space that should show live video the moment the lights go on. One machine. One display or many. HDMI, DisplayPort, or a laptop panel. The same installer.

This project is **in active development**. **If you try it and it does not work on your hardware, please tell us.** Open an [issue](https://github.com/zabelez/ndi-player-releases/issues) with what you used and what you saw.

**0.22.0 must be installed from the USB image.** Do not use **Device → Updates** from the previous version: that in-place update does not apply 0.22.0 correctly. After this USB install, later versions can use **Device → Updates** as usual.

## What you can do today

- **Boot straight into playback.** No desktop for operators.
- **Put a different NDI source on every screen.**
- **Switch cleanly.** Optionally prepare the next source before it hits the display.
- **Fit the room’s network.** Ethernet or Wi-Fi, DHCP or a fixed address, NDI groups, Discovery Server.
- **Activate a device in seconds.** License from **Device → License**. Email **contact@sysontech.com** with the Device UUID.
- **Lock the UI.** First visit sets an operator password. Scripts use **API → API token**.
- **Backup per screen.** A still image, a looping video, or another NDI source if the main source drops.
- **Get help.** Time-limited remote support from the UI.

Open the UI at `https://<player-ip>` or `https://<hostname>.local`. On first boot the screens start black — press **SPACE** on a display to read the address.

Current version: **0.22.0**.

## New machine — USB image (Try or Install)

1. Download **`ndi-player-0.22.0.iso`** and **`ndi-player-0.22.0.iso.sha256`** from [Releases](https://github.com/zabelez/ndi-player-releases/releases/tag/v0.22.0).
2. Verify the download:

   ```bash
   # Linux
   sha256sum -c ndi-player-0.22.0.iso.sha256

   # macOS
   shasum -a 256 -c ndi-player-0.22.0.iso.sha256
   ```

3. Write the image to a USB stick (Balena Etcher; Rufus **DD Image** on Windows).
4. Boot from USB. A 15-second menu appears. **Try NDI Player** (the default) does not change the internal disk. **Install NDI Player** erases it. If you do nothing, Try starts.
5. Connect network and a monitor. Press **SPACE** for the IP.
6. Open `https://<IP>`, set the operator password, then **Device → License**.
7. **Displays** — pick a source for each screen.

**Try is for evaluation, not for a show.** Playback is slower and less stable than after Install: Try runs from the USB stick and a temporary copy in memory, which is much slower than the computer’s internal disk. After Install, the player lives on that disk — that is the performance this product is built for. Nothing from Try is saved.

## Already installed — 0.22.0 requires a USB install

Do not use **Device → Updates** to reach 0.22.0 from a previous version. Write the 0.22.0 ISO, boot from USB, and choose **Install NDI Player**. Installing erases the internal disk. After 0.22.0 is on the machine, later versions can apply from **Device → Updates**.

## Downloads

| File | Purpose |
|------|---------|
| `ndi-player-0.22.0.iso` | Try or Install. **Install erases the target disk.** |
| `ndi-player-0.22.0.iso.sha256` | Verify the image |
| `ndi-player-0.22.0.tar.gz` | Linux update package (after a 0.22.0 install) |
| `ndi-player-0.22.0.tar.gz.sha256` | Verify the update package |

## Talk to us

Questions, ideas, a PC that surprised you — [open an issue](https://github.com/zabelez/ndi-player-releases/issues).
