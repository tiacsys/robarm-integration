# robarm-integration: rules for agents

Read the workspace `CLAUDE.md` (copied from `xdmod/launch/CLAUDE.md`) first. This file adds the
rules of this repo. Run every command from the workspace root.

## What this repo is

System test cases (`INT-STC`), integration test cases (`INT-ITC`), the HIL setups (`hil/`), and
the documents `int-test-spec` and `int-test-report`. Its docs build includes every upstream
document (syseng, sw, ee, me), so it needs the `integration` role.

## Rules

- **Tests live by what they verify** (D115): every test that verifies a `SYS-REQ` or a `SYS-IF`
  is here, even if it touches only one domain.
- A test case links to what it verifies (`verifies`); the requirement never links back (D5).
- **Evidence:** HIL run records go to the orphan branch `evidence`, never to `main`. Only runs of
  `main` or of a baseline count (D60); runs of PR branches are previews. Agents prepare verdicts,
  but only a human commit counts as one (D58).
- Each test result names the configuration it ran on (`config`, a `SYS-CFG` ID, D103).

## Pitfalls

- The docs build of this repo is the largest one (all upstream documents). If an upstream
  document fails, fix it in its own repo.
- The `evidence` branch and the run-record format are a later task (4.5a, 4.6); do not create
  them by hand.
