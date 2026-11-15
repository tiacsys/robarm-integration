# HIL setups

One folder per hardware-in-the-loop setup, `hil/<setup>/`: the hardware map, fixtures, a
reference to the wiring in robarm-ee (`proto/`), and the runner configuration. Each setup runs on
one configuration of the system model (`SYS-CFG`).

HIL run records (firmware hash, the repo SHAs of the manifest, Twister results) are kept on the
orphan branch `evidence` of this repo, never on `main` (D57, D73). Only runs of `main` or of a
baseline count as evidence (D60).
