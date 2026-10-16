# Current evidence inventory and readiness audit

Audit date: 2026-09-29

## Recovery and authority

- The workspace is **not a Git repository**. `git status` returned
  `fatal: not a git repository`. Therefore recovery currently depends on file
  hashes, preserved source copies, run directories, and append-only logs.
- `RIFE_RESEARCH_LOG.md` is the decision authority.
- `simulations/az58/runs/<attempt>/attempt_journal.txt`, generated decks, logs,
  raw files, and result reports are execution evidence.
- Checkpoints and `RIFE_NEXT_STEPS.md` are summaries and may become stale; they
  must not override later logged results.

## Branch readiness

| Branch | Evidence present locally | Standard dossier | Simulation | Readiness decision |
|---|---|---|---|---|
| 1 pre-Crane | No. 4 charts/notes, Johnson letter, Kennedy manuals, trial manuscript | populated `NO4_DEVICE_DOSSIER.md` | five-run behavioral batch and independent verifier passed | normalized behavioral simulation approved; historical circuit replica not approved |
| 2 AZ-58 | three source PDFs/text, source netlist, tools, full run family | information spread across log/checkpoint plus final RF specification | final three-representation RF gate and independent verifier passed | corrected-topology RF sensitivity simulation approved; complete/audio/cable replica not approved |
| 3 Bare/Holland | four patents, 2012 paper, 2023 preprint, rendered pages, measurement schema | external-chain specification populated | S00-S04 external-system batch and independent verifier passed | external-system sensitivity simulation approved; OM2 internal replica not approved |

## AZ-58 run-family reconciliation

- Early official RF deck: deterministic runaway around -10.8 MV; failed as a
  physical model and preserved.
- Removal/reduction of the guessed feedthrough branch isolated the instability
  but did not validate historical topology.
- Blain-derived topology variants initially diverged; successive one-variable
  behavioral limits produced a bounded diagnostic.
- Material and interconnect sensitivity runs completed.
- Full-startup cable representations completed without LTspice error:
  approximately 4.5945 MHz lumped, 4.6547 MHz ladder, and 4.6375 MHz ideal
  transmission line.
- The final immutable gate is
  `simulations/az58/gates/20260929-az58-rf-final-gate-v1`: all three controls
  passed independently, but their 57.9005 kHz carrier spread exceeded the
  primary ±20 kHz tolerance and none fell inside it. This approves sensitivity
  behavior while falsifying cable identification by carrier agreement.
- Unknown cable identity, nonlinear tube load, disputed retrospective topology,
  Wien-network connections, and behavioral tube validity still block complete
  historical approval.

## Stale-instruction finding

`RIFE_NEXT_STEPS.md` retains T0/T1 for history but now begins with the completed
3/3 status. Treat the older unchecked items as historical context, not current
execution instructions.

## Current verified next choice

The three-simulation phase is complete. Use
`evidence/THREE_BRANCH_SIMULATION_APPROVAL.md` as the controlling comparison
and `evidence/THREE_BRANCH_APPROVAL_MANIFEST.json` for exact authoritative
paths/hashes. The next step, only if authorized, is a low-voltage measurement
requirements sheet and documentary comparison. No further parameter tuning is
justified unless new branch-specific evidence changes a named assumption.
