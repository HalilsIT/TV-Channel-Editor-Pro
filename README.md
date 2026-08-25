# TV Channel Editor Pro

Offline universal TV channel list editor for Sony, Samsung, LG, TCL/Thomson, Vestel and compatible channel-list formats.

**Current release candidate:** `v7.9.0.0-rc1`

**Development branch:** `v7-dev`

The v7 line keeps the HalilsIT browser interface and uses selected TV-format parsing, serialization, layout and checksum knowledge derived from ChanSort where appropriate.

The project is currently in **feature freeze / stabilization**. Hisense and Philips are intentionally not advertised as supported until real sample exports are available for round-trip validation.

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

## Current Status

- Sony Bravia `sdb.xml`: **real-TV validated**
- Samsung Legacy `.scm` / `map-SateD` 144/168/172-byte profiles: **software tested**
- LG webOS `GlobalClone*.TLL`: **experimental**
- LG Legacy / NetCast binary `xx*.TLL`: **software-tested v7 ChanSort-derived pilot**
- TCL / Thomson `.tar` with `DtvData.db` + `cloneCRC.bin`: **software round-trip tested with a real sample**
- Vestel `.sdx` / `SATCODX`: **experimental**
- Hisense: **not actively supported — real sample required**
- Philips: **not actively supported — real sample required**
- Fully offline browser application
- No cookies, no cloud processing, no external upload

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

## Supported Formats

### Sony Bravia

`sdb.xml`

Status: **Real-TV validated.**

### Samsung Legacy

`.scm` / `map-SateD`

Supported legacy satellite record profiles:

- 144 bytes — B/C generations
- 172 bytes — D generation
- 168 bytes — E/F/H and some J generations

Status: **Software tested.** Real-TV validation pending.

### LG webOS

`GlobalClone*.TLL`

Status: **Experimental.**

### LG Legacy / NetCast

Binary `xx*.TLL`

Status: **Software-tested ChanSort-derived v7 pilot.** The pilot profile is based on the real `xxMT47U-PZS00001.TLL` sample and follows the DVB-S block structure, linked channel list and CRC32 rules rather than heuristic record scanning.

### TCL / Thomson

`.tar` containing TCL channel database files, typically:

- `database/userdata/DtvData.db`
- `database/userdata/satellite.db` (when present)
- `database/cloneCRC.bin`

Status: **Software round-trip tested with a real sample.** SQLite integrity and CRC16-CCITT validation passed. Real-TV import validation pending.

### Vestel

`.sdx` / `SATCODX`

Status: **Experimental.**

## Deferred Formats

### Hisense

No active support is advertised until a real TV export sample is available.

### Philips

No active support is advertised until a real TV export sample is available.

## v7 Architecture

The core browser UI uses a brand-independent channel model and modular TV format adapters. Native, already validated implementations are preserved where appropriate, while selected format-specific logic can be adapted from ChanSort under GPLv3.

The UI deliberately does not expose every low-level TV flag. `Kaldır` is treated as a reversible operation: adapters retain enough source-record information for a removed channel to be found and re-added later whenever the underlying format allows it.

See [`docs/CHANSORT_SUPPORT_MATRIX.md`](docs/CHANSORT_SUPPORT_MATRIX.md) for the ChanSort loader inventory and port notes.

## Acknowledgements

Selected TV channel-list format implementations in the v7 line are derived in part from or based on format knowledge from **ChanSort by PredatH0r and contributors**.

ChanSort: https://github.com/PredatH0r/ChanSort

ChanSort is licensed under GNU GPL v3. TV Channel Editor Pro is also licensed under GNU GPL v3.

The ChanSort Windows/DevExpress user interface is not ported. TV Channel Editor Pro keeps its own HalilsIT browser interface and workflow; only useful format-specific parsing, serialization, mapping, layout and checksum logic is adapted where needed.

See [`CREDITS.md`](CREDITS.md) for detailed attribution.

## Privacy

TV channel list files are processed locally in the browser.

No channel-list data is uploaded to a server. No cookies or browser storage are required for channel-list processing.

## Contact

halilsit@outlook.com

## Support

If this project is useful to you, you can support its development through GitHub Sponsors:

https://github.com/sponsors/HalilsIT

## License

This project is licensed under the GNU General Public License v3.0.

Copyright © 2026 HalilsIT
