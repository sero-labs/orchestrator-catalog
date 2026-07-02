# HYGIENE.md (appended 2026-06-29)

- `cli.ts:88` — `console.log('DEBUG args', args)` left in from the flag work
- `report/format.ts:12-31` — commented-out legacy formatter, superseded two
  weeks ago; safe to delete
- `export/csv.ts` — 517 lines, over the 500-line house limit; the fixture
  builders at the bottom want their own file
- `TODO parser/dates.ts:104` — "handle BC dates??" has no owner

*(Nothing was changed — findings only. Clean passes add no entry.)*
