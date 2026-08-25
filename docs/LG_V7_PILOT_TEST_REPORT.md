# v7 LG Legacy Pilot — Binary Diff Test

Sample: `xxMT47U-PZS00001.TLL`

## Detected structure

- File size: **706,030 bytes**
- Header magic: `ZZZZ`
- DVB-S block offset: **18,488**
- DVB-S block size: **687,532 bytes**
- DVB-S subblock CRCs: **5 / 5 valid**
- Satellite table: **64 × 44 bytes**
- Transponder table: **2400 × 48 bytes**
- Channel capacity: **6000 records**
- Channel record size: **84 bytes**
- Linked-list active channel records: **704**
- LNB table: **40 × 48 bytes**

The 687,532-byte block size is exactly reproduced by the ChanSort `DvbsDataLayout` formula when the sample-specific 84-byte channel record size is used.

## Channel record mapping validated for the sample

- Program number: `+8`, UInt16 LE
- Radio flag: program number bit `0x4000`
- Preset program number: `+10`
- Deleted / encrypted flags: byte `+14`
- Lock / skip / hide / moved flags: byte `+15`
- Service ID: `+18`, UInt16 LE
- Service type: `+20`
- Name length: `+21`
- Channel name: `+22`, max 40 bytes

## No-op round trip

A no-edit export is designed to return the original byte array unchanged.

Expected diff: **0 bytes**.

## Three-channel renumber test

Test edit:

- `TGRT HABER HD`: 17 → 20
- `DIYANET TV HD`: 20 → 21
- `TGRT BELGESEL HD`: 21 → 17

Result:

- Total changed bytes: **10**
- 6 bytes are within the three edited channel records (program-number byte + moved flag).
- 4 bytes are the DVB-S channel-subblock CRC32.
- No unrelated firmware, satellite, transponder, LNB or other channel-record bytes changed.
- All five DVB-S subblock CRCs validate after export.

This is the desired minimal-diff behavior for the v7 pilot.
