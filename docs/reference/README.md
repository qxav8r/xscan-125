# Reference

## Uniden BC125AT PC Protocol

Uniden's official PC programming command specification for the BC125AT:

**https://info.uniden.com/twiki/pub/UnidenMan4/BC125AT/BC125AT_PC_Protocol_V1.01.pdf**

(Uniden's document — linked here rather than copied.)

xScan-125 doesn't send these commands itself; bc125at-tool does. The ones
behind xScan-125's buttons:

| Command | Used for |
|---|---|
| `PRG` / `EPG` | Enter / exit program mode |
| `MDL`, `VER`, `STS` | Model, firmware, display status (Initialize, Scanner Info) |
| `CIN` | Read / write channel memory (Read Banks, Export, Import) |
| `BLT`, `BSV`, `BPL`, `KBP`, `PRI`, `CNT`, `WXS`, `VOL`, `SQL` | Settings palette |

Notes:
- Every command waits for the scanner's reply before the next one.
- Memory and most settings commands only work in program mode.
- `WXS` (weather alert priority): the scanner answers OK but turns it back
  off by itself when it can't hear a NOAA weather station.
