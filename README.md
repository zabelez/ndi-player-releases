# NDI Player

Turn an ordinary PC into a dedicated [NDI](https://ndi.video/) video player.

Power it on. It finds sources on your network. Every screen in the room comes alive — no desktop, no login, no window to drag into place. A browser is the only remote you need.

NDI Player is built for control rooms, classrooms, houses of worship, studios, and any space that should show live video the moment the lights go on. One machine. One display or many. HDMI, DisplayPort, or a laptop panel. The same installer.

This project is **in active development**. We are installing it on all kinds of computers — old laptops, gaming PCs, machines with one graphics card and machines with two. Every new box teaches us something. **If you try it and it does not work on your hardware, please tell us.** Open an [issue](https://github.com/zabelez/ndi-player-releases/issues) with what you used and what you saw. We want NDI Player to be useful for everyone, not just the machines on our bench.

## What you can do today

- **Boot straight into playback.** No desktop for operators. Connect a monitor, connect the network, and go.
- **Put a different NDI source on every screen.** Each output gets its own source, resolution, frame rate, and bandwidth.
- **Switch cleanly.** Optionally prepare the next source before it hits the display.
- **See what is on the wire.** Format, frame rate, and bitrate stay visible; offline sources remain in the list.
- **Fit the room’s network.** Ethernet or Wi-Fi, DHCP or a fixed address, NDI groups, and an NDI Discovery Server when automatic discovery cannot run.
- **Keep an eye on the box.** CPU, memory, graphics, disk, temperature, and battery in one health view.
- **Activate a device in seconds.** License from **Device → License**. Email **contact@sysontech.com** with the Device UUID for a test license.
- **Update without reinstalling.** New versions land from **Device → Updates** on machines that are already in the field.
- **Get help when you need it.** Start a time-limited remote support session from the UI with a one-time code.
- **Drive every connected display.** Built-in panels and external monitors are first-class outputs.

Open the UI at `https://<player-ip>` or `https://<hostname>.local`. On first boot the screens start black — press **SPACE** on a display to read the address.

Current version: **0.18.1** in-place update (Device → Updates). New USB installs still use the **[0.18.0 image](https://github.com/zabelez/ndi-player-releases/releases/tag/v0.18.0)**, then apply 0.18.1.

## Help us make it yours

We are not done. Hardware is wonderfully messy: different screens, different GPUs, different NDI sources. That is exactly why your test matters.

Tried it on a PC we have never seen? **It worked? Celebrate with us in an issue. It failed? Even better — tell us**, so the next build can love that machine too. The goal is simple: anyone should be able to take a spare computer, flash this image, and have a rock-solid NDI player.

## New machine — install from ISO

1. Download **`ndi-player-0.18.0.iso`** and **`ndi-player-0.18.0.iso.sha256`** from [Releases](https://github.com/zabelez/ndi-player-releases/releases/latest).
2. Verify the download:

   ```bash
   # Linux
   sha256sum -c ndi-player-0.18.0.iso.sha256

   # macOS
   shasum -a 256 -c ndi-player-0.18.0.iso.sha256
   ```

3. Write the image to a USB stick. **Installing erases the target computer’s internal disk.** The same file works from Linux, macOS, and Windows.

   **macOS or Windows** — flash with [Balena Etcher](https://etcher.balena.io/): select the ISO, select the USB stick, Flash. That is the path that works on a Mac. Rufus also works on Windows (use **DD Image** mode).

   **Linux** — replace `sdX` with the USB device from `lsblk` (the whole disk, not a partition like `sdX1`):

   ```bash
   sudo dd if=ndi-player-0.18.0.iso of=/dev/sdX bs=4M status=progress conv=fsync
   ```

   The Linux `dd` line does **not** work on macOS. If you prefer Terminal on a Mac:

   ```bash
   diskutil list
   diskutil unmountDisk /dev/diskN
   sudo dd if=ndi-player-0.18.0.iso of=/dev/rdiskN bs=4m
   ```

   Replace `N` with the USB disk number. Write to `/dev/rdiskN`, not `/dev/diskN`.

4. Boot from USB and let the install finish. At the end, **remove the USB stick** when asked, then continue so the machine starts the player — not the installer again.
5. Connect network and a monitor. Press **SPACE** for the IP.
6. Open `https://<IP>` (accept the certificate warning on the first visit).
7. **Device → License** — email **contact@sysontech.com** with the Device UUID, paste the token you receive, Activate.
8. **Displays** — pick a source for each screen.

One image for every PC we support. After install, each unit keeps its own name, license, and which source goes where.

## Already installed — update in place

1. Open **Device → Updates**.
2. **Check for updates**, then **Apply**.
3. Reboot if the UI asks you to.

Your settings and license stay put.

## Downloads

| File | Purpose |
|------|---------|
| `ndi-player-0.18.0.iso` | Fresh install. **Erases the target disk.** |
| `ndi-player-0.18.0.iso.sha256` | Verify the image |
| `ndi-player-0.18.1.tar.gz` | In-place update (Device → Updates) |
| `ndi-player-0.18.1.tar.gz.sha256` | Verify the update |

```bash
# Linux
sha256sum -c ndi-player-0.18.0.iso.sha256
sha256sum -c ndi-player-0.18.1.tar.gz.sha256

# macOS
shasum -a 256 -c ndi-player-0.18.0.iso.sha256
shasum -a 256 -c ndi-player-0.18.1.tar.gz.sha256
```

Players installed from an older image can stay on that disk: open **Device → Updates** and apply 0.18.1.

## Talk to us

Questions, ideas, a PC that surprised you — [open an issue](https://github.com/zabelez/ndi-player-releases/issues). We read them. This only becomes the player everyone can trust if we hear from the rooms it actually lives in.
