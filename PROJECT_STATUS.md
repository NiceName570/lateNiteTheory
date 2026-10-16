# Live Project Status

Updated: 2026-09-30 (BH-SP08 complete; Claude tube package received)

## Current state

`BH-SPP-001` is approved and frozen. `BH-SP00` through `BH-SP06` have passed
their authorized gates. The `BH-SP02..BH-SP06` decision core passed two full
repetitions, two independent verification passes, and repeat comparison. The
watchable CircuitJS explanation loaded successfully; its failed headless
capture attempts are retained separately. Design package `BH-SPP-002` is now
frozen with separate Bare-1999 and Bare-2014 plasma-antenna circuit branches.
`BH-SP07` is now PASS in two final repetitions, independently verified with
identical stored metrics. Four earlier development attempts remain preserved.
The full connected plasma-load prototype is not yet complete.

## Private repository backup

- Private GitHub repository:
  `https://github.com/LarryLangMui/rife-machine-research`
- Baseline commit: `ece9ab3336ece0613a561b7bdc214680e8a63694`.
- Branch: `main`; the first remote readback matched the local baseline commit.
- Large evidence is retained through Git LFS; reproducible simulator binaries,
  caches, and temporary renders remain excluded by the documented ignore rules.
- Publication details and every observed failure are recorded in
  `RIFE_RESEARCH_LOG.md` §10.50.

## Active gate

BH-SP08's AC subgate passed 44/44 fixtures in two identical repetitions with
independent complex V/I verification. Do not restart the completed SP07 gate.
Claude's finished tube research is present in
`incoming/claude-2026-09-30-plasma-tube-rf-impedance/`; source/figure validation
is the next gate before selecting tube-load parameters. Read
`evidence/bare/BH_SP08_AC_DECISION_REPORT.md` and the separate SP08 continuation.
40-artifact AC manifest SHA-256:
`95A4A69690BBFF7F930FA92F86D6E1F7A5857DD8F3C384C019A2CB68435B2217`.

Connected time-domain validation is under
`simulations/bare/BH-SP08_TRANSIENT_CONTINUATION.json` and its separate
`BH-SP08_TRAN_NUMERICAL_VARIANTS.json`.
The native lossy-line batch `20260930-bh-sp08-tran-v1-r1` timed out at 180 s;
its partial output is retained and is not a passed result. Equivalent 48-/96-
section distributed-RLC controls passed independent preflight, connected
waveforms and convergence. The accepted 96-section representation passed twice
with identical results. Maximum independent waveform error: 0.068146%; maximum
48-to-96 phasor difference: 0.165527%, power difference: 0.022953%.
Read `evidence/bare/BH_SP08_TRANSIENT_DECISION_REPORT.md`.
66-artifact transient seal SHA-256:
`DC6CD3355CD6DB49C31894379CB436CE0B8F72DACB0D4DF5C0ABDC92FDF1A856`.
Do not restart completed tests. Next: source-review Claude's incoming tube data
and produce a visible explanation from the verified connected waveforms.

- `BH-SP07`: PASS twice, two independent checks, exact repeated metric/deck
  comparison. Native LTspice power agrees with both raw readers within 0.5%.
- Report: `evidence/bare/BH_SP07_DECISION_REPORT.md`.
- Attempt index, repeat comparison and 90-artifact manifest:
  `simulations/bare/runs/20260930-bh-sp07-decision-v1/`.
- Manifest SHA-256:
  `D5974A77D1EDAB44E3BB29BC312FD5469EAD0F5CFBB3BE98C6D003C92562F4EF`.
- Final runs: `20260930-bh-sp07-v5-r1` and `20260930-bh-sp07-v5-r2`.
- BH-SP08 AC and connected transient passed repeated independent validation.
  BH-SP09 is not run. Spatial fields, physical hardware and biological testing
  remain excluded.

- `BH-SP00`: PASS, 27.120 MHz carrier baseline.
- `BH-SP01`: PASS, 26.960/27.120/27.280 MHz lines reconstruct one AM waveform.
- `BH-SP02..BH-SP06`: PASS 5/5 in both repetitions.
- Independent verifier: PASS 5/5 in both repetitions using a separate raw
  reader and SciPy periodogram method.
- Repeat comparison: PASS 5/5; zero reported metric difference at stored
  precision.
- Continuation record:
  `simulations/bare/BH-SPP-001_CORE_CONTINUATION.json`.
- Controlling decision report:
  `evidence/bare/BH_SP02_SP06_DECISION_REPORT.md`.
- Controlling artifact manifest:
  `simulations/bare/runs/20260930-bh-sideband-core-decision-v1/ARTIFACT_MANIFEST.json`.
- Artifact-manifest SHA-256:
  `03538292717AD8EB75CC92174A490FEA8CE4B181CA165CA55F553BB62AC01047`.
- Parked lead: the earlier patent's reflector and the later patent's close
  matcher-to-antenna requirement are now distinguished, but no field/distance
  simulation is authorized or justified from the available inputs.
- Design freeze: `simulations/bare/BH-SPP-002_FREEZE.json`, SHA-256
  `B32A8BEDFC10F0A69DD177E0C9853A7078241DCA40988FC307B74AD63AFE23D3`.

## Fixed boundaries

- Bare 1999 modified-CB embodiment is not the same as the Holland 2012 OM2.
- No AZ-58 or No. 4 values enter this run family.
- No physical CB modification, power-amplifier construction, tube energization,
  or biological exposure is authorized.
- LTspice/raw parsing is authoritative; Falstad follows as explanation.

## Latest integrity boundary

- Inventory rows: 2,074
- Inventory bytes: 1,338,595,995
- Inventory CSV SHA-256:
  `D25F93AEA87EE5CF321251D1F4E10C8B5FBDA6D9335FDD57B02665263F049F42`
- Proposal SHA-256:
  `BE45C8E794D341FCC19C0D06A26785E92915B96ED91BA4BB33BA33CFEAEF1821`

## Open blockers that are not part of this gate

- AZ-58 plate rail: approximately 950 V transformer-supported estimate versus
  2.9 kV Table-I/model value.
- AZ-58 Pictorial C and View D remain missing.
- No. 4 internal interconnection remains unidentified.
- Holland's early circa-2005 apparatus remains unidentified.
