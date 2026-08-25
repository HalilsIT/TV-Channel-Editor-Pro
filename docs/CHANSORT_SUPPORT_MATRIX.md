# ChanSort ↔ TV Channel Editor Pro Support Matrix

This document records how ChanSort loader knowledge relates to the active TV Channel Editor Pro `v7.9.0.5-rc6` scope.

The project is currently in **feature freeze**. The matrix is no longer a promise to port every ChanSort loader.

## Status meanings

- **Real-TV validated** — tested successfully on actual TV hardware in TV Channel Editor Pro.
- **Software tested** — parser/export/integrity behavior validated with real sample files, but TV hardware import is still pending.
- **Experimental** — parser/export exists, but validation is limited.
- **Deferred** — no active adapter; real sample required before implementation is advertised.
- **Reference only** — ChanSort may contain useful knowledge, but no active port is planned for this development cycle.

## Active TV Channel Editor Pro formats

| Brand / family | Format | TV Channel Editor Pro status | Relationship to ChanSort |
|---|---|---|---|
| Sony Bravia | `sdb.xml` | **Real-TV validated** | Native/original HalilsIT implementation; ChanSort is not the basis of the active adapter |
| Samsung Legacy | `.scm / map-SateD` 144/168/172B | **Software tested** | Original 168B sample work later expanded/verified with ChanSort Samsung mappings |
| LG webOS | `GlobalClone*.TLL` | **Experimental** | Predominantly original HalilsIT sample analysis / implementation |
| LG Legacy / NetCast | binary `xx*.TLL` | **Software tested** | Hybrid: ChanSort-derived container/layout/CRC logic + original 687532-byte / 84-byte sample profile analysis |
| TCL / Thomson | `.tar` with `DtvData.db` + `cloneCRC.bin` | **Software round-trip tested** | ChanSort-derived schema/edit-flag/CRC knowledge + original browser TAR/SQLite implementation |
| Vestel | `.sdx / SATCODX` | **Experimental** | Predominantly original HalilsIT sample analysis; ChanSort SatcoDX remains a reference |

## Deferred formats

| ChanSort loader | Family | TV Channel Editor Pro status | Current decision |
|---|---|---|---|
| `ChanSort.Loader.Hisense` | Hisense DB/BIN/CSV families | Deferred | Do not advertise support without a real export sample |
| `ChanSort.Loader.Philips` | Philips binary/XML/database families | Deferred | Do not advertise support without a real export sample |

## ChanSort loaders not targeted in the current cycle

The following loaders may be useful references in the future, but no active port is planned for the current frozen scope:

- `ChanSort.Loader.Amdb`
- `ChanSort.Loader.Android`
- `ChanSort.Loader.CmdbBin`
- `ChanSort.Loader.DBM`
- `ChanSort.Loader.Enigma2`
- `ChanSort.Loader.Grundig`
- `ChanSort.Loader.Loewe`
- `ChanSort.Loader.M3u`
- `ChanSort.Loader.MediaTek`
- `ChanSort.Loader.Medion`
- `ChanSort.Loader.Panasonic`
- `ChanSort.Loader.Sharp`
- `ChanSort.Loader.TechniSat`
- `ChanSort.Loader.Toshiba`
- `ChanSort.Loader.VDR`
- `ChanSort.Loader.VisionEdge4K`

Support/helper projects such as `ChanSort.Loader.LG.UI`, `ChanSort.Loader.RefList` and `ChanSort.Loader.Unsupported` are not TV-format adapter targets.

## Attribution policy

TV Channel Editor Pro is not a ChanSort UI port and should not be described as one.

The HalilsIT browser UI, workflow, generic channel model, filtering, ordering, wide editor, Undo/Redo, reversible-remove model, offline architecture and adapter abstraction are original project work.

Where selected format-engine logic is derived from ChanSort, the corresponding source section should retain an explicit ChanSort attribution comment and remain compliant with GNU GPL v3.

See `CREDITS.md` for adapter-by-adapter attribution details.
