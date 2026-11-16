# robarm-integration

System and integration tests of the robot arm example of [XDMOD](https://github.com/tiacsys/xdmod):
the right side of the V-model at system level, the hardware-in-the-loop (HIL) setups, and the
test documents.

Status: **skeleton** (Phase 4). The structure, the checks and empty documents are in place; the
content comes in Phase 6.

## Layout

| Path | What |
|---|---|
| `tests/` | system and integration test cases (scripts, Twister configurations) |
| `hil/<setup>/` | HIL setups: hardware map, fixtures, wiring reference, runner configuration |
| `docs/int-test-spec/` | System and Integration Test Specification |
| `docs/int-test-report/` | System and Integration Test Report |
| `ids.yaml` | ID ledger for `INT-*` IDs |
| `checks.yaml` | what `curatrix check robarm-integration` runs |
| `claude/` | rules and skills for agents working in this repo |
| branch `evidence` | orphan branch with HIL run records (created by a later task) |

Every test that verifies a system requirement or a system interface lives here, even if it
touches only one domain (D115).

## Use

This repo is a west project of the [robarm-manifest](https://github.com/tiacsys/robarm-manifest)
workspace and needs the `integration` role (all design repos). Run every command from the
workspace root:

```sh
curatrix docs robarm-integration                  # own and all upstream documents (strict)
curatrix check robarm-integration --stage local   # all checks, as before a push
```

## Licence

Apache-2.0, see `LICENSE`.
