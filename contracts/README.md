# Contracts produced by assessment

## `@givecare/tools.InstrumentExport` (live, v1)

`data/instruments-export.json`, consumed by mira (`scripts/sync-instruments.ts`)
and care-evals. The id is frozen while consumers pin it.

## `@givecare/tools.InstrumentExport/v2` (written, not yet produced)

- Schema: [`instrument-export.v2.schema.json`](instrument-export.v2.schema.json)
- Each instrument carries `version`, `license` and `items`, and the export
  carries `owner_revision`, so a stored measurement names the exact instrument
  version and scoring that produced it.
- One definition: SMS scoring and the web assessment read this projection
  instead of keeping their own copies (today BSFC-s is hand-written in
  web `apps/site/src/lib/bsfc.ts` and mira
  `care/assessment/scoring.ts`).
- Licensed instruments: BSFC-s stays out of the open SDK until Ali decides
  where its licensed definition lives. In v2 it is absent (not inlined) unless
  `redistributable` is true for it.
- The npm package name `@givecare/tools` is unchanged.
