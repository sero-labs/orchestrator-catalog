# Triage report — issue #142 "CSV export drops the last row"

**Reproduced:** yes — any input file without a trailing newline loses its
final record on export.

**Where:** `export/csv.ts` `flushBuffer()` — the loop only emits on `\n`, so
the last unterminated line never flushes.

**Severity:** medium-high. Silent data loss, but only for files missing a
trailing newline (~10% of the sample fixtures).

**Effort:** small — flush the remainder in the `end` handler and add one
fixture. Suggested owner: whoever shipped the CSV export last week.

*(Sent to the team webhook after your approval.)*
