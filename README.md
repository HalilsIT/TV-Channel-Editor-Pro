# TV Channel Editor Pro

Offline, single-file, browser-based TV channel list editor for selected Sony, Samsung, LG, TCL/Thomson and Vestel channel-list formats.

**Current release candidate:** `v7.9.0.5-rc6`

**Development branch:** `v7-dev`

**License:** GNU GPL v3

The project is currently in **feature freeze / stabilization**. Hisense and Philips are intentionally not advertised as supported until real sample exports become available for round-trip validation.

## What this project is

TV Channel Editor Pro is an independently developed HalilsIT browser application. Its UI, interaction model, workflow, filtering, ordering, wide multi-column editor, Undo/Redo behavior, reversible-remove model, browser-only/offline architecture, generic channel model, adapter abstraction and integration logic are original project work.

Selected TV-format parsing, serialization, binary-layout, mapping and checksum logic is derived in part from **ChanSort by PredatH0r and contributors** where explicitly identified in the source. ChanSort is licensed under GNU GPL v3, and TV Channel Editor Pro is also distributed under GNU GPL v3.

The project does **not** port ChanSort's Windows/DevExpress UI.

## Screenshots

### Demo / OLED Theme

![TV Channel Editor Pro - Demo OLED Theme](demo-oled.png)

### Sony Bravia — Real SDB File

Real Sony `sdb.xml` support has been validated on actual TV hardware.

![TV Channel Editor Pro - Sony Bravia](sony-bravia.png)

### Samsung Legacy SCM

Samsung Legacy SCM has software-level parser/export/checksum validation. Real Samsung TV import validation is still pending.

![TV Channel Editor Pro - Samsung SCM](samsung-scm.png)

English interface example:

![TV Channel Editor Pro - Samsung SCM English](samsung-scm-ENG.png)

## Current Support

| Brand / family | File / format | Status | Implementation origin |
|---|---|---|---|
| Sony Bravia | `sdb.xml` | **Real-TV validated** | Predominantly original HalilsIT reverse-engineering / implementation |
| Samsung Legacy | `.scm` / `map-SateD` 144/168/172B | **Software tested** | Original 168B work, later expanded/verified with ChanSort format knowledge |
| LG webOS | `GlobalClone*.TLL` | **Experimental** | Predominantly original HalilsIT sample analysis / implementation |
| LG Legacy / NetCast | binary `xx*.TLL` | **Software tested** | Hybrid: ChanSort-derived container/layout/CRC logic plus original sample-specific 84B profile analysis |
| TCL / Thomson | `.tar` with `DtvData.db` + `cloneCRC.bin` | **Software round-trip tested** | ChanSort-derived format/schema/CRC knowledge with original browser SQLite/TAR implementation |
| Vestel | `.sdx` / `SATCODX` | **Experimental** | Predominantly original HalilsIT sample analysis / implementation |
| Hisense | — | Not actively supported | Real export sample required |
| Philips | — | Not actively supported | Real export sample required |

Support does not guarantee every TV model from the same brand. Channel-list formats can differ by model, generation and firmware.

## Features

- Channel search and filtering
- TV / Radio filtering
- Uydu / Kablo / Karasal source filtering
- Listede / Gizli status filtering
- Add-to-end / add-to-start mode
- Drag-and-drop channel ordering
- Bulk add and reversible remove
- Manual channel numbering
- Multi-column wide editing mode
- Undo / redo
- Turkish and English interface
- Multiple themes
- Automatic TV format detection through modular adapters
- In-app supported-format information panel
- Fully offline channel-list processing
- No cookies and no cloud upload for channel-list processing

The demo data intentionally includes one source-only hidden channel so the `Gizli` workflow can be seen without loading a TV file.

## Format Notes

### Sony Bravia

`SDB / sdb.xml`

Status: **Real-TV validated.** This is the most mature adapter and remains native rather than being replaced by ChanSort logic.

### Samsung Legacy

`.scm / map-SateD`

Supported legacy satellite record profiles:

- 144 bytes — B/C generations
- 172 bytes — D generation
- 168 bytes — E/F/H and some J generations

Status: **Software tested.** The first 168-byte implementation was developed from the project's own real sample; v7 later used ChanSort mappings to verify and expand the family to 144/168/172-byte profiles.

### LG webOS

`GlobalClone*.TLL`

Status: **Experimental.** Developed primarily from real sample inspection of the XML + embedded `legacybroadcast` JSON structure.

### LG Legacy / NetCast

Binary `xx*.TLL`

Status: **Software tested.** The v7 engine uses ChanSort-derived DVB-S container, linked-list and CRC concepts, while the exact real `xxMT47U-PZS00001.TLL` 687532-byte DVB-S / 84-byte channel-record profile was derived through project-specific byte-level analysis because that exact profile was not present in the inspected ChanSort LG profile data.

### TCL / Thomson

`.tar` typically containing:

- `database/userdata/DtvData.db`
- `database/userdata/satellite.db` when present
- `database/cloneCRC.bin`

Status: **Software round-trip tested with a real sample.** The adapter uses ChanSort-derived TCL schema/edit-flag/CRC knowledge, while the browser-side TAR handling and focused SQLite b-tree reader/patcher are implemented specifically for TV Channel Editor Pro. SQLite integrity and CRC16-CCITT checks passed after edits.

### Vestel

`.sdx / SATCODX`

Status: **Experimental.** Current adapter originates from project sample analysis. ChanSort SatcoDX may remain a reference, but the current implementation is not presented as a ChanSort port.

## Deferred Formats

### Hisense

No active support is advertised until a real TV export sample is available.

### Philips

No active support is advertised until a real TV export sample is available.

No additional brand families are currently planned for this development cycle.

## Architecture

The core browser UI uses a brand-independent channel model and modular TV format adapters. Native/original implementations are preserved where they are already useful or validated; selected format-engine knowledge may be adapted from compatible GPLv3 projects where explicitly credited.

`Kaldır` is intentionally treated as a reversible operation. Adapters retain enough source-record information for a removed channel to remain discoverable and re-addable whenever the underlying TV format allows it.

See [`docs/CHANSORT_SUPPORT_MATRIX.md`](docs/CHANSORT_SUPPORT_MATRIX.md) for the current ChanSort relationship/support matrix.

## Acknowledgements

Selected format-engine portions are derived in part from **ChanSort by PredatH0r and contributors**:

https://github.com/PredatH0r/ChanSort

Only specifically identified portions are ChanSort-derived. TV Channel Editor Pro's UI, workflow, browser architecture and original format work remain project work by HalilsIT.

See [`CREDITS.md`](CREDITS.md) for detailed attribution.

## Privacy

TV channel-list files are processed locally in the browser.

No channel-list data is uploaded to a server. No cookies or persistent browser storage are required for channel-list processing.

## Contact

halilsit@outlook.com

## Support

The project is provided freely under GPLv3. If it is useful to you, voluntary support is available through GitHub Sponsors:

https://github.com/sponsors/HalilsIT

## License

This project is licensed under the **GNU General Public License v3.0**.

Redistribution and modification are permitted under the GPL terms. Applicable copyright, license and third-party attribution notices must be preserved, and corresponding source must be provided where required by GPLv3.

Copyright © 2026 HalilsIT
