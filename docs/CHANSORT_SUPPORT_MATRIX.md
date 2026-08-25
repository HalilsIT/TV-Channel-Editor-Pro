# ChanSort ↔ TV Channel Editor Pro Support Matrix

This document tracks ChanSort loader projects and how they relate to TV Channel Editor Pro.

Status meanings:

- **Validated** — tested on real TV hardware in TV Channel Editor Pro.
- **Experimental** — parser/export exists but real-TV validation is pending.
- **v7 Pilot** — being reworked with ChanSort-derived format logic.
- **Planned** — ChanSort has a relevant loader; no TV Channel Editor Pro adapter yet.
- **Reference / utility** — not a TV-format adapter target.

| ChanSort loader | Main family / format role | TV Channel Editor Pro status | v7 direction |
|---|---|---|---|
| `ChanSort.Loader.Amdb` | AMDB family | Not supported | Planned after major TV brands |
| `ChanSort.Loader.Android` | Android TV-related channel data | Not supported | Planned / evaluate by vendor |
| `ChanSort.Loader.CmdbBin` | `dtv_cmdb_*.bin` family | Not supported | Planned; useful for several OEM brands |
| `ChanSort.Loader.DBM` | `.DBM` receiver/TV databases | Not supported | Planned later |
| `ChanSort.Loader.Enigma2` | Enigma2 bouquets/services | Not supported | Optional later |
| `ChanSort.Loader.Grundig` | Grundig XML/binary families | Not supported | Planned |
| `ChanSort.Loader.Hisense` | Hisense DB/BIN/CSV families | Not supported | High-priority planned |
| `ChanSort.Loader.LG` | LG binary TLL + GlobalClone | **GlobalClone experimental; Legacy v7 Pilot** | First ChanSort-derived port |
| `ChanSort.Loader.Loewe` | Loewe channel lists | Not supported | Planned later |
| `ChanSort.Loader.M3u` | SAT>IP / M3U | Not supported | Optional later |
| `ChanSort.Loader.MediaTek` | MediaTek-platform TV formats | Not supported | Important shared-OEM candidate |
| `ChanSort.Loader.Medion` | Medion-specific formats | Not supported | Planned later |
| `ChanSort.Loader.Panasonic` | Panasonic SQLite/BIN/TXT/SDX families | Not supported | High-priority planned |
| `ChanSort.Loader.Philips` | Philips binary/XML/database families | Not supported | High-priority planned |
| `ChanSort.Loader.Samsung` | Samsung SCM + newer ZIP/DB families | **Legacy SCM experimental** | Expand existing adapter from ChanSort |
| `ChanSort.Loader.SatcoDX` | SatcoDX text/binary lists | **Vestel SATCODX experimental** | Compare/merge knowledge; broaden OEM support |
| `ChanSort.Loader.Sharp` | Sharp CSV and related OEMs | Not supported | Planned |
| `ChanSort.Loader.Sony` | Sony `sdb.xml` | **Validated on real Sony TV** | Keep native adapter; expand only where useful |
| `ChanSort.Loader.TCL` | TCL channel-list formats | Not supported | **High-priority planned** |
| `ChanSort.Loader.TechniSat` | TechniSat formats | Not supported | Planned later |
| `ChanSort.Loader.Toshiba` | Toshiba SQLite/ZIP families | Not supported | Planned |
| `ChanSort.Loader.VDR` | VDR text lists | Not supported | Optional later |
| `ChanSort.Loader.VisionEdge4K` | Vision Edge 4K | Not supported | Planned later |
| `ChanSort.Loader.LG.UI` | ChanSort LG desktop UI helper | Not applicable | Do not port |
| `ChanSort.Loader.RefList` | ChanSort reference-list utility | Not applicable | Do not port initially |
| `ChanSort.Loader.Unsupported` | Unsupported-format diagnostics | Not applicable | Reference only |

## Current TV Channel Editor Pro adapters

| Brand / family | Format | Status |
|---|---|---|
| Sony Bravia | `sdb.xml` | **Real-TV validated** |
| Samsung Legacy | `.scm` / `map-SateD` 168B | Experimental |
| LG webOS | `GlobalClone00001.TLL` | Experimental |
| LG Legacy / NetCast | binary `xx*.TLL` | **v7 ChanSort-derived pilot** |
| Vestel platform | `.sdx` / `SATCODX` 133B | Experimental |

## Suggested port priority after LG pilot

1. Samsung — use ChanSort to expand beyond the single legacy SCM profile.
2. TCL — high sales volume and explicit ChanSort loader.
3. Hisense — multiple database/BIN families already covered by ChanSort.
4. Panasonic — several SQLite/BIN/TXT/SDX generations.
5. Philips — several binary/XML/database generations.
6. Grundig / MediaTek / Toshiba / Sharp.
7. Receiver and niche families (`DBM`, Enigma2, VDR, M3U, etc.).

Source inventory: ChanSort `source/` directory and `source/build.md`, inspected for the v7 migration.
