---
name: diagnose-bug
description: Diagnose bugs, failures, regressions, and performance problems by building a tight reproducible feedback loop before hypothesising or fixing.
---

# Diagnose Bug

Use a disciplined loop so the fix addresses the reported symptom rather than a nearby failure.

## Workflow

1. Redact secrets and sensitive payloads from evidence.
2. Build the smallest fast feedback loop that can go red on the exact user symptom.
3. Reproduce the issue repeatedly and capture the observable failure.
4. Minimise the input, trace, or code path while preserving the symptom.
5. Form a small set of competing hypotheses and instrument only the boundaries that distinguish them.
6. Turn the minimised reproduction into a regression test.
7. Apply the smallest fix, verify the regression test, then rerun the original reproduction.
8. Remove temporary instrumentation and record the confirmed cause.

Do not declare success because a command exits cleanly. The loop must detect this specific bug and remain deterministic enough to trust.
