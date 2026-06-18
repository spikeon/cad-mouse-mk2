# CAD Mouse MK2 — Linux Fork

> ### 🚀 There's a newer, better version: **[linapse-cad-mouse-v2](https://github.com/spikeon/linapse-cad-mouse-v2)**
>
> This fork still works, but active development has moved to **Linapse** — a complete, polished Linux software stack for the CAD Mouse MK2. If you want the best experience, start there. It adds:
>
> - **A web configurator (GUI).** Remap buttons, taps, and chords; design RGB lighting; and tune the motion filter — all in the browser, applied to the device live. No editing scripts by hand.
> - **Cap-tap gestures.** Tap the puck top/left/right/front/back (single, double, triple) and bind each to keys, clicks, scrolls, commands, or macros.
> - **A live 3D test viewport.** Push a 3D Benchy around with the puck to feel sensitivity changes in real time while you tune.
> - **Richer firmware.** Kalman-filtered motion, a sensitivity curve, an SK6812 LED effect engine (breathing, motion-reactive, swirls, rainbow), and serial telemetry.
> - **A cleaner architecture.** One `linapse-service` bridges serial ↔ WebSocket for buttons, taps, lighting, and config.
>
> 👉 **[Check out linapse-cad-mouse-v2 →](https://github.com/spikeon/linapse-cad-mouse-v2)**

---

This is a fork of [sb-ocr/cad-mouse-mk2](https://github.com/sb-ocr/cad-mouse-mk2) with changes to make the device work on Linux with OnShape.

## What's different

**Firmware**
- Sleep timeout disabled

**`linux/` directory** — full Linux integration, not in the original repo:
- One-command installer (`install.sh`)
- `spacenavd` + `spacenav-ws` WebSocket bridge for OnShape
- Tampermonkey userscript so OnShape connects to the local bridge
- Button mapper (`spnav-buttons`): scroll up/down while held, both buttons = Shift+7
- udev rules with delayed restarts to avoid race conditions on plug-in
- `spacemouse-status` health check script
- Patches to `spacenav-ws` that disable the button-snap-to-front-view behaviour and add automatic reconnection to `spacenavd` (no OnShape tab refresh needed after replug)

## Linux setup

See [linux/README.md](linux/README.md).

## Original project

Hardware design, build instructions, BOM, and enclosure files are from the original project:

**[sb-ocr/cad-mouse-mk2](https://github.com/sb-ocr/cad-mouse-mk2)**

Build instructions → [Instructables](https://www.instructables.com/CAD-Mouse-MK2-a-6DoF-Space-Mouse-Using-Magnets)

[![CC BY-NC-SA 4.0][cc-by-nc-sa-shield]][cc-by-nc-sa]

[cc-by-nc-sa]: http://creativecommons.org/licenses/by-nc-sa/4.0/
[cc-by-nc-sa-shield]: https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg
