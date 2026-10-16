# Three-branch simulation approval record

Established: 2026-09-29  
Status: **3 of 3 independently verified simulation packages approved within
their declared boundaries**

This record closes the three-simulation phase. “Approved” means the preserved
artifacts answer the bounded question stated by that branch's specification and
pass an independent verifier. It never means that missing historical circuitry
was recovered, that a physical machine was validated, or that a biological
claim was tested.

## Final approval matrix

| Branch | Authoritative package | Independent result | Approved claim | Explicitly not approved |
|---|---|---|---|---|
| 1 — pre-Crane / No. 4 | `simulations/pre_crane/runs/20260929-no4-behavioral-v1` | PASS, 5/5 | normalized No. 4 behavioral comparison | historical No. 4 circuit replica |
| 2 — Crane-era / AZ-58 | `simulations/az58/gates/20260929-az58-rf-final-gate-v1` | PASS, 3/3 | bounded corrected-topology AZ-58 RF sensitivity simulation | complete replica, audio/modulator, Pictorial-C wiring, cable identity, biological effect |
| 3 — Bare / Holland / OM2 | `simulations/bare/runs/20260929-om2-external-v3` | PASS, 5/5 | bounded OM2 external-system sensitivity simulation | OM2 internals, actual tuner, cable, plasma V-I curve, biological effect |

## Branch 1 — No. 4 behavioral package

Question: what distinguishes single-channel, simultaneous-linear,
sequential, and weakly nonlinear common-load interpretations of the two
surviving 1935 calibration values without inventing the machine?

Result:

- 760 kHz and 1.445 MHz single-source controls were recovered.
- Linear simultaneous output recovered both and placed its largest unexplained
  line at approximately -171.54 dBc, below the -60 dBc gate.
- The sequential alternative had nonoverlapping source windows.
- The declared weak cubic load produced all six predicted products: 75 kHz,
  2.130 MHz, 2.280 MHz, 2.965 MHz, 3.650 MHz, and 4.335 MHz.

Interpretation: several behaviors remain possible because waveform, amplitude,
phase, impedance, power, tube/load behavior, and exact group assignment are
not recovered. The package is useful precisely because those alternatives are
not collapsed into a fictional schematic.

## Branch 2 — AZ-58 RF sensitivity package

Question: does the correction-based RF diagnostic self-start and remain
bounded across three representations of the unidentified shielded output
leads, and how strongly does representation affect the carrier?

Result:

| Representation | Tank frequency | Error vs 4.680 MHz | Tank Vpp | Mean rail |
|---|---:|---:|---:|---:|
| lumped 100 pF/lead | 4.5969996 MHz | -83.0004 kHz | 10.8393 kV | 2933.86 V |
| four-section ladder | 4.6549002 MHz | -25.0998 kHz | 10.7679 kV | 2937.84 V |
| ideal 50-ohm/5 ns line | 4.6374696 MHz | -42.5304 kHz | 10.6952 kV | 2935.32 V |

All three unseeded startup runs passed the boundedness, period-count,
tank/grid-convergence, rail, and amplitude gates. The carrier spread was
57.9005 kHz, larger than the drawing's ±20 kHz tolerance. None of the three
assumption sets fell inside that tolerance.

Interpretation: the corrected-topology RF model is reproducibly runnable, but
frequency agreement cannot identify the historical cable. The unknown output
lead construction remains first-order. The audio/modulator remains outside the
approval because C114/C115 topology and missing Pictorial C/View D are still
unresolved.

## Branch 3 — OM2 external-system package

Question: what external behavior follows from the documented
F125→OM2→amplifier→tuner→helium-Phanotron chain without inventing OM2 internals?

Result:

- Holland's published table arithmetic passed first: 2.455% maximum table
  error and 0.589 dB maximum distance-trend difference.
- S00 recovered the declared -0.2/+2.2 overmodulated envelope factors.
- S01 separated the compressed peak to 0.613 of the linear bound and the
  bandwidth-limited RMS to 0.766 of the compressed trace.
- S02's ideal-match upper bound improved assumed 20/200-ohm load power by
  1.225x and 1.5625x.
- S03 separated explicit unlit/lit load-family terminal RMS by 1.132x.
- S04 separated assumed cable cases to 1.272x and 0.930x of the reference RMS.

Interpretation: Holland supplies the clearest external measurement method, but
not an internal OM2 reconstruction. The 160 kHz/50% pulse shape is labeled as
a later-revision baseline; the 2012 500 Hz-250 kHz and 50-70% capability range
is preserved separately.

## Cross-branch result

The three branches are not interchangeable implementations of one recovered
circuit:

- No. 4 is approved at the signal-behavior level because topology is absent.
- AZ-58 has a primary carrier/rail target and substantial circuit evidence, but
  missing wiring and output-lead details make a full historical replica
  non-identifiable.
- OM2 has the clearest external chain and procedure, but hides the transmitter,
  tuner, cable, and plasma internals.

The common, defensible observables are source/carrier, envelope or modulation,
linearity/compression, matching, load state, cable representation, terminal
voltage/current/power, and field geometry. The values remain branch-specific.
No Bare/Holland value was used to fill an AZ-58 or No. 4 gap.

The main triangulation finding is negative but useful: later explicit cable,
matching, and plasma methodology shows what must be measured, while the AZ-58
spread proves those variables cannot be guessed from carrier agreement alone.
This prevents retrograde tuning loops and defines the instrumentation fields
for any later low-voltage physical prototype.

## Reproducibility and custody

| Artifact | SHA-256 |
|---|---|
| No. 4 specification | `80FCF8AB325D25DC7082D1FA28AB97528078259FFD5999643C967B37EC17D826` |
| No. 4 runner | `B5C8C72671FB2FA8AEC27294A2782DE196D444A4D0966C91F0368CFCEC4B88D8` |
| No. 4 verifier | `F040192EC58DA55BAA55212EFDB230FD43FBB93E0BFF8BF58335012139865EF9` |
| No. 4 verification report | `B6F9DAD89854091A9BD539D401906381433A6647399CF20DC12F9DE58903C28E` |
| AZ-58 final specification | `96CD92740CF028E1B7E812A6AFAC8A41AB9CC9C596A57FA6BF07EABC01824A75` |
| AZ-58 preserved source netlist | `67178D93EA5103FAF37A45996D06E31644BCA06941F2A1DB465BD72505173BB2` |
| AZ-58 transform runner | `9D0AEE4780496C81EF28979070691507DC30B34986B9B099D9D812EC90FDBE2F` |
| AZ-58 gate runner | `53C5C70E0AFF054AD50E3D12A17DB77F99313239C904F2B060054168EECD3449` |
| AZ-58 verifier | `D607ACCAC9A2FBEF699EC2F03F30C69557FC19A1FF7A0160B0DEAC6B84B7CCEC` |
| AZ-58 verification report | `F62E17AFA07EF0FAED5EBC5C8A8822EE8D0A6C20EC47933442A62D06CE0618D4` |
| OM2 specification | `78371142313C526AF044D4AFBF57569C1EDDFD3C659E6A90FDA934C17AE067FD` |
| OM2 runner | `A26C0CAF9E8520B1E430D4ACB20CA78582FE241D14600E9AF77D2ABF295B656A` |
| OM2 verifier | `9B3572248B78BB29C952CED2FD3A931A89990A248511E431FAC1629C79A9CE78` |
| OM2 verification report | `92F44EE32E03D9200F757A2F269E12A358193B01F4304C06D12369A892B51281` |

The append-only decision/failure history is in `RIFE_RESEARCH_LOG.md` §§10.15,
10.17, 10.19, and 10.20. Superseded or failed attempts remain preserved; they
are not approval evidence.

