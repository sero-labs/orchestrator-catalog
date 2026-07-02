# Pull request: fix flaky date assertion breaking CI (#87)

**CI failure:** `test / unit (node 24)` — `parser/dates.test.ts` asserts on
local midnight, so the suite fails in any CI region east of UTC.

**Fix (smallest change that addresses the cause):** pin the two assertions to
UTC with `Date.UTC(...)` instead of the local-time constructor. No production
code touched.

**Verified:** re-ran the failed suite under `TZ=Asia/Tokyo` and `TZ=UTC` —
both green.

*(Opened as a PR on a branch — nothing lands without your review.)*
