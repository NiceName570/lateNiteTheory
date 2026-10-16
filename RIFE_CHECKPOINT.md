# RIFE CHECKPOINT — resume point for the state-sync session

> **SUPERSEDED FOR ACTIVE WORK (2026-09-29):** this 2026-09-25 recovery list is
> retained as failure history. The three bounded simulation branches are now
> approved and independently verified. Resume from
> `evidence/THREE_BRANCH_SIMULATION_APPROVAL.md` and log §10.20.

Created: 2026-09-25, mid-session. Do not delete: when every item in §5–§8 is
done, append `CHECKPOINT [CONSUMED] — <date>` at the bottom. Durable facts
belong in RIFE_RESEARCH_LOG.md §7.13 (still PENDING — see §7 below).

## 1. Why this session exists
The 2026-09-24 evening session installed LTspice, fixed many netlist defects,
built tools/run_spice.py, and completed a first two-deck run at 21:17 — then
died (command timeout + WebSocket 1006) BEFORE writing its promised log
entry. RIFE_RESEARCH_LOG.md §7.12c therefore still claims "the netlist has
never been executed" — FALSE as of 2026-09-24 21:17. Job of this session:
(a) fix one harness window bug found on review, (b) regenerate stale
reports, (c) re-run, (d) append §7.13, (e) update RIFE_AGENT_START_HERE.md.

## 2. Verified on-disk facts (checked this session)
- Engine: C:\Users\crucial\AppData\Local\Programs\ADI\LTspice\LTspice.exe (26.1.1)
- First run 2026-09-24 21:17, both decks return code 0, 0 log errors.
  BACKED UP verbatim: simulations\az58\az58_spice_results_first_run_20260924_2117.txt
  - audio deck: 26779 points / 18 vars; rf deck: 10004 points / 4 vars
  - NEITHER deck oscillates (no zero crossings: bnd_sum, h116_3, h119_grid, h_tank_pl)
  - audio V(hv_bplus)=4100.69 V (+41.4 % vs Table I 2900): C_FEEDTHRU is
    removed in this deck, so the 812A draws no RF current — unloaded rail,
    near the model's capacitor-input estimate 4182 V (interpretation, flag it)
  - audio DC misses: V(h116_8) 227.93 vs 6.00 (+3698.9 %), V(h117_5) +113.3 %,
    V(h117_6) +176.7 % — but h117_6 was .ic-SEEDED at 290, so that reading is
    self-fulfilling, not independent evidence
  - rf V(hv_bplus)=2.17 V = harness artifact, see §3
- NOT a git repository — dated backup files are the only safety net.
- Files the next run will OVERWRITE: work\az58_audio.cir/.raw/.log,
  work\az58_rf.cir/.raw/.log, az58_spice_results.txt (first run is preserved
  in the backup above).

## 3. Diagnosis made this session (belongs in §7.13d/e)
RF deck save window `.tran 0.02u 2m 1.8m 0.02u` opened at 1.8 ms, BEFORE the
first 60 Hz quarter-cycle (4.17 ms) — the rail physically cannot be charged,
hence 2.17 V. The harness docstring itself requires late save windows; the
dead session shrank the window under timeout pressure and broke its own rule.
The earlier 9–10 ms full-netlist probe read hv_bplus 2532–2804 V (session
transcript only — not in any file; cite it as transcript evidence).
Fix applied: window → `.tran 0.02u 10m 9.8m 0.02u`, no .ic on the rf deck
(startup is the question that deck must answer unseeded).

## 4. DONE this session
- [x] Backup az58_spice_results_first_run_20260924_2117.txt (byte-identical copy of 21:17 results).
- [x] run_spice.py docstring lines 7–19 rewritten (real deck windows + quarter-cycle rule).
- [x] run_spice.py rf .tran 2m → 10m window fix applied (comment cites log 7.13d).
- [x] az58_netlist_check.py docstring now points to run_spice.py / LTspice (7.13a).
- [x] az58_waveform_model.py docstring + report banner: TOOLING LIMITATION → SCOPE.

## 5. PENDING — commands, in order
R1. `python simulations\az58\tools\az58_netlist_check.py`  → regenerates
    netlist_check_report.txt (footer must cite run_spice.py; expect PASS).
R2. `python simulations\az58\az58_waveform_model.py`  → regenerates
    az58_model_report.txt. DIFF key numbers vs previous report: must still be
    3183.1 / 636.6 / 318.3 / 63.7 / 31.8 Hz, 4.682 MHz, 41.0 pF, 3132 V,
    +8.0 %, 451–478 W. If ANY changed, the netlist moved under the model:
    log a dated reconciliation in §7.13; do NOT edit §7.12b.
R3. `python simulations/az58/tools/run_spice.py` (poll, don't block; expect
    ~5–20 s). New az58_spice_results.txt: rf deck should now show a LIVE
    rail (~2000–2900 V at 9.8–10 ms) and answer "does the Hartley start?" —
    that answer goes verbatim into §7.13e.

## 6. PENDING — §7.13 outline for RIFE_RESEARCH_LOG.md (append-only; NEVER
edit §7.12c/§7.12f — supersede them with dated corrections)
- 7.13a Engine acquisition: `winget install --id AnalogDevices.LTspice` →
  26.1.1 at %LOCALAPPDATA%\Programs\ADI. Probe failure preserved verbatim
  (tools/spice_engine_probe.txt): the probe searched winget only for
  "ngspice", got "No package found", and stopped instead of trying "LTspice"
  or a direct installer — that omission is the reason §7.12c is wrong.
- 7.13b Netlist defects exposed by EXECUTION (each fixed, each a lesson):
  missing Hartley feedback path (H_TANK_FB never reached the grid); floating
  band-network output; tank wired plate→chassis dead-shorted the HV rail
  (~1.5 A through the choke) → series feed rail→coil→plate; LTspice drops
  spaces around "=" in .param; subckt pins P/G/K collided with perveance
  parameter K; TITLE-LINE bug — LTspice discards line 1, so every generated
  deck silently lost its first .param (MU12AT7 undefined; the long bisection
  hunt only ended because hand-made probe files began with a comment line);
  singular matrix from two ideal primaries sharing LINE_HOT/COMMON → winding
  resistances; RT104 centre tap grounded (steps 44–47); one multi-winding K
  statement instead of three; three lines had lost "*" markers; C104 was
  modelled 100 nF grid→−60 V source = 0.34 Ω at 4.68 MHz, shorting the
  Hartley feedback (parts list says RF choke); C_C110B 10 µF τ≈24 ms through
  2.3 kΩ starved the audio B+ (44 V of 340 V at 10 ms).

- 7.13c Harness: two decks from one netlist (4.68 MHz forces ~10–20 ns steps
  → 60 ms ≈ 3M steps; audio deck drops C_FEEDTHRU, rf deck runs the complete
  circuit), .raw parser specs (UTF-16LE header, tab-separated Variables
  lines, point-major float64 time + float32 vars, 52 B/point strided, .op
  saved to its own file), results via numpy — not .meas.
- 7.13d FIRST run 2026-09-24 21:17 — transcribe ALL numbers verbatim from
  simulations\az58\az58_spice_results_first_run_20260924_2117.txt (audio:
  26779 pts, every node vs Table I, both period checks empty; rf: 10004 pts,
  hv_bplus 2.17 V = window artifact, both period checks empty).
- 7.13e Window fix (§3 above) + SECOND run 2026-09-25: audio IDENTICAL to
  run 1 (reproducibility ✓); rf now 11133 pts but
  V(hv_bplus) = **−10776048.41 V** [min −10923846 .. max −10621907], still
  no zero crossings on h119_grid / h_tank_pl. ISOLATION: rf deck differs
  from the stable audio deck only by C_FEEDTHRU being present → runaway
  enters through the RF feedback branch. −10.8 MV is physically impossible
  (105–125 V mains, ~3500 VAC secondaries) → solver/model artefact; mark
  that inference [R]. Also correlate: the transcript's early 9–10 ms probe
  (before the C104→RF-choke fix) read a healthy 2532–2804 V.
- 7.13f Establishes / open: §7.12c superseded (netlist HAS executed) — but
  executed ≠ correct: zero oscillation evidence in EITHER run, RF deck
  divergent, DC deviations large (h116_8 +3699 %, h117_5 +113 %, h117_6
  +177 % — seeded, therefore self-fulfilling, hv_bplus +41 % — unloaded
  deck). NO biological claim of any kind. Priority-ordered open items:
  (1) RF runaway — C_FEEDTHRU / C104 choke / feedback polarity after the
  series-feed change; (2) silent Wien despite settled rails; (3) DC vs
  Table I; (4) Pictorial C / View D + R107; (5) uncalibrated tube models.
- 7.13g Stale-text sweep = §4 list of this session; spice_engine_probe.txt
  left UNCHANGED as the failure record; reports regenerated (validator
  PASS; model report numbers IDENTICAL to §7.12b — no reconciliation owed).
- Process note: 13 editor calls failed this session on parameter names
  (file_path / old_string vs path / old_text); none changed a file — same
  precedent as §7.11a. Contract for existing-file edits: path + old_text +
  new_text.

## 7. STATUS at session end (2026-09-25)
- [x] §7.13 APPENDED to RIFE_RESEARCH_LOG.md (7.13a–g: engine correction,
  defect list, harness, both runs verbatim, window fix, −10.8 MV runaway +
  C_FEEDTHRU isolation, sweep, process note). Log line 2 date → 2026-09-25.
- [x] RIFE_AGENT_START_HERE.md: date, read order gains §§7.11–7.13, §8 item
  1 = debug the two simulation failures, §10 prompt updated, §4 file map
  gained CHECKPOINT + results-file rows.
- [x] R1/R2/R3 executed: validator REGENERATED (PASS, new footer); model
  report REGENERATED (numbers identical to §7.12b — no reconciliation);
  second run captured in az58_spice_results.txt (rf deck runaway −10.8 MV).

## 8. Open research state handed forward (whoever resumes)
1. RF deck diverges to ≈ −10.8 MV by 10 ms; isolation = C_FEEDTHRU branch
   (audio deck minus that single line is stable). First debug target.
2. Wien audio modulator silent at 50–60 ms despite healthy rails
   (V(h116_6)=305 V vs 290, V(h124)=308 V vs 290).
3. DC deltas vs Table I — remember the .ic-seeding caveat on h117_6.
4. Pictorial C / View D, R107 fixed-vs-pot, uncalibrated 6AQ5/812A models.
Commands (all seconds): python simulations\az58\tools\run_spice.py ·
python simulations\az58\tools\az58_netlist_check.py ·
python simulations\az58\az58_waveform_model.py
Evidence files to read first: RIFE_RESEARCH_LOG.md §7.13 ·
simulations\az58\az58_spice_results.txt ·
simulations\az58\az58_spice_results_first_run_20260924_2117.txt

CHECKPOINT [CONSUMED] — 2026-09-25
