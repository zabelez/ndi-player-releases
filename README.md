# NDI Player

Turn ordinary PCs into dedicated [NDI](https://ndi.video/) video players — boot, discover, and put a live source on every screen, with no desktop in the way.

This repository publishes **installers only**. Use it to download a build, try the appliance, and tell us what to build next.

## Why it exists

PCs running generic playback software waste time: logins, windows, wrong resolutions, a source that blinks when you switch. NDI Player is built to do one job well — receive NDI and drive HDMI/DisplayPort as if the decoder were a piece of AV gear.

Control rooms, classrooms, houses of worship, huddle rooms: if the picture should be there when power comes on, this is the player.

## What you get

- **A screen for every source.** Route a different NDI stream to each monitor, with its own resolution and frame rate.
- **Clean switches.** Optional preload prepares the next source before it hits the display, so the current picture stays up until the new one is ready.
- **Live source intelligence.** See format, frame rate, encoder, and bitrate. Sources you already used stay available even if they drop off the network for a moment.
- **Network that fits the room.** Ethernet or Wi-Fi, DHCP or a fixed address, a unique name on the LAN (`https://your-player.local`), NDI groups, and discovery across subnets.
- **Health at a glance.** CPU, memory, GPU, disk, temperature, and battery when the hardware has one.
- **Device identity and license.** Each player has a UUID. Activate it in the Device tab and you are in production.
- **Help when you need it.** Start a time-limited remote support session from the UI with a one-time code.

Open the UI at `https://<player-ip>` (or the `.local` name). After first boot, press **SPACE** on a connected display to read the address on screen.

## Get started

1. Download the latest ISO and its `.sha256` from [Releases](https://github.com/zabelez/ndi-player-releases/releases/latest).
2. Confirm the file:

   ```bash
   sha256sum -c ndi-player-*.iso.sha256
   ```

3. Write it to a USB stick. **Installing erases the target computer’s internal disk.**

   ```bash
   sudo dd if=ndi-player-….iso of=/dev/sdX bs=4M status=progress conv=fsync
   ```

   On a Mac, use the `mac-usb` ISO from the same release, or `dd` to `/dev/rdiskN`.

4. Boot the target PC from USB and let the unattended install finish.
5. Connect a network cable and a monitor. Displays start black — press **SPACE** to show the IP.
6. From another computer, open `https://<IP>` (you will see a self-signed certificate once).
7. In **Device → License**, paste the token for this player and Activate.
8. In **Displays**, pick a source for each monitor and apply.

That is the whole path from USB to a live wall.

## Shape what we build next

If you install NDI Player, we want the idea you had in the room:

- A workflow we do not cover yet
- A display, GPU, or NDI encoder that misbehaves
- A control that should exist in the UI
- An integration (control systems, signage, audio, tally, scheduling)

[Open an issue](https://github.com/zabelez/ndi-player-releases/issues) with the idea or the setup. Short notes are enough. The best features started as “what if we could…” from people who had a screen to fill.
