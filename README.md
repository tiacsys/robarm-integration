# robarm-integration: evidence branch

This orphan branch holds the **test run records** of the robot arm (D57, D73). It shares no
history with `main` and is never merged. Only `curatrix evidence record` writes here.

```
runs/<YYYY>/<run id>/record.json        the run record (schema xdmod-run-record/1)
runs/<YYYY>/<run id>/twister.json       Twister's JSON report of the run
runs/<YYYY>/<run id>/twister_report.xml Twister's JUnit report
```

- **Schema and fields:** `xdmod/curatrix/src/curatrix/data/run-record.schema.json`, explained in
  `xdmod/curatrix/README.md`, section "Evidence (run records)".
- **Evidence rule (D60):** a record is written here only if every west project was at its
  manifest pin with a clean tree, and the manifest, xdmod and every robarm repo were on `main`
  (or the manifest at a `baseline/*` tag). Runs on PR branches are previews and are not kept.
- **Kinds:** `hil` runs on a HIL setup (`hil/<setup>` on `main`) carry the firmware sha256 and the
  SHAs of all pinned repos (R5). `sim` runs (native_sim, QEMU) are test results, never HIL evidence.
- **Validity (D131):** the test report reads the records with `curatrix evidence read` and makes
  one `TR` need per traced result. A record whose SHAs no longer match the current pins is shown
  as `stale` and doesn't count for coverage. Each baseline records this branch's SHA.

Record a run (from the workspace root, on `main` pins, clean tree):

```sh
curatrix evidence record build/<area>/twister --config SYS-CFG-nnnn --kind hil --setup <setup>
git -C robarm-integration push origin evidence
```
