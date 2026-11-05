# End-to-End Verification Playbook

**A successful install/build is only the beginning.** Verify complete user journeys.

## Requirement-to-evidence matrix
For each feature track:

| Feature | User action | Expected behavior | Automated test | Manual UI test | Status |
|---|---|---|---|---|---|
| Example: filter | Select a date and click Apply | Only matching rows appear | API returns expected IDs | Click Apply and inspect table | NOT TESTED |

Use status values **PASS / FAIL / NOT TESTED**. Do not pre-fill PASS.

## Recommended layered checks
1. **Data:** Counts, duplicates, join coverage, missing values, units, nonempty source, no invented rows.
2. **Business rules:** Hand-check one normal, one boundary, one invalid/missing case.
3. **API:** Start server; send a real request; check HTTP code, response body, persisted state and failure response.
4. **UI wiring:** Confirm click handlers, state changes, network calls and response rendering. If permitted, click through the actual preview; otherwise give the human an exact manual checklist.
5. **Full flow:** Complete one realistic user journey from input to stored/retrieved result.
6. **Regression:** Re-run the core checks after fixes.

## Debug non-responsive UI (work from evidence)
- Write **reproduction steps / expected / actual**.
- Inspect browser console/network logs **only where available and allowed**.
- Trace: control -> handler -> request -> API -> domain logic -> data -> response -> UI update.
- Fix the root cause, re-run tests and ask the human to click again when automated browser UI interaction is restricted.
- If the issue cannot be reproduced, mark it NOT TESTED, not fixed.

## Reporting format
```text
FEATURE: ...
STATUS: PASS | FAIL | NOT TESTED
COMMAND / ACTION: ...
EXPECTED: ...
OBSERVED: ...
EVIDENCE: ...
OPEN RISK: ...
```

When choosing a heuristic/optimization method, validate feasibility of all hard constraints separately from solution quality. Compare small cases against brute force or a baseline when feasible.

Before completion, ask the human to perform a short smoke check of the most consequential visible controls and input flows.
