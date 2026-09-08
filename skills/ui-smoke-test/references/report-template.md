# UI smoke-test report

- **URL / run:** tested URL and timestamp
- **Viewports:** actual desktop and mobile CSS dimensions
- **Summary:** PASS, FAIL, or BLOCKED; number of reproduced defects

## Checks

| Check | Result | Observed evidence |
| --- | --- | --- |
| Seed data and counters | PASS / FAIL / BLOCKED | |
| Active / Completed / All filters | PASS / FAIL / BLOCKED | |
| Add and toggle a task | PASS / FAIL / BLOCKED | |
| Whitespace input | PASS / FAIL / BLOCKED | |
| Mobile layout | PASS / FAIL / BLOCKED | |
| Console errors | PASS / FAIL / BLOCKED | |

## Defects

For each reproduced defect, provide:

- **Title and impact:** describe the user-visible problem.
- **Steps:** numbered reproduction steps starting from Reset demo.
- **Expected / actual:** explain the mismatch.
- **Evidence:** screenshot path or exact DOM measurements / visible labels.

## Cleanup and next step

State whether seed data and desktop viewport were restored. List untested areas and blockers. Recommend the coding-agent handoff for reproduced defects, or state that the exercised checks passed. Do not claim a full security or accessibility audit.