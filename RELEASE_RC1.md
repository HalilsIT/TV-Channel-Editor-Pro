# TV Channel Editor Pro — v7.9.0.0-rc1

Project checkpoint created on 2026-08-25 before a planned development pause.

## RC1 artifact

Expected file name:

`tv_kanal_editoru_pro_v7.9.0.0-rc1(finalization-info-modal).html`

SHA-256:

`f691278006dc7663eaacb87e0ee87fa218f0e18614ef0adec0304fe729a7091f`

Size:

`368,308 bytes`

## Frozen active scope

- Sony Bravia `sdb.xml` — real-TV validated
- Samsung Legacy `.scm` / `map-SateD` 144/168/172B — software tested
- LG webOS `GlobalClone*.TLL` — experimental
- LG Legacy / NetCast `xx*.TLL` — software-tested ChanSort-derived pilot
- TCL / Thomson `.tar` (`DtvData.db` + `cloneCRC.bin`) — real-sample software round-trip tested
- Vestel `.sdx` / `SATCODX` — experimental

Hisense and Philips remain deferred until real export samples are available.

## Attribution

Selected format parsing/serialization/layout/checksum logic in the v7 line is derived in part from ChanSort by PredatH0r and contributors under GNU GPL v3. See `CREDITS.md`.
