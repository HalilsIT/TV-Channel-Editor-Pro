# TV Channel Editor Pro

Offline universal TV channel list editor for Sony, Samsung, LG and additional TV platforms.

**Current development branch:** `v7.0.0.0-dev`

The v7 line keeps the existing HalilsIT browser interface and begins a controlled port of selected TV-format parsing/serialization knowledge from ChanSort.

## Screenshots

### Demo / OLED Theme

![TV Channel Editor Pro - Demo OLED Theme](demo-oled.png)

### Sony Bravia — Real SDB File

Real Sony `sdb.xml` support has been validated on actual TV hardware.

![TV Channel Editor Pro - Sony Bravia](sony-bravia.png)

### Samsung Legacy SCM — Experimental

Samsung Legacy SCM support is currently experimental and has not yet been validated on real Samsung TV hardware.

![TV Channel Editor Pro - Samsung SCM](samsung-scm.png)

English interface example:

![TV Channel Editor Pro - Samsung SCM English](samsung-scm-ENG.png)

## Current Status

- Sony Bravia SDB support: validated on real TV hardware
- Samsung Legacy SCM support: experimental
- LG webOS `GlobalClone00001.TLL` support: experimental
- LG Legacy / NetCast binary `xx*.TLL`: v7 ChanSort-derived pilot
- Vestel-platform `.sdx` / `SATCODX`: experimental
- Fully offline, single-file HTML application
- No cookies, no cloud processing, no external upload

## Features

- Channel search and filtering
- TV / Radio and source filtering
- Drag-and-drop channel ordering
- Bulk add / reversible remove
- Manual channel numbering
- Multi-column wide editing mode
- Undo / redo
- Turkish and English interface
- Multiple themes
- Automatic TV format detection through modular adapters

## Supported / Planned Formats

### Sony
Sony Bravia `sdb.xml`

Status: **Real-TV validated.**

### Samsung
Legacy Samsung SCM / `map-SateD`

Status: **Experimental.** The v7 roadmap will use ChanSort format knowledge to expand Samsung generation coverage.

### LG webOS
`GlobalClone00001.TLL`

Status: **Experimental.**

### LG Legacy / NetCast
Binary `xx*.TLL`

Status: **v7 ChanSort-derived pilot.** The first pilot profile is based on the real `xxMT47U-PZS00001.TLL` sample. The new parser follows the TLL DVB-S block structure, linked channel list and CRC32 rules instead of heuristic record scanning.

### Vestel platform
`.sdx` / `SATCODX`

Status: **Experimental.** ChanSort's SatcoDX loader will be evaluated for broader compatible-platform support.

## v7 Format Engine Roadmap

The current migration plan is:

1. LG Legacy / NetCast binary TLL pilot
2. Samsung expansion
3. TCL
4. Hisense
5. Panasonic
6. Philips
7. Grundig / MediaTek / Toshiba / Sharp and additional families

See [`docs/CHANSORT_SUPPORT_MATRIX.md`](docs/CHANSORT_SUPPORT_MATRIX.md) for the loader inventory and port matrix.

## Acknowledgements

Selected TV channel-list format implementations in the v7 line are derived in part from or based on format knowledge from **ChanSort by PredatH0r and contributors**.

ChanSort: https://github.com/PredatH0r/ChanSort

ChanSort is licensed under GNU GPL v3. TV Channel Editor Pro is also licensed under GNU GPL v3.

The ChanSort Windows/DevExpress user interface is not being ported. TV Channel Editor Pro keeps its own HalilsIT browser interface and workflow; only useful format-specific parsing, serialization, mapping and checksum logic is adapted where needed.

See [`CREDITS.md`](CREDITS.md) for detailed attribution.

## Privacy

TV channel list files are processed locally in your browser.

No channel list data is uploaded to a server.

## Support

If this project is useful to you, you can support its development through GitHub Sponsors:

https://github.com/sponsors/HalilsIT

## License

This project is licensed under the GNU General Public License v3.0.

Copyright © 2026 HalilsIT
