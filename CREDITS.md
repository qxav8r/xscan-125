# Credits

## bc125at-tool — Costa Mesa Tech Solutions

xScan-125 would not exist without **bc125at-tool**, which does all of the
actual communication with the Uniden BC125AT over USB.

- Project: https://github.com/costamesatechsolutions/bc125at-tool
- Author: Pine Heights Ventures LLC, dba Costa Mesa Tech Solutions
  (https://costamesatechsolutions.com)
- License: GNU Affero General Public License v3.0 (AGPL-3.0)

**How xScan-125 uses it:** the stack runs bc125at-tool's command-line
interface as a separate program (`python3 -m bc125at info`, `channels`,
`import`) and shows the results. xScan-125 does not copy, modify or link
bc125at-tool's code.

**In this repo:** `bc125at-tool/` is a git submodule pointing at the
original repository, unmodified. Its own LICENSE and copyright notices
apply to everything in that folder. xScan-125's MIT license covers only
xScan-125's own files.

Thank you to the bc125at-tool developers for building and sharing it.

## Uniden BC125AT PC Protocol

`docs/reference/README.md` links to Uniden's BC125AT programming command
specification (Uniden's document, not copied here). Uniden and BC125AT are
trademarks of Uniden; this project is not affiliated with or endorsed by
Uniden.
