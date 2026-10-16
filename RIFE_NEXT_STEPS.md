# RIFE NEXT STEPS — what still needs to be done

Updated: 2026-09-29 · Task layer derived from RIFE_RESEARCH_LOG.md §7.14n
and RIFE_AGENT_START_HERE.md §8. The LOG remains authoritative: findings
get appended there; this file is the live to-do and gets ticked/corrected
after each batch. Evidence rules apply without exception — see §6.

## ACTIVE PLAN — three independently gated simulations (2026-09-29)

**COMPLETED 2026-09-29:** all three bounded packages are independently
verified and approved within their explicit limits. No. 4 passed 5/5 as a
normalized behavioral simulation; OM2 passed 5/5 as an external-system
sensitivity simulation; AZ-58 passed 3/3 as a corrected-topology RF sensitivity
simulation. The authoritative matrix is
`evidence/THREE_BRANCH_SIMULATION_APPROVAL.md`; exact paths and report hashes
are in `evidence/THREE_BRANCH_APPROVAL_MANIFEST.json`. Do not reinterpret this
as approval of historical replicas or biological claims.

The next stage, if authorized, is to derive a low-voltage measurement bench
requirements sheet and documentary comparison from the shared observables.
New historical evidence should reopen only its affected branch under a new
versioned gate.

The controlling execution plan is now:

1. normalize evidence into the three branches defined in
   `evidence/THREE_BRANCH_MASTER_MAP.md`;
2. populate device dossiers using `evidence/DEVICE_DOSSIER_TEMPLATE.md`;
3. close the highest-value items in `evidence/PRIORITIZED_MISSING_SOURCES.md`;
4. approve and simulate one defensible device/revision per branch independently;
5. compare functions and rank AZ-58 variants under the charter's triangulation
   rule.

**Latest Branch-1 decision (2026-09-29):** the original Kennedy 110/525 and
220/525 instruction scans are now local, hashed, rendered, and inspected. The
110/220 are coupled-circuit regenerative receivers whose stock ranges remain
below about 2 MHz; the 525 is an audio-frequency amplifier. This rules out the
simple stock-Kennedy explanation for No. 4's Group 1 range to about 22.5 MHz.
Proceed to No. 4/Beam Rays-specific wiring, modification, or operating records.
If the prioritized search cannot recover one, define only a behavioral
simultaneous/sequential/heterodyne comparison and keep replica status rejected.
See `evidence/pre_crane/kennedy/KENNEDY_MANUAL_EXTRACTION.md` and log §10.13.

**Behavioral gate completion:** the preserved 1939 trial manuscript confirms that
1935 calibration values were transferred from an earlier machine using a
standard oscillator, while the 1936-38 master-oscillator/harmonic machines were
described as fundamentally different. Exact No. 4 circuitry remains unknown,
but `simulations/pre_crane/NO4_BEHAVIORAL_SIM_SPEC.md` has now been implemented.
Batch `20260929-no4-behavioral-v1` and its independent verifier passed all five
normalized single/simultaneous/sequential/nonlinear runs. Branch 1 is approved
as a behavioral simulation only, not a circuit replica. Next use Holland's
comparatively complete external methodology to define common observables and
the OM2 external-system model; that follow-on is now complete. See log
§§10.14-10.19.

**Branch-3 completion (2026-09-29):** Holland's published electrical tables
were independently recomputed first and passed the declared arithmetic gate
(2.46% maximum table error; 0.59 dB maximum distance-trend difference). The
authoritative `20260929-om2-external-v3` batch then completed S00-S04, and the
artifact verifier passed 5/5. Branch 3 is approved as a bounded OM2
external-system sensitivity simulation only. OM2 internals, tuner topology,
cable identity, and Phanotron V-I behavior remain unknown. The next active
simulation task was the Branch-2 AZ-58 final gate; it is now complete without
using the other branches as sources of missing AZ-58 values. See log
§§10.19-10.20 and `simulations/bare/OM2_2012_SYSTEM_SIM_SPEC.md`. The v1 and
v2 predecessors are retained but superseded because post-run specification
edits correctly invalidated their current-source hash checks. V3 uses the
final batch-neutral specification.

The detailed T0/T1 history below is retained because it explains earlier
choices, but it is no longer the immediate instruction: the bounded RF
diagnostic and three cable representations were completed and verified in the
2026-09-28 checkpoint. Do not resume value tuning from an older unchecked box.
The complete AZ-58 model remains unapproved for historical fidelity.

## Controlling destination added 2026-09-29

`RIFE_PROJECT_CHARTER.md` now controls the end goal: convert the evidence and
simulation work into a modular, PC-controlled physical measurement bench and a
parallel evidence-backed YouTube reconstruction series. Simulation is a design
and comparison tool, not the final product.

Before purchasing or wiring the first prototype, produce the Stage-1
requirements sheet: signals to generate, measurements to capture, instrument
and hardware limits, calibration fixtures, dummy loads, stop conditions, run
data schema, and the smallest low-voltage experiment that tests one specific
historical electrical claim. The user's high-voltage, low-current experience is
recorded, but hazardous-voltage work remains a later, separately reviewed stage.

## 1. PRIORITY 1 — Correct the reconstructed topology before more tuning

**Material/interconnect result (2026-09-28):** the bounded corrected-topology
diagnostic has now been swept with low/mid/high material corners and isolated
one-axis controls (log §§7.14u–7.14z). At the tested midpoint, 100 pF from each
shielded output lead to chassis shifted the carrier about -74.4 kHz, while
2 ohms total H120 RF loss shifted frequency only -80 Hz but reduced tank
amplitude about 3.3 percent. The exact shielded-lead construction and length
are therefore a first-order evidence gap. Do not relabel the primary wording
`10,000-volt shielded wires` as 50-ohm coax without a source.

**Current stop condition (2026-09-28):** no further C_FEEDTHRU or C104 value
sweeps in the present RF topology. Log §7.14n records a topology-level
contradiction: the current [R] netlist puts C104 in the 812A grid return, while
Blain p.6/p.64 [C] identifies it as the plate-feed choke to the anode top cap
and calls for breaking the C101–C104 and C104–C105 links. The source netlist is
preserved unchanged while this is re-derived.

**T0. Reconstruct and audit the RF nodes.**
- Trace primary wiring steps 30–60 and page-11 geometry for C101, C104, C105,
  H113, H114, H119, H120, H127, S107, the 812A grid pin, and its anode top cap.
- Compare that trace to Blain pp.55–66, but keep the Blain correction [C] and
  every inferred node [R]. Missing Pictorial C / View D still prevents a fully
  [B] connection claim.
- Build a separate diagnostic deck/runner variant; do not silently rewrite the
  preserved source model. Run it first in the short seeded window with a hard
  timeout and a unique durable attempt directory.
- Only when that variant stays physically bounded should it be copied to a
  separate visible-run directory and opened for the user to watch.

**T0A. Resolve output-lead construction before frequency trim.**
- Search priority is now explicitly pre-Crane. Start with the 1935 #4 settings
  and worksheet, 1935-1939 correspondence and experiment notes, May 1938 #5
  photographs, and the 1939 Beam Rays filings/trial exhibits. See log §7.18 and
  `evidence/pre_crane_source_search.md`. Later Crane/Scoon material is locator or
  comparison evidence only and cannot supply historical values silently.
- Search the primary drawing set, period parts sources, and photographs for
  the two T106 lead lengths, conductor size, dielectric, shield termination,
  and routing. Record absence as carefully as a positive identification.
- Until identified, sweep capacitance/loss as explicit ranges. Do not tune the
  tank capacitor to cancel an unknown cable value and then call the result a
  historical match.
- Keep the ray tube as an effective 139–147 kΩ sensitivity anchor only; add a
  nonlinear ignition/conduction model only when suitable V-I evidence exists.
- Resolve the possible wirewound matching element in the earth return. Blain
  p.64–65 [C] claims it from photographs but says it is absent from the parts
  list/schematic. The old deck's parallel R/L representation is not a faithful
  wirewound equivalent; log §7.14ab preserves parallel, series, and direct-wire
  controls. Do not choose among them without stronger device-specific evidence.
- Two distributed sensitivity representations now run bounded at the same
  midpoint total. The four-section ladder completed both short and full
  startup tests (log §§7.16–7.16b), moving the modeled carrier from 4.6023 to
  about 4.6547 MHz. The ideal tline-mid control also completed both tests
  (log §§7.17–7.17a), landing about 4.6375 MHz. Both have separate watchable
  copies. These are representation controls, not historical cable
  identifications; the lead construction/length evidence gap remains open.

**T0B. Keep the later Bare/Holland branch separate.**
- The modern patent record now supplies a useful design comparison: Bare's
  later systems explicitly use tuned coax, impedance matching, baluns, and
  plasma-on/plasma-off impedance changes. Holland/Bare's later preprint uses a
  Phanotron, custom RF amplifier, MFJ tuner, and 156–162 kHz pulse band.
- These are not AZ-58 component identifications. Do not import 27.12 MHz,
  18-foot coax, sub-one-foot coax, 156–162 kHz, or later plasma-tube values into
  the 1958 deck. If modeled, create a separate modern-architecture branch with
  its own source hashes and assumptions. See
  `evidence/modern_bare_holland.md` and log §7.15.
- Scope decision recorded in log §7.15a: use the modern work only to choose
  test categories and observables. Do not transfer its carrier frequencies,
  cable lengths, gas/tube values, or biological claims into AZ-58.

## 1A. PRIOR RF/audio questions retained for audit

Both decks have now run twice (log §7.13d/e); neither answered
"does it oscillate?". Everything else in Priority 1 depends on T1/T2.

**T1. Kill the RF-deck runaway (−10.8 MV).**
- Symptom: complete-circuit deck with `.tran 0.02u 10m 9.8m 0.02u` →
  V(hv_bplus) = −10 776 048 V by 10 ms; no crossings on h119_grid/h_tank_pl.
- Isolation: the audio deck is the same netlist minus ONE line
  (C_FEEDTHRU) and is stable at +4100 V → the instability enters through
  the C_FEEDTHRU feedback branch.
- Earlier hypotheses (superseded as the immediate action by T0):
  a) feedback polarity wrong after the series-feed change — grid must see
     the tank tap with correct phase; re-derive tap → grid against the
     812A grounded-grid arrangement;
  b) C104 as RF choke now creates a DC path that clamps the grid (choke
     toward the −60 V source would hard-hold it — check both ends);
  c) behavioural 812A model unstable at the loop's gain — temporarily
     reduce perveance K; if the runaway stops, the model is the limit,
     not the topology.
- Success = rail lands ~2000–2900 V at 9.8–10 ms AND a measurable period
  on V(h_tank_pl), or a documented proof the stage cannot start.

**T2. Rebuild the Wien modulator before another audio run.**
- Symptom: audio deck, settled rails (V(h116_6)=305 vs 290, V(h124)=308 vs
  290), save window 50–60 ms, band-1 network → zero crossings absent on
  both bnd_sum and h116_3 in BOTH runs.
- Stop condition: primary parts list names C114/C115 as 25M/500M ohm
  Midgetrol controls; the old model incorrectly made both 250 pF capacitors.
  Working reading 25 kΩ/500 kΩ is [R/C], supported by Blain Figure 25, which
  shows separate Cs/Cp capacitors. Rebuild that topology before testing loop
  gain or removing `.ic` seeds.
- Success = stable oscillation at 3183 Hz ±1 % on modelled band 1
  (matching §7.12b.1), or a documented reason the network cannot start.

**T3. Re-check DC against Table I — only after T1/T2 pass.**
- Open deltas (§7.13e): V(h116_8) 227.93 vs 6.00 (+3699 %) — pin-8
  identity suspect, verify the H116 socket pinout against Table I; 
  V(h117_5) +113 %; V(h117_6) +177 % — but that node was `.ic`-SEEDED at
  290, so its value is self-fulfilling and untestable until unseeded;
  V(hv_bplus) +41 % is expected while the deck is unloaded (no RF
  current) — re-evaluate ONLY with the RF deck stable and loaded.
- Rule: Table I is a LOADED measurement — compare like with like.

**T4. Tube models.**
- 6AQ5 and 812A parameters are literature-typical, unverified locally
  (12AT7 IS datasheet-cited). After T3, calibrate against Table I pin
  voltages; keep every value tagged [R] until it carries a citation.

## 2. PRIORITY 2 — Evidence gaps that block topology guesses

**T5. Pictorial C and View D are MISSING** from the retrieved 11-page
August 1958 drawings PDF (START_HERE §6). They would settle the audio arm
assignment, the modulation node, C114/C115 — and quite possibly T1/T2
outright. Search for another copy of the document (rife.org alternates,
archive.org, forum mirrors) before any further reconstruction is promoted.
Treat as absent from this copy unless another source is found.

**T6. R107: fixed resistor vs potentiometer.** Blain Fig. 25 shows a
~25 kΩ pot; 39 kΩ fixed reproduces Table I's 200 V at H116 pin 1. Resolve
from a primary document or keep it flagged in the netlist and in §6 of
`az58_modern_bom_cross_reference.md`.

**T7. Ray #5 / Beam Ray schematic + Hoyland 1939 trial transcript** —
still not retrieved; needs an external court-record/document search
(both were already on the old handoff's list and remain open).

**T8. Cross-check Blain 2018 against the primary pages** without merging
model identities — 4.15 MHz and 4.68 MHz are trim states of one tank
(§7.12b.3); keep that reconciliation explicit and never collapse two
models into one claim.

## 3. PRIORITY 3 — Long-running research threads

**T9. Formalize test criteria / falsification conditions for H5/H6**
(hypotheses themselves are logged in §8.1; the criteria that would
distinguish them are not yet written).

**T10. Keep unresolved until a primary record lands:** 1934 La Jolla
clinic [C], 1953–54 fowl-leprosy record, Crane 1958–62 legal case,
Hoyland patent search. Log failures and dead links alongside hits.

## 4. DEFINITELY DO NOT
- Do not claim oscillation, waveform agreement, or Table I validation
  before T1–T3 pass — §7.13f is explicit: executed ≠ correct.
- Do not produce or imply ANY biological result. Electrical fact ≠
  mechanism (log §0; repeated in §7.13f). No component joins a build
  without the full evidence chain in log §9.
- Do not edit prior log sections — append dated corrections only.
- Do not delete failures: probe files, dead links, and the preserved
  21:17 first-run numbers are all retained on purpose.

## 5. HANDOFF MECHANICS
- State files: `RIFE_RESEARCH_LOG.md` (authority) ·
  `RIFE_AGENT_START_HERE.md` (read order) · `RIFE_NEXT_STEPS.md` (this —
  live to-do) · `RIFE_CHECKPOINT.md` (2026-09-25 session, CONSUMED — start
  a fresh checkpoint next session) · `RIFE_HANDOFF.md` (historical only).
- Commands (all take seconds, run from the workspace root):
  `python simulations\az58\tools\run_spice.py` (LTspice 26 at
  %LOCALAPPDATA%\Programs\ADI) ·
  `python simulations\az58\tools\az58_netlist_check.py` (must stay PASS) ·
  `python simulations\az58\az58_waveform_model.py` (must reproduce the
  §7.12b numbers: 3183.1 Hz bands, 4.682 MHz, 3132 V, +8.0 %, 451–478 W).
- Loop after every batch: append findings to the log → tick/correct this
  file → refresh the checkpoint. Never leave a result only in chat — the
  2026-09-24 session died before writing its entry and cost a full
  re-derivation.

## 6. Evidence rules (from log §0 / START_HERE §2 — non-negotiable)
- Tiers: **[A]** government/peer-reviewed · **[B]** contemporaneous dated
  document · **[C]** later testimony — flagged, never promoted without
  primary corroboration.
- Claims trace to documents, not headlines. Separate electrical fact from
  biological interpretation. Preserve every failure, dead link, and
  negative finding.
