# xScan-125 — to do

Planned work, roughly in priority order. Ideas and feedback welcome via Issues.

## Features
- [ ] **Manage Banks** — palette with checkboxes for banks 1–9 and 0 to turn
      them on or off for scanning (bc125at-tool `banks --enable / --disable`).
- [ ] **Load Presets** — load one of bc125at-tool's built-in presets (marine,
      NOAA weather, railroad, aviation, FRS/GMRS, MURS, racing) into a bank you
      pick. Shows what will be overwritten and exports a backup first.
- [ ] **Browser bank / frequency editor** — an editable version of the Read
      Banks channel report: edit channels bank by bank in the browser, save a
      CSV, load it with Import Channels.

## Website and docs
- [ ] **Web page** on qxav8r.github.io (Floggy-Go style) with a Download button
      for the latest release.
- [ ] **Screenshots** in the README — main window and the Settings palette.
- [ ] Test on an **Intel Mac** — bc125at-tool is only tested on Apple Silicon.
      Check that macOS's own serial driver doesn't grab the scanner first
      (`info` should answer). Report the result to bc125at-tool's developers.
- [ ] Test the stack in **OpenXTalk** and **LiveCode** (built and tested in
      HyperXTalk 0.9.15 so far).

## Getting the word out
- [ ] Add xScan-125 to the RadioReference BC125AT wiki ("Supporting Software").
- [ ] Post in the RadioReference BC125AT forum.
- [ ] Let the bc125at-tool developers know about this Mac front end.

## Done (v0.1)
- [x] Initialize: setup checks, auto-find bc125at-tool, buttons locked until ready
- [x] Scanner Info, Read Banks (CSV + browser report), Export / Import Channels
- [x] Settings palette with read-back check
- [x] Help page, native macOS buttons
