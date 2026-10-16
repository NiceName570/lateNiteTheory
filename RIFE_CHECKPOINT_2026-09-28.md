# RIFE CHECKPOINT — simulation recovery session, 2026-09-28

> **CONSUMED FOR THE THREE-SIMULATION PHASE — 2026-09-29.** The bounded AZ-58
> RF work was promoted through a final immutable three-representation gate and
> independently verified. Resume from
> `evidence/THREE_BRANCH_SIMULATION_APPROVAL.md`; retain this file for its
> attempt/failure history.

Status: ACTIVE. This checkpoint exists so a simulator crash or disconnected
session does not erase the reasoning trail. Durable findings are appended to
`RIFE_RESEARCH_LOG.md` §7.14.

## User directive

Keep the detailed evidence-first log. Record every command, hypothesis, change,
run, timeout, failure, and result. The simulator has repeatedly choked; do not
run combined opaque jobs that can lose partial progress.

## Baseline

- Pre-repair snapshot:
  `simulations/az58/archive/20260928-131558_pre-repair/`
- Current official result before this session: audio deck silent; RF deck
  divergent at approximately -10.8 MV.
- No LTspice process was running at session start.
- Unrelated OpenWebUI Python processes were left untouched.

## New source finding

The August 1958 parts list identifies C114/C115 as 25 MΩ and 500 MΩ Midgetrol
adjustable controls. The current netlist models both as 250 pF capacitors. That
unsupported component-type conversion must be resolved before another audio
oscillator tuning run.

Assumption preserved for later review: the sheet literally says `25M ohms` and
`500M ohms`. Reading period `M` as thousand yields 25 kΩ and 500 kΩ; Blain's
later Figure 25 uses those exact kΩ values. Treat that conversion as [R/C], not
as a silent correction to the primary document, until a Mallory catalogue or
original-part measurement confirms it.

## Immediate work

1. Make `tools/run_spice.py` crash-resilient and one-deck-at-a-time.
2. Verify its write-ahead journal with a short smoke run.
3. Re-derive the audio network from the primary drawing; log uncertainty rather
   than forcing the old 250 pF model to oscillate.

## Compaction-safe resume state — 2026-09-28 after visible-window request

If chat context is compacted, resume here and then read `RIFE_RESEARCH_LOG.md`
§7.14. Do not repeat completed runs.

- Source netlist is intentionally still unchanged:
  SHA-256 `67178D93EA5103FAF37A45996D06E31644BCA06941F2A1DB465BD72505173BB2`.
- Pre-session files are preserved under
  `simulations/az58/archive/20260928-131558_pre-repair/`.
- Hardened runner requires exactly one mode (`--smoke`, `--deck audio`, or
  `--deck rf`), uses a unique `runs/<attempt-id>/` directory, fsyncs a
  write-ahead journal, atomically replaces only that attempt's report, records
  source/runner/deck hashes, catches timeout as a logged result, and never
  overwrites the old combined report unless explicitly promoted.
- Old combined report remains untouched; SHA-256
  `B6177573FD72E5967F5F28D6F86257C68411B4C3F8905773ADFD799C9ED95D4A`.
- C114/C115: primary sheet literally says `25M ohms` / `500M ohms` Midgetrol.
  Working interpretation 25 kΩ / 500 kΩ is [R/C], supported by Blain p.56
  Figure 25 labels `Rtot=25K` / `Rtot=500K`. Blain shows separate `Cs`/`Cp`
  capacitors at a reconstructed 250 pF. Never again model C114/C115 themselves
  as those capacitors; preserve the literal primary wording for later Mallory
  catalogue or original-part verification.
- Audio runs are PAUSED until that topology is corrected. Do not tune the old
  250 pF C114/C115 model merely to force oscillation.
- RF baseline with 100 pF C_FEEDTHRU deterministically diverges to
  -10,776,048.41 V. Removing only C_FEEDTHRU gives a stable unseeded 2822.48 V
  rail. Reducing only C_FEEDTHRU to 10 pF gives a stable 2808.50 V rail and
  real ~0.785 MHz oscillation (FFT and crossings), not 4.68 MHz.
- Current inference [R]: 100 pF is too strong for the guessed feedback nodes;
  10 pF prevents divergence but the loop is selecting another resonance. The
  2.5 mH C104 RF-choke value is also reconstructed and may be setting that
  resonance: scaling 2.5 mH to 100 µH predicts an upward frequency shift by
  approximately sqrt(25)=5 if the choke dominates. Next diagnostic should use
  the stable 10 pF deck as its control and change only L_C104 2.5 mH → 100 µH.
  This is a diagnostic value, not a proposed historical value.
- Visible LTspice PID at the last check: 9272, title
  `LTspice - [az58_rf_feedback-10p.cir]`. It contains the exact preserved 10 pF
  generated deck. The first visible launch failed because the path with spaces
  was unquoted; PID 16040 from that failed launch was closed and the quoted
  retry succeeded. Continue quoting all visible-launch paths.
- Batch attempt directories and authoritative results:
  - `20260928-1325_smoke-harness-v1` — Python journal-argument failure before
    LTspice; preserved and fixed.
  - `20260928-1330_smoke-harness-v2` — harness PASS, 0.922 s.
  - `20260928-1340_rf-baseline-durable-v1` — exact -10.776 MV reproduction.
  - `20260928-1350_rf-no-feedback-v1` — 2822.48 V stable control.
  - `20260928-1400_rf-feedback-10p-v1` — 2808.50 V, ~0.785 MHz stable.
- After every new attempt: inspect journal/log/raw, append full result and
  interpretation to log §7.14, update this checkpoint, then open the exact
  generated deck visibly with a fully quoted path. Keep manual/visible runs
  observational unless their outputs are separately captured and logged.

## Attempts

- `20260928-1325_smoke-harness-v1`: failed before LTspice launch with
  `TypeError: append_journal() got multiple values for argument 'path'`.
  Opening journal survived; official report untouched. Fix: rename the helper
  parameter only, then repeat the identical smoke test under a new attempt ID.
- `20260928-1330_smoke-harness-v2`: PASS. LTspice completed the independent RC
  deck in 0.922 s; raw parser read 1020 points / 2 variables; the full journal,
  deck, log, raw files, and atomic report are preserved under
  `simulations/az58/runs/20260928-1330_smoke-harness-v2/`. The previous official
  AZ-58 result hash is unchanged.
- `20260928-1340_rf-baseline-durable-v1`: completed in 4.390 s and exactly
  reproduced the old impossible -10,776,048.41 V rail with no RF crossings.
  Deterministic model failure; source hash unchanged; attempt fully preserved.
- `20260928-1350_rf-no-feedback-v1`: removed only generated-deck C_FEEDTHRU;
  completed in 4.844 s with an unseeded 2822.48 V rail (-2.7% vs Table I), no
  log errors and no oscillation. Runaway is isolated to the guessed feedback
  element or its guessed nodes/polarity, not the HV supply alone.
- `20260928-1400_rf-feedback-10p-v1`: stable at 2808.50 V and oscillating near
  0.785 MHz (confirmed by crossings and FFT), not 4.68 MHz. 100 pF runaway is
  coupling-sensitive, but 10 pF does not restore the documented carrier.
- `20260928-1430_rf-feedback-10p-c104-100u-v1`: timed out at 45.016 s. Log
  reached operating point, no error; raw file was zero bytes, so no circuit
  result exists. Runner now distinguishes an empty raw pathname from usable raw.
  Do not rerun the 10 ms form. Next: matched `--rf-window short-seeded` control
  (2.5 mH) and then 100 µH, each 0–200 µs.
- `20260928-1445_rf-feedback-10p-short-control-v1`: short seeded control PASS;
  0.516 s, stable 2797.47 V rail, ~0.855 MHz mode.
- `20260928-1450_rf-feedback-10p-c104-100u-short-v1`: LTspice returned but the
  model diverged to a -7.49 GV minimum. The predicted 5× frequency shift did
  not occur; C104-scaling hypothesis falsified. Do not open/reuse this unstable
  deck. Next: 2.5 mH restored, C_FEEDTHRU 1 pF, short-seeded window.
- `20260928-1500_rf-feedback-1p-short-v1`: process completed in 0.500 s and
  rail stayed at 2798.13 V, but the apparent approximately 2.08 MHz result was
  only a two-cycle startup ring. Grid amplitude decayed from a 0.648 V total
  span to exactly 0 Vpp in the final 50 microseconds; no sustained oscillation.
- Topology stop condition: Blain p.6/p.64 [C] places C104 as the plate-feed RF
  choke to the 812A anode top cap, while the current [R] netlist places it in
  the grid return. Blain also calls for breaking the C101–C104 and C104–C105
  links and connecting the point after C101 to grid pin 3. Stop tuning values
  in the present topology. Preserve the source unchanged; re-derive wiring and
  create a separate [C/R] diagnostic variant only after the node trace.
- Node trace completed across primary pages 3–5, 7–8, 11 and Blain pp.5–7,
  55–66. One `pdftoppm` command used invalid `-singlefile:$false` syntax and
  produced no pages; the corrected render produced pages 55–63 under
  `tmp/pdfs/blain-55-63/`. Runner now has isolated variant `blain-shunt-a`:
  C101 grid coupling, C104 plate-feed choke, C105 plate blocking, H120 split
  7/6/23 turns (Scenario A), and an explicitly diagnostic 4.68 MHz tank-cap
  assumption. Source netlist remains unchanged. Next action: syntax-check the
  runner, then run only `blain-shunt-a` / `short-seeded` with a hard timeout.
- `20260928-1530_rf-blain-shunt-a-short-v1`: completed in 0.657 s but diverged
  physically. Rail minimum -4.121 GV; RF nodes reached teravolts. The tank
  crossing detector did find 4.662 MHz, showing the selected L/C mode but not a
  valid oscillator. Never open this deck visibly.
- Active-model cause: unverified K812A=0.03 predicts about 6.6 A at the seeded
  2800 V/-60 V point. RCA's 812A Class-C peak point derives K812A=5.083e-4;
  350 W / 2900 V independently implies the same order. Next test changes only
  generated K812A to 5.08e-4; no grid clamp or bias change in that run.
- `20260928-1545_rf-blain-shunt-a-k508u-short-v1`: changing only K812A to
  5.08e-4 did not stabilize the loop; rail minimum -3.892 GV, tank mathematical
  mode 4.660 MHz. Perveance was not the sole fault. Next one-variable test adds
  generated positive grid current `max(Vgk,0)/3500` while retaining K=5.08e-4.
  Never display the failed deck.
- `20260928-1600_rf-blain-shunt-a-k508u-grid3k5-short-v1`: adding only the
  grid-current branch still diverged (rail minimum -3.405 GV); mathematical
  tank mode 4.660 MHz. Next one-variable test caps the 812A behavioral plate
  current at 0.8 A, near the RCA 0.692 A worked peak, while retaining K and the
  grid branch. Never display this failed deck.
- `20260928-1615_rf-blain-shunt-a-limited-short-v1`: first numerically bounded
  corrected-topology run; rail 2753.68–2800 V and sustained ~4.663 MHz. Not
  physically valid: final tank ~81.07 kVpp and grid ~19.73 kVpp at -5.494 kV
  mean. Do not display as success. Next one-variable test changes only the
  generated effective grid return 3 MΩ -> 3.3 kΩ, based on RCA/Blain scale;
  this is not a claim that primary designator R111 has that role.
- Material stop condition added at user request: all runs so far use ideal L/C,
  zero-ohm leads, and a fixed linear tube load. Do not claim amplitude. Primary
  only says 10 kV shielded wire, not 50-ohm coax. Model shielded-lead
  capacitance/loss as a range. B&W 3906-1 catalog confirms 2.5-inch, 8-TPI air
  coil stock but exact gauge/material is still open. June-test V/I implies only
  an effective 139–147 kΩ load range, not a proven linear resistance. Finish
  active-model bounding, then run a logged material/load sensitivity matrix.
- `20260928-1630_rf-blain-shunt-a-rgrid3k3-short-v1`: 3.3 kΩ effective grid
  return kept rail 2735–2800 V and sustained ~4.666 MHz, reducing tank from
  81.1 to 32.3 kVpp. Still invalid amplitude: grid peaks +3.06 kV. Final active
  bound is a soft grid-current knee above +150 V; after that, stop tube tuning
  and move to material/cable/load sensitivity.
- `20260928-1645_rf-blain-shunt-a-vgrid150-short-v1`: bounded 0.609 s run, rail
  2770.88–2800 V and final ~4.683 MHz. Tank 10.825 kVpp / 3.875 kV AC rms;
  grid 2.404 kVpp with +328 V peak. Safe for a separately copied visible
  diagnostic, but not validated: frequency uses assumed tank capacitance and
  material/cable/plasma losses are not yet included.
- Visible bounded copy launched as PID 12336 from
  `simulations/az58/visible/20260928-1645_bounded-diagnostic/` using `-run -big`.
  It reproduced rail 2770.8769–2800 V and 4,682,871.26 Hz / 10,824.51 Vpp in
  its own raw file, with no logged errors. This is the safe window to watch;
  batch record remains authoritative.
- Material corner runs all bounded: low `1700` final 4.6446 MHz / 10.886 kVpp;
  mid `1705` 4.6023 MHz / 10.798 kVpp; high `1710` 4.5807 MHz / 10.372 kVpp.
  Corners combine coil R, cable C, mica ESR, and 139–147 kΩ tube load, so they
  prove sensitivity but not attribution. A read-only comparison initially
  selected `.op.raw` and raised `KeyError: time`; corrected by excluding it.
  Next: one-axis mid controls for coil, cable, mica, and tube load.
- One-axis controls completed, all bounded/no errors. Baseline 4.682871 MHz.
  Coil 2 Ω (`1720`) = 4.682792 MHz and -3.3% tank amplitude; shielded lead
  100 pF each (`1725`) = 4.608428 MHz (-74.4 kHz); ray load 143 kΩ (`1730`)
  = 4.678578 MHz (-4.3 kHz); mica ESR (`1735`) = 4.683366 MHz. Cable
  capacitance dominates the frequency sensitivity in this model and exceeds
  the documented +/-20 kHz tolerance. Exact cable type/length is a priority
  evidence gap; do not call the primary wording 50-ohm coax.
- Visible material-aware midpoint copy launched as PID 14132 from
  `simulations/az58/visible/20260928-1705_material-mid/`. Its deck SHA-256
  matches the durable 1705 batch deck:
  `F56DF1061E0EC379B5777482E4726274CF5736B5415A7335FCC1A5502CCB9A65`.
  Independent parse reproduced 4.602341 MHz, 10.7979 kVpp tank, and
  2771.0757–2800 V rail; no failure text in the visible log. The README beside
  the deck records the 2-ohm H120, 100-pF/lead, 143-kilohm load, and mica-ESR
  assumptions and warns that the primary document does not identify 50-ohm
  coax.
- Earth-return mismatch found and isolated (log §7.14ab): the preserved deck
  described a wirewound matching resistor but represented its guessed 100-ohm
  resistance and 10-uH inductance in parallel. Source remains unchanged.
  Separate midpoint controls were bounded/no-error: same values in series
  (`1800`) = 4.603702 MHz / 10.7969 kVpp; direct-wire return (`1805`) =
  4.595382 MHz / 10.6719 kVpp, versus preserved parallel 4.602341 MHz /
  10.7979 kVpp. This topology ambiguity is secondary to the tested
  shielded-lead capacitance. Primary step 62 gives no cable length/type;
  Blain's earth-resistor claim is later [C] and says the part is absent from
  the primary parts list/schematic.
- Full 10 ms unseeded material-midpoint startup completed as attempt
  `20260928-1815_rf-material-mid-startup-10ms-v1` in 5.578 s, return 0, zero
  textual LTspice errors. Because `.tran` saves only 9.8–10.0 ms, the raw axis
  is relative 0–0.2 ms; corrected final-window parse gives 4.594513 MHz,
  10.8242 kVpp tank, 2.4173 kVpp grid, and rail 2865.16–3002.33 V. A first
  read-only parser check used the physical time against that relative axis and
  raised an empty-slice error; no file changed, and the corrected result is
  logged in §7.14ac.
- Visible full-startup copy launched as PID 2800 from
  `simulations/az58/visible/20260928-1815_material-mid-startup/`; its deck hash
  matches the 1815 batch deck
  (`906C9D9E7D784E75C18FF9503AC47A692103F391B1A74A746C181878928F237E`).
  Independent visible-raw parse matches 4.594513 MHz, 10.8242 kVpp tank,
  2.4173 kVpp grid, and 2865.16–3002.33 V rail; no visible-log failure text.
- Visible LTspice: first launch failed because the path with spaces was not
  quoted; failed session-launched PID 16040 closed. Quoted retry succeeded as
  PID 9272 with title `LTspice - [az58_rf_feedback-10p.cir]`.
- Added separate modern Bare/Holland evidence track in log §7.15 and
  `evidence/modern_bare_holland.md`. Bare's later patents explicitly document
  tuned coax, impedance matching, baluns, and plasma-on/plasma-off impedance;
  Holland/Bare's 2023 preprint documents a Phanotron, MFJ tuner, and 156–162
  kHz pulsed-field work. These are later design clues only. Do not import their
  carrier frequencies or component values into the AZ-58 deck. Bare patent text
  contains no `Rife` match; Holland's Rife/OPEF patent was not located, which is
  recorded as an unresolved search result rather than a negative proof.
- User confirmed the modern material is a separate perspective for insight,
  not a generation merge. Scope rule is logged in §7.15a: it may supply test
  categories (distributed cable, matcher, ignition-state impedance, coupling,
  modulation bandwidth), but no later carrier, cable length, gas/tube value, or
  biological claim may enter the AZ-58 model. Any such experiment must have a
  separate branch, hash, and assumptions.
- Added separate `--rf-cable ladder-mid` control (log §7.16). Four 50-ohm/5-ns-
  equivalent ladder sections, holding 100 pF total lead loading, completed
  bounded in 3.079 s with no errors: 4.655304 MHz, 10.7031 kVpp tank, rail
  2771.89–2800 V. The raw was denser (227,293 points) but usable. Next safe
  check is the 10 ms unseeded startup; historical cable identity remains open.
- Full unseeded ladder startup completed as attempt
  `20260928-1840_rf-material-mid-cable-ladder-startup-v1` in 28.344 s, return 0,
  zero textual errors. Corrected final parse gives 4.654654 MHz, 10.7679 kVpp
  tank, 2.3758 kVpp grid, and 2869.10–3006.15 V rail. It is bounded and may
  receive a separate visible copy; assumptions remain sensitivity-only.
- Visible ladder startup copy launched as PID 16736 from
  `simulations/az58/visible/20260928-1840_material-mid-cable-ladder-startup/`.
  The visible deck hash matches the 1840 batch deck
  (`DCB2A7427018FE056BFF0626B4A21CB0CFA53A60C27614D4A1ED510E1C935DE9`).
  Independent visible-raw parse matches 4.654654 MHz, 10.7679 kVpp tank, and
  2869.10–3006.15 V rail with no visible-log failure text. The first poll came
  before raw completion; follow-up verified responsive completion.
- Added a separately labeled ideal distributed-line control. Short tline-mid
  run `20260928-1850_rf-material-mid-cable-tline-v1` completed in 1.156 s,
  and full unseeded startup `20260928-1900_rf-material-mid-cable-tline-startup-v1`
  completed in 34.766 s, both return 0 with zero LTspice log errors. Full
  startup reports 4.6374696 MHz, 10.6952 kVpp tank, and 2867.17–3003.98 V rail;
  its distributed assumptions are ideal 50-ohm/5-ns line behavior plus 50-pF
  remote shunt per conductor, not historical identification.
- Visible tline startup copy launched as PID 9760 from
  `simulations/az58/visible/20260928-1900_material-mid-cable-tline-startup/`.
  The deck hash matches the batch deck
  (`3B5A509FD3FE49E32CD33DE88304C33C11A0D184AE08FBF58D8B7C7E1E35EDEB`).
  Visible raw parsing reproduces 90,261 points, 4.637469 MHz, 10,695.2 Vpp
  tank, and 2867.17–3003.98 V rail with no visible-log failure text.
- Final integrity pass: `az58_netlist_check.py` returned PASS with 0 structural
  errors; source hash remains
  `67178D93EA5103FAF37A45996D06E31644BCA06941F2A1DB465BD72505173BB2`; all
  visible logs scanned clean for failure keywords.
- An interactive reopen was attempted after the completed batch solve (PID
  15252), but the shell poll did not obtain a title and the process later
  disappeared; the user confirmed the window was closed. This is a UI/process
  lifecycle note only, not a simulation failure; the copied deck, README, raw,
  and log remain intact.
- Added `simulations/az58/visible/README.md` as a durable index for the three
  separately labeled watch copies and their bounded full-startup frequencies.
- User redirected evidence retrieval to the period before John Crane. First
  pass is logged in §7.18 and `evidence/pre_crane_source_search.md`: located
  1935 #4 settings/worksheet scans, pre-1940 correspondence/lab/court groups,
  May 1938 #5 photographs, and the official McGill Gruner fonds catalogue.
  No exact cable specification, plasma V-I curve, complete institutional
  schematic, or official 1939 reporter transcript was found. The supposedly
  1938-1939 Scoon machine is now excluded as a pre-Crane value source because
  its Eico 377 section dates it to about 1954 or later.
- Additional pre-Crane leads (log §7.18a): original Kennedy receiver manuals
  and surviving sets; the missing Hoyland enclosure named in Milbank Johnson's
  October 15, 1935 letter; original frames from the 1939 laboratory film;
  Siner/Gonin Gables reports; uncertain Couche/Low/Tully ownership chains; and
  period National/Piffard/RCA component catalogs. These are prioritized by how
  directly they can constrain circuit variables and by provenance quality.
- Bare/Holland lineage corrected in log §7.19 from Holland's own TEDx role
  description: Holland calls the hardware Bare's invention/device and describes
  taking it into the laboratory to search/test frequencies. Holland is now
  nested under the Bare engineering branch as tester/coauthor/presenter, not a
  parallel hardware-invention branch.

## End goal clarified — 2026-09-29

- `RIFE_PROJECT_CHARTER.md` now records the controlling destination: a small,
  modular, PC-controlled physical test platform using modern instruments and
  controls, with vintage components retained only when their physical behavior
  proves material.
- Simulation now explicitly supports hardware design and historical comparison;
  it is not the project endpoint.
- The user's substantial hands-on high-voltage, low-current experience,
  including MOT/capacitor experimentation, is recorded as operator context. It does
  not replace enclosure, grounding, discharge, interlock, and isolation design.
- A parallel evidence-backed YouTube series will reconstruct the historical
  timeline and show sources, assumptions, failed runs, corrections, and physical
  test results.
- The immediate engineering deliverable is the Stage-1 requirements sheet, not
  an unbounded high-power build. See research log §10.

## Three-simulation program progress — 2026-09-29

- First work-package audit completed. Workspace is not a Git repository; hashes,
  source copies, run directories, and append-only logs are the recovery chain.
- Created master branch map, works catalog, dossier template, current evidence
  inventory, and prioritized missing-source register under `evidence/`.
- Branch 1 No. 4 settings/worksheet, Johnson letter, and October/November 1935
  experiment notes are now local and hashed. The recovered settings are a
  high-confidence match to Johnson's referenced Hoyland enclosure/copy because
  fields and 760/1445/800-kc relationships agree.
- October test says No. 4 used a quartz tube and was set for rod and
  filter-passing values in one exposure. This supports a dual-setting functional
  inference but does not reveal mixing, waveform, or circuit topology.
- Branch 1 has now passed as a normalized behavioral simulation: LTspice batch
  `simulations/pre_crane/runs/20260929-no4-behavioral-v1` completed all five
  single/simultaneous/sequential/nonlinear runs and the independent artifact
  verifier passed 5/5. This does not approve a historical circuit replica.
- All four Bare patent PDFs are local and hashed. BH-2012 drawings are functional
  block diagrams, not a unique transistor schematic; exact replica simulation
  is unapproved.
- Holland's documented 2012 laboratory device is now identified as a Plasma
  Sonics OM2 prototype chain, not merely the 1999 CB-derived embodiment. The
  earliest circa-2005 apparatus remains unknown.
- Created separate specifications:
  `simulations/bare/BH2012_FUNCTIONAL_SIM_SPEC.md` and
  `simulations/bare/OM2_2012_SYSTEM_SIM_SPEC.md`. Neither is approved to run;
  they preserve the patent-internal versus OM2-external evidence boundary.
- AZ missing-record search found no Pictorial C/View D. Scribd has an 11-page
  `rife.org`-watermarked mirror candidate, the same page count as the local copy;
  it is not evidence of a more complete packet without page/hash comparison.
- Kennedy 110/525 (Sheet 110-E, 1923) and 220/525 (Bulletin 220-D, 1922)
  instruction scans are now local, fully hashed, rendered, and inspected. The
  110/220 are coupled-circuit regenerative receivers whose stock ranges remain
  below about 2 MHz; the 525 is an audio-frequency amplifier. They cannot, in
  stock form, explain No. 4 Group 1 reaching about 22.5 MHz or prove two
  simultaneous outputs. Full extraction and failed-render/bulk-image attempts
  are preserved in `evidence/pre_crane/kennedy/KENNEDY_MANUAL_EXTRACTION.md`.
- Live next choices: use Holland's procedure to define common measurements,
  implement and verify the OM2 external-system model, then normalize the AZ
  dossier/gate against the cross-branch findings. One of three simulations is
  now approved; do not claim the other two yet.

When the session is complete, append `CHECKPOINT [CONSUMED] — <date>`.
