---
name: diagnose-bug
description: Diagnose bugs, failures, regressions, and performance problems through a reproducible feedback loop, and apply a verified fix when requested.
---

# Diagnose bug

Establish the cause with a feedback loop that detects the reported symptom. Do
not start from a preferred fix and work backwards.

## Build the evidence

1. Record the expected behaviour, observed behaviour, environment, and exact
   reproduction command. Redact secrets and sensitive payloads.
2. Reproduce the failure more than once. If it is intermittent, measure the
   frequency and preserve the conditions under which it occurs.
3. Reduce the input, trace, or code path while keeping the same symptom.
4. Separate observations from inferences. Maintain a short hypothesis ledger
   with evidence for and against each candidate cause.
5. Add instrumentation only at boundaries that distinguish those hypotheses.

If the symptom cannot be reproduced, report what was checked and what evidence
is missing. Do not manufacture certainty from a nearby failure.

## Fix when implementation is in scope

Implementation is in scope when the user asked for a fix. Otherwise report the
confirmed cause and stop. Before changing production code, turn the minimal
reproduction into a behaviour-focused regression test and confirm that it fails
for the intended reason. Apply the smallest fix that addresses the confirmed
cause.

Verify the regression test, the original reproduction, and the repository's
applicable validation. Remove temporary instrumentation. Report the confirmed
cause, changed behaviour, exact checks run, and any check that could not be run.
A clean exit alone is not proof that this specific bug is fixed.
