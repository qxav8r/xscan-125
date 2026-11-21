# Example channel plan — Portland / Vancouver / Columbia River

`pdx-columbia-river-2026-11.csv` is a real working plan read straight off a
BC125AT on 11/21/2026 with **Read Banks** / **Export Channels**: 243 programmed
channels in all 10 banks, for the Portland OR / Vancouver WA area and the
Columbia River.

| Bank | Channels | Contents |
|---|---|---|
| 1 | 1–26 | PDX ATC (ATIS, clearance, ground, tower, approach/departure), airline ops, ZSE Seattle Center sectors |
| 2 | 51–71 | Marine VHF + Columbia River port operations |
| 3 | 101–140 | CB, all 40 channels |
| 4 | 151–155 | Fire / search & rescue (non-trunked) |
| 5 | 201–212 | Clark Co. Sheriff, WSP, OSP (conventional analog) |
| 6 | 251–257 | NOAA Weather Radio, all 7 |
| 7 | 301–337 | Pacific Northwest railroad (BNSF, UP, PTRC, Amtrak, WES, detectors) |
| 8 | 351–400 | AAR channel plan Ch 07–56 |
| 9 | 401–441 | AAR channel plan Ch 57–97 |
| 0 | 451–454 | Misc / unverified |

Priority is set on PDX App Final, Marine Ch 16 and CB Ch 9.

## Loading it
- **xScan-125:** click **Import Channels** and pick the CSV.
- **Terminal (bc125at-tool):** `python -m bc125at import pdx-columbia-river-2026-11.csv`

**Import overwrites** the channel numbers in the file. Run **Export Channels**
first so you have a backup of what's on your scanner.

## Notes
- The file is bc125at-tool's own CSV format:
  `channel, name, frequency, modulation, tone, tone_code, delay, lockout, priority, bank`.
  Edit it in Numbers or Excel, save as CSV, then Import.
- Names stop at 16 characters — that's the scanner's limit.
- The BC125AT is analog only: P25/DMR trunked systems (most Portland/Clark
  County police and fire dispatch) can't be received, so they aren't here.
- Frequencies change. Check local listings (e.g. RadioReference) before you
  rely on any of them. Entries marked "unk" / "Unknown" are unverified.
