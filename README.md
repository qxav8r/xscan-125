# xScan-125

**Program a Uniden BC125AT scanner from your Mac** — an OpenXTalk / xTalk-family
stack (HyperXTalk, OpenXTalk, LiveCode) that puts a point-and-click front end on
[bc125at-tool](https://github.com/costamesatechsolutions/bc125at-tool).

> Status: prototype, private. Not ready for general use yet.

> **xScan-125 is a stack, not a standalone app.** You open it in a free xTalk
> development app (an "IDE") — see [Requirements](#requirements).

## What it does
| Button | |
|---|---|
| **Initialize** | Checks Homebrew, libusb, finds bc125at-tool and its Python environment, then talks to the scanner. The other scanner buttons stay off until every check passes. |
| **Scanner Info** | Model, firmware, what's on the display, current settings, which banks are on. |
| **Read Banks** | Saves every programmed channel to a CSV on the Desktop and opens a channel report in your browser — one table per bank, filter box, light/dark mode, prints cleanly. |
| **Export Channels** | Saves all programmed channels to a CSV file (your backup). |
| **Import Channels** | Writes a CSV file to the scanner. |
| **Settings** | Palette with the scanner's live settings (volume, squelch, contrast, backlight, priority, key beep, key lock, weather alert, band plan, battery timer). Apply sends only what changed and re-reads the scanner to confirm each one. |
| **Help** | Opens the help page in your browser. |
| Load Presets, Manage Banks | Coming soon. |

Editing channels: **Export → edit the CSV in Numbers or Excel → Import.**

## Requirements
- macOS (Apple Silicon or Intel)
- **An xTalk IDE to open the stack** — xScan-125 runs inside one of these, it is
  not a double-click app:
  - [HyperXTalk](https://github.com/emily-elizabeth/HyperXTalk) (free, open source,
    macOS 13+) — **recommended; xScan-125 is built and tested in HyperXTalk 0.9.15**
  - [OpenXTalk](https://www.openxtalk.org) or LiveCode — should work, not yet tested
- [Homebrew](https://brew.sh) and `libusb` (`brew install libusb`)
- [bc125at-tool](https://github.com/costamesatechsolutions/bc125at-tool),
  set up with its `./setup.sh`

## Quick start
1. Install [HyperXTalk](https://github.com/emily-elizabeth/HyperXTalk).
2. Install Homebrew, then `brew install libusb`.
3. Download bc125at-tool into your home folder and run `./setup.sh` in it.
4. Plug in the scanner (USB) and turn it on.
5. Open `xscan-125.v1.hyperxtalk` in HyperXTalk (File → Open Stack, or
   drag it onto the app) and click **Initialize**.

xScan-125 finds bc125at-tool on its own every time (home, Documents, Desktop,
Downloads, Documents/GitHub, next to the stack, then a Spotlight search) — no
setup inside the stack, and nothing machine-specific is saved in it.

## Repo layout
- `xscan-125.v1.hyperxtalk` — the stack
- `xscan-125_inventory.txt` — text export of every script in the stack
  (written by the stack's option-click inventory tool)
- `docs/help.html` — the Help page (the stack keeps a copy and opens it)
- `examples/` — a real 243-channel plan for Portland / Vancouver / the
  Columbia River, ready to load with Import Channels (see its README)
- `bc125at-tool/` — git submodule: the original
  [bc125at-tool](https://github.com/costamesatechsolutions/bc125at-tool),
  unmodified (AGPL-3.0). Clone with `git clone --recurse-submodules`.
- `web/webusb-probe.html` — experiment: can a browser talk to the scanner
  directly over WebUSB? (Chrome/Edge desktop, read-only)
- `docs/reference/` — link to Uniden's BC125AT PC programming protocol, and
  the commands xScan-125's buttons rely on
- `docs/history/` — earlier WebUSB / serial experiments (March 2026)

## Credits
Scanner communication is handled entirely by
**[bc125at-tool](https://github.com/costamesatechsolutions/bc125at-tool)**
by Costa Mesa Tech Solutions (AGPL-3.0). xScan-125 runs it as a separate
program and includes it only as an unmodified submodule. See
[CREDITS.md](CREDITS.md).

Uniden and BC125AT are trademarks of Uniden. This project is not affiliated
with Uniden.

## License
MIT — see [LICENSE](LICENSE). Copyright (c) 2026 QXAV8R.
