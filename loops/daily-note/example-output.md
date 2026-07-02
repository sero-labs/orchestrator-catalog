# Daily note — Tuesday 2026-06-30

**Since yesterday**
- `parser/dates.ts`: fixed the ISO-week edge case (2 commits)
- `export/csv.ts`: new CSV export with header row support

**Looks unfinished**
- `TODO` in `cli.ts:41` — `--quiet` flag parsed but never used
- `export/csv.test.ts` covers happy path only

**Suggested focus today**
Wire up `--quiet` and add a malformed-input test for the CSV export — both are
small and unblock the release checklist.
