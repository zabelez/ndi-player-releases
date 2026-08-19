# NDI Player

Turn an ordinary PC into a dedicated [NDI](https://ndi.video/) video player.

Power it on. It finds sources on your network. Every screen in the room comes alive — no desktop, no login, no window to drag into place. A browser is the only remote you need.

NDI Player is built for control rooms, classrooms, houses of worship, studios, and any space that should show live video the moment the lights go on. One machine. One display or many. HDMI, DisplayPort, or a laptop panel. The same installer.

This project is **in active development**. We are installing it on all kinds of computers — old laptops, gaming PCs, machines with one graphics card and machines with two. Every new box teaches us something. **If you try it and it does not work on your hardware, please tell us.** Open an [issue](https://github.com/zabelez/ndi-player-releases/issues) with what you used and what you saw. We want NDI Player to be useful for everyone, not just the machines on our bench.

## What you can do today

- **Boot straight into playback.** No desktop for operators. Connect a monitor, connect the network, and go.
- **Put a different NDI source on every screen.** Each output gets its own source, resolution, frame rate, and bandwidth.
- **Switch cleanly.** Optionally prepare the next source before it hits the display.
- **See what is on the wire.** Format, frame rate, encoder, and bitrate stay visible; offline sources remain in the list.
- **Fit the room’s network.** Ethernet or Wi-Fi, DHCP or a fixed address, `.local` hostname, NDI groups, discovery across subnets.
- **Keep an eye on the box.** CPU, memory, graphics, disk, temperature, and battery in one health view.
- **Activate a device in seconds.** Each player has its own identity; license from **Device → License**.
- **Update without reinstalling.** New versions land from **Device → Updates** on machines that are already in the field.
- **Get help when you need it.** Start a time-limited remote support session from the UI with a one-time code.
- **Drive every connected display.** Built-in panels and external monitors are first-class outputs.

Open the UI at `https://<player-ip>` or `https://<hostname>.local`. On first boot the screens start black — press **SPACE** on a display to read the address.

Current application: **[v0.17.2](https://github.com/zabelez/ndi-player-releases/releases/tag/v0.17.2)** (signed in-place update). Fresh-install ISO is still **[v0.17.1](https://github.com/zabelez/ndi-player-releases/releases/tag/v0.17.1)** until the next image.

## Help us make it yours

We are not done. Hardware is wonderfully messy: different screens, different GPUs, different NDI sources. That is exactly why your test matters.

Tried it on a PC we have never seen? **It worked? Celebrate with us in an issue. It failed? Even better — tell us**, so the next build can love that machine too. The goal is simple: anyone should be able to take a spare computer, flash this image, and have a rock-solid NDI player.

## New machine — install from ISO

1. Download **`ndi-player-0.17.1.iso`** and **`ndi-player-0.17.1.iso.sha256`** from [Releases](https://github.com/zabelez/ndi-player-releases/releases/latest).
2. Verify: `sha256sum -c ndi-player-0.17.1.iso.sha256`
3. Write the image to USB. **This erases the target computer’s internal disk.**

   ```bash
   sudo dd if=ndi-player-0.17.1.iso of=/dev/sdX bs=4M status=progress conv=fsync
   ```

4. Boot from USB and let the unattended install finish.
5. Connect network and a monitor. Press **SPACE** for the IP.
6. Open `https://<IP>` (self-signed certificate on the first visit).
7. **Device → License** — paste your token and Activate.
8. **Displays** — pick a source for each screen.

One ISO for every PC we support. After install, each unit keeps its own name, identity, license, and which source goes where.

## Already installed — update in place

1. Open **Device → Updates**.
2. **Check for updates**, then **Apply**.
3. Reboot if the UI asks you to.

Your configuration, license, and certificates stay put.

## Downloads

| File | Purpose |
|------|---------|
| `ndi-player-0.17.1.iso` | Fresh install. **Erases the target disk.** (latest ISO) |
| `ndi-player-0.17.1.iso.sha256` | Verify the ISO |
| `ndi-player-0.17.2.tar.gz` | In-place update (Device → Updates) |
| `ndi-player-0.17.2.tar.gz.sha256` | Verify the update |
| `latest.json` + `latest.json.sig` | Signed update manifest |

```bash
sha256sum -c ndi-player-0.17.1.iso.sha256
sha256sum -c ndi-player-0.17.2.tar.gz.sha256
```

After a 0.17.1 ISO install, open **Device → Updates** to apply 0.17.2.

## Talk to us

Questions, ideas, a PC that surprised you — [open an issue](https://github.com/zabelez/ndi-player-releases/issues). We read them. This only becomes the player everyone can trust if we hear from the rooms it actually lives in.
