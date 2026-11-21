# To-Do: Connect Bearcat BC125AT to LiveCode

**Goal:** Talk to the Uniden BC125AT scanner from LiveCode.

**Skip WebUSB / browser widget** — LiveCode's browser widget runs on CEF, which lacks
the device-picker UI `navigator.usb.requestDevice()` needs. No known working examples.

**Use native serial instead** — no extra LiveCode driver required:
- `open driver "COM3:" for read write` (Windows) or `/dev/tty.usbmodemXXXX` (Mac)
- `read from driver`, `write to driver`, `close driver`
- `serialControlString` to set baud (default 9600, 8N1, no flow control)

**Step 1 — check if OS already sees it as a COM/serial device:**
- Windows: Device Manager → Ports (COM & LPT)
- Mac: `ls /dev/tty.*` before/after plugging in
- Linux: `dmesg | tail` after plugging in (look for ttyACM/ttyUSB)

**Step 2 — protocol commands to try (ASCII, CR-terminated):**
- `PRG` / `EPG` — enter/exit program mode
- `MDL` — get model
- `VER` — get firmware version
- `VOL,[0-15]` / `SQL,[0-15]` — volume / squelch
- `GLG` — real-time status (freq, channel, squelch) — unofficial but widely used
- `CIN,[index]` — read/write channel memory
- `LOF` / `ULF` — lockout management

**References:**
- Official protocol PDF: https://info.uniden.com/twiki/pub/UnidenMan4/BC125AT/BC125AT_PC_Protocol_V1.01.pdf
- Python example (GLG usage): https://github.com/pa3ang/ubc125xlt
- Channel/CSV tooling: https://github.com/fdev/bc125csv
