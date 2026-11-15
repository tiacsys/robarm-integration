# System and integration tests

Every test that verifies a system requirement (`SYS-REQ`) or a system interface (`SYS-IF`) lives
here, even if it touches only one domain (D115). Tests of domain requirements stay in the domain
repos.

* System test cases are `INT-STC` needs, integration test cases are `INT-ITC` needs. Both are
  written in `docs/int-test-spec/`, with IDs from `ids.yaml`.
* Scripts and Twister configurations that run them go into this folder, one folder per test or
  test group.
