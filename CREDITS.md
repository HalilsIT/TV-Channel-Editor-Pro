# Credits and Acknowledgements

## ChanSort

TV Channel Editor Pro uses and adapts selected TV channel-list format knowledge and implementation concepts from **ChanSort**, created by **PredatH0r** and its contributors.

ChanSort repository:
https://github.com/PredatH0r/ChanSort

ChanSort is distributed under the **GNU General Public License v3.0 (GPL-3.0)**.

TV Channel Editor Pro is also distributed under **GPL-3.0**.

The project does **not** copy ChanSort's Windows/DevExpress user interface. The HalilsIT interface, workflow and browser application remain independent. Selected format-specific parsing, serialization, record-layout and checksum logic may be ported or adapted to JavaScript where useful.

Where a format implementation is derived from ChanSort, the source code should contain an explicit attribution comment identifying ChanSort and the relevant upstream implementation.

### v7 pilot

The first ChanSort-derived pilot is the LG Legacy / NetCast binary `.TLL` engine. The following ChanSort components were studied for this work:

- `ChanSort.Loader.LG/Binary/TllFileSerializer.cs`
- `ChanSort.Loader.LG/Binary/DvbsDataLayout.cs`
- `ChanSort.Loader.LG/Binary/SatChannelListHeader.cs`
- `ChanSort.Loader.LG/Binary/TllChannelBase.cs`
- `ChanSort.Loader.LG/ChanSort.Loader.LG.ini`
- `ChanSort.Api/Utils/Crc32.cs`

The exact `xxMT47U-PZS00001.TLL` 687532-byte DVB-S block / 84-byte channel-record profile used by TV Channel Editor Pro was derived by combining ChanSort's documented LG binary TLL container model with byte-level analysis of the project's real sample file.

## TV Channel Editor Pro

Interface design, browser architecture, generic channel model, workflow, themes, wide editing mode, Undo/Redo and project-specific adapters are part of TV Channel Editor Pro / HalilsIT.

Copyright © 2026 HalilsIT
