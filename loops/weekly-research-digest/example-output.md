# Weekly research digest — week of 2026-06-22

Your project: a TypeScript CLI with CSV/report tooling.

1. **Node 24.3 shipped a stable `util.parseArgs` overhaul** — your CLI parses
   flags by hand in `cli.ts`; migrating would delete ~80 lines and fix the
   quoting bug logged in HYGIENE.md.
2. **`csv-spectrum` added 12 new edge-case fixtures** — cheap win: point the
   CSV export tests at them to harden the parser you shipped last week.
3. **TypeScript 6.0 beta tightened `exactOptionalPropertyTypes`** — two spots
   in `report/format.ts` will start erroring; a 10-minute fix now avoids a
   noisy upgrade later.

Saved as `weekly-digest` in this loop's reports.
