# TV Channel Editor Pro — v7.9.0.5-rc6

Release-candidate checkpoint created on 2026-08-25 during final stabilization before a development pause.

## RC6 artifact

Expected file name:

`tv_kanal_editoru_pro_v7.9.0.5-rc6.html`

SHA-256:

`30bb4233e4d2f3ad828b112bdea3cd0f69c4ec622430e91bcbef856b4e54a53c`

Size:

`373,284 bytes`

## RC6 highlights

- GNU GPL v3 is visible in the application subtitle.
- A full GPL-compatible source header was added before `<!DOCTYPE html>`.
- The source header explicitly distinguishes original HalilsIT work from specifically identified ChanSort-derived format-engine portions.
- Demo data includes a source-only hidden channel so the `Gizli` workflow can be demonstrated without loading a TV file.
- English information modal translations are fixed.
- Contact email and language/info controls use frameless header placement.
- The English `Assigned` target column was widened slightly.
- Privacy remains shown as a centered two-line `%100 Yerel ve Güvenli / no cookies` badge.

## Frozen active scope

- Sony Bravia `sdb.xml` — **real-TV validated**
- Samsung Legacy `.scm / map-SateD` 144/168/172B — **software tested**
- LG webOS `GlobalClone*.TLL` — **experimental**
- LG Legacy / NetCast `xx*.TLL` — **software tested / hybrid ChanSort-derived engine**
- TCL / Thomson `.tar` (`DtvData.db` + `cloneCRC.bin`) — **real-sample software round-trip tested**
- Vestel `.sdx / SATCODX` — **experimental**

Hisense and Philips remain deferred until real export samples are available.

No additional brand families are planned for the current development cycle.

## Original work / attribution summary

Predominantly original HalilsIT implementations:

- Sony Bravia
- LG webOS
- Vestel
- browser UI/workflow/architecture and generic editing engine

Mixed / hybrid implementations:

- Samsung Legacy — original 168B work later expanded and verified using ChanSort mappings
- LG Legacy / NetCast — ChanSort-derived binary container/layout/CRC concepts plus original sample-specific 84B profile analysis
- TCL / Thomson — ChanSort-derived format/schema/CRC knowledge plus original browser TAR and focused SQLite b-tree implementation

See `CREDITS.md` and `docs/CHANSORT_SUPPORT_MATRIX.md` for details.

## License

TV Channel Editor Pro is distributed under GNU GPL v3.

Selected format-engine portions derived from ChanSort retain explicit attribution to ChanSort by PredatH0r and contributors. Applicable GPLv3 copyright, license, attribution and corresponding-source obligations remain in effect for redistributed or modified versions.
