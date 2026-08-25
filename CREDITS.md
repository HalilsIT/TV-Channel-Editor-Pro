# Credits and Acknowledgements

## TV Channel Editor Pro / HalilsIT

TV Channel Editor Pro is an independently developed browser application by **HalilsIT**.

The following areas are original project work unless a source comment explicitly states otherwise:

- browser-only/offline application architecture
- user interface and interaction model
- source/target channel workflow
- filtering and search
- channel ordering and numbering workflow
- wide multi-column editing mode
- Undo / Redo behavior
- reversible `Kaldır` model
- generic channel model and modular adapter architecture
- theme system and bilingual TR/EN interface
- integration logic between generic UI and TV-specific adapters
- substantial TV-format reverse-engineering and sample-specific implementation work

Copyright © 2026 HalilsIT

Contact: halilsit@outlook.com

Repository: https://github.com/HalilsIT/TV-Channel-Editor-Pro

## ChanSort

Selected TV channel-list format knowledge and implementation concepts are derived in part from **ChanSort**, created by **PredatH0r** and contributors.

ChanSort repository:
https://github.com/PredatH0r/ChanSort

ChanSort is distributed under the **GNU General Public License v3.0 (GPL-3.0)**.

TV Channel Editor Pro is also distributed under **GPL-3.0**.

The project does **not** port ChanSort's Windows/DevExpress user interface. Where a format implementation is derived from ChanSort, the source code contains an explicit attribution comment identifying ChanSort and, where practical, the relevant upstream implementation.

Only specifically identified format-engine portions are ChanSort-derived. It would be inaccurate to describe the complete TV Channel Editor Pro application as a ChanSort port.

## Adapter-origin notes

### Sony Bravia — `sdb.xml`

Predominantly original HalilsIT reverse-engineering and implementation. The project derived its Sony behavior through real sample comparison and real-TV validation, including Sony-specific channel-number packing and preservation behavior. The active Sony adapter is intentionally kept native.

### Samsung Legacy — `.scm / map-SateD`

The project's first 168-byte implementation was developed from its own real Samsung sample. During v7, ChanSort's Samsung mappings and serializer behavior were studied to verify the existing work and expand support to the 144/168/172-byte legacy profile family.

Relevant upstream references include:

- `ChanSort.Loader.Samsung/ChanSort.Loader.Samsung.ini`
- `ChanSort.Loader.Samsung/Scm/ScmSerializer.cs`
- `ChanSort.Loader.Samsung/Scm/ScmChannelBase.cs`

The current v7 Samsung adapter is therefore a mixed/original-plus-ChanSort-derived implementation rather than a purely clean-room adapter.

### LG webOS — `GlobalClone*.TLL`

Predominantly original HalilsIT sample analysis and browser implementation based on real XML + embedded `legacybroadcast` JSON data.

### LG Legacy / NetCast — binary `xx*.TLL`

Hybrid implementation.

ChanSort components studied for the v7 binary engine include:

- `ChanSort.Loader.LG/Binary/TllFileSerializer.cs`
- `ChanSort.Loader.LG/Binary/DvbsDataLayout.cs`
- `ChanSort.Loader.LG/Binary/SatChannelListHeader.cs`
- `ChanSort.Loader.LG/Binary/TllChannelBase.cs`
- `ChanSort.Loader.LG/ChanSort.Loader.LG.ini`
- `ChanSort.Api/Utils/Crc32.cs`

The exact `xxMT47U-PZS00001.TLL` 687532-byte DVB-S block / 84-byte channel-record profile used by TV Channel Editor Pro was derived by combining ChanSort's documented LG binary TLL container model with byte-level analysis of the project's real sample file. That exact 687532/84 profile was not present in the inspected ChanSort LG profile data.

### TCL / Thomson — TAR + `DtvData.db`

ChanSort-derived format/schema/edit-flag/CRC knowledge combined with a TV Channel Editor Pro-specific browser implementation.

Relevant upstream references include:

- `ChanSort.Loader.TCL/DtvDataSerializer.cs`
- `ChanSort.Loader.TCL/TclPlugin.cs`
- `ChanSort.Api/Utils/Crc16.cs`

TV Channel Editor Pro implements its own browser-side TAR handling and focused SQLite b-tree reader/patcher so the single-file HTML application can modify the real TCL sample without embedding ChanSort's desktop runtime.

### Vestel — `.sdx / SATCODX`

Current adapter originates predominantly from HalilsIT sample analysis and implementation. ChanSort's SatcoDX loader is a useful reference but the current Vestel adapter is not presented as a ChanSort port.

## License notice

Redistribution, modification, derivative works and substantial reuse must comply with the applicable GPLv3 terms. Applicable copyright, license and third-party attribution notices must be preserved, and corresponding source must be provided where required by GPLv3.
