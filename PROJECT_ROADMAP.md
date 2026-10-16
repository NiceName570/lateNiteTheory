# Project Roadmap

## Phase 0 - continuity and integrity

Question answered: can later work be resumed without losing provenance or
repeating failed paths?

- [x] Preserve the append-only research log.
- [x] Build and validate the pre-move path/size/time/SHA-256 inventory.
- [x] Create one project index, live status file, roadmap, and ID registers.
- [ ] Write a path map before any legacy move or rename.
- [x] Initialize Git with large/raw/tool exclusions after the checkpoint.

## Phase 1 - bounded historical branches

Question answered: what behavior is reproducible without claiming missing
hardware details?

- [x] No. 4 normalized behavioral package approved, 5/5.
- [x] Bare/Holland OM2 external-system sensitivity package approved, 5/5.
- [x] AZ-58 corrected-topology RF sensitivity package approved, 3/3.
- [ ] AZ-58 rail-only 950 V versus 2.9 kV gate, after the current checkpoint.

## Phase 2 - Bare carrier/sideband/power discrimination

Question answered: which spectral components reach the load, where are they
created, and how does broad coverage trade against power and selectivity?

- [x] `BH-SPP-001` approved and frozen.
- [x] `BH-SP00`: carrier-only numerical/power baseline, PASS and independently verified.
- [x] `BH-SP01`: carrier plus first sideband pair and time-domain reconstruction, PASS and independently verified.
- [x] Visible checkpoint and user review.
- [x] `BH-SP02`-`BH-SP06`: PASS twice, independently verified and reproducible.
- [x] `BH-SPP-002`: plasma-antenna circuit design package frozen with separate
  1999 and 2014 architectures; no run authorized.
- [x] `BH-SP07`: amplifier bandwidth/compression diagnostics passed twice,
  independently verified; development failures and repairs preserved.
- [x] `BH-SP08`: separate cable/matcher branches into a calibrated 50-ohm load;
  44-case AC gate and connected transient passed repeated independent checks,
  with 48-/96-section convergence and all failed attempts retained.
- [ ] `BH-SP09`: tube-state load model after source review; Claude's detailed
  package is now received in `incoming/claude-2026-09-30-plasma-tube-rf-impedance`.
  No unsupported strike or plasma dynamics; first audit source/figure claims.

## Phase 3 - common measurement method

Question answered: can all three branches be compared using the same declared
electrical observations without mixing their component values?

- Stage-by-stage frequency, phase, voltage, current, power, impedance, spectrum,
  field, and optical timing schema.
- Separate source, network, and load-created components.
- Preserve unlit, strike, and sustained-discharge states.

## Phase 4 - low-power physical validation

Question answered: do the simulation and instruments agree on a calibrated
non-biological reference load?

- Requirements and equipment adequacy check.
- 50-ohm low-power validation and uncertainty budget.
- KiCad measured prototype schematic only after requirements freeze.
- Falstad explanatory visuals based on approved measurements.

## Phase 5 - instrumented gas-load prototype

Question answered: how does a real gas discharge reshape the electrical and
optical signal?

This phase requires a new proposal and authorization. It is not authorized by
`BH-SPP-001`.
