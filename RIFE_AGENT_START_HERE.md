# RIFE AGENT START HERE — evidence-first continuity guide

Updated: 2026-09-29  
Workspace: `C:\Users\crucial\Desktop\rife machine`

**2026-09-30 pickup override:** Read `PROJECT_STATUS.md` and
`evidence/bare/BH_SP07_DECISION_REPORT.md` before older priorities below.
BH-SP07 now passed twice with independent verification; the next unfinished
stage is source-review of Claude's completed tube package in
`incoming/claude-2026-09-30-plasma-tube-rf-impedance/` and the visible explanation
of verified connected waveforms. Both the 44-case AC network and connected
transient checkpoints passed repeated independent checks and numerical
convergence. Read `evidence/bare/BH_SP08_TRANSIENT_DECISION_REPORT.md`.
The connected plasma-load prototype is incomplete; do not rerun earlier
failures or presume comparable measurements are Bare's tube values.

**Current simulation status:** 3 of 3 bounded branch packages are approved and
independently verified. Start with
`evidence/THREE_BRANCH_SIMULATION_APPROVAL.md` and
`evidence/THREE_BRANCH_APPROVAL_MANIFEST.json`; do not resume an older
simulation task list. The approved scopes are No. 4 normalized behavior, AZ-58
corrected-topology RF sensitivity, and OM2 external-system sensitivity. None is
a complete historical replica or biological validation.

**Read `RIFE_PROJECT_CHARTER.md` first.** As of 2026-09-29, the controlling
destination is a modular PC-controlled physical measurement prototype, with
simulation serving as a supporting tool, plus a parallel evidence-backed
YouTube reconstruction series. The user has substantial high-voltage,
low-current operator experience, but hazardous-voltage work remains a separately reviewed and
interlocked stage. The initial bench is not for human or animal exposure. See
`RIFE_RESEARCH_LOG.md` §10.

This is the current entry point for a fresh agent. It is a navigation and traceability layer, not a replacement for the evidence ledger. The authoritative record is `RIFE_RESEARCH_LOG.md`; do not rely on this guide alone for claims.

---

## 1. Mission

Research Royal Raymond Rife's original work in three tracks:

1. original microscopes;
2. patents and attempted patents;
3. original frequency-machine lineage: Rife Ray / Beam Ray / Beam Rays Inc. / later AZ-58.

The mechanism question is primary: identify what the documented devices actually did electrically and what a real modern device would need to measure, control, and prove before any biological mechanism is claimed.

---

## 2. Non-negotiable evidence rules

Source tiers:

- **[A]** government, patent, peer-reviewed, or institutional primary record.
- **[B]** contemporaneous dated document: engineering drawing, lab test, court/corporate record, dated newspaper, notebook, or report.
- **[C]** later testimony, retrospective, advocacy site, or secondary reconstruction. Keep flagged; do not promote to fact without primary corroboration.

Rules:

- Claims must trace to documents, not headlines.
- Preserve failures, dead links, OCR failures, and negative findings.
- The main log is append-only. Do not rewrite prior findings; add dated corrections/reconciliations.
- Separate electrical fact from biological interpretation.
- Do not claim organism-specific resonance, clinical efficacy, suppression, or a complete circuit unless the cited record directly establishes it.
- Log every action in `RIFE_RESEARCH_LOG.md`, including failed attempts.

---

## 3. Read order for a fresh agent

The completed three-simulation work (2026-09-29) is audited in:

1. `RIFE_PROJECT_CHARTER.md`, especially §§7–8;
2. `evidence/THREE_BRANCH_SIMULATION_APPROVAL.md`;
3. `evidence/THREE_BRANCH_APPROVAL_MANIFEST.json`;
4. `RIFE_RESEARCH_LOG.md` §§10.15–10.20;
5. `evidence/THREE_BRANCH_MASTER_MAP.md` and the applicable branch
   specification.

Do not resume the older AZ T0/T1 instructions as if they are unfinished. The
bounded RF diagnostic and final cable gate completed; the complete historical
AZ model remains unapproved. The next stage is a separately authorized
low-voltage measurement-requirements and documentary-comparison phase.

Read in this order before continuing research:

1. `RIFE_RESEARCH_LOG.md` §§0–1 — evidence rules and objective.
2. §3 — established claims, separated into microscope, device line, unverified [C], and contrary evidence.
3. §4 — patent index.
4. §§7.2 and 7.4 — Smithsonian 1944 report and verbatim microscope evidence.
5. §7.5 — rifevideos RF-versus-EMF thesis, still [C].
6. §7.7 — AZ-58 PDF source URLs and retrieval record.
7. §§7.8–7.10 — direct AZ-58 test/drawing transcription and current completeness note.
8. §§7.11–7.13 — structural validator, netlist build, and LTspice execution (§7.12c's "no engine" claim is superseded by §7.13).
9. §§8–9 — mechanism-first hypotheses and evidence standard for any build.
10. §5 and §7.6 — older open threads; use them with later reconciliations, because some have since been resolved.
11. `RIFE_HANDOFF.md` — historical handoff only; this START HERE file supersedes stale priorities in it.

---

## 4. File and evidence map

| Path | Role |
|---|---|
| `C:\Users\crucial\Desktop\rife machine\RIFE_AGENT_START_HERE.md` | Current fresh-agent navigation file |
| `C:\Users\crucial\Desktop\rife machine\RIFE_RESEARCH_LOG.md` | Authoritative append-only evidence ledger |
| `C:\Users\crucial\Desktop\rife machine\RIFE_HANDOFF.md` | Older handoff retained for context; not the current priority list |
| `C:\Users\crucial\Desktop\rife machine\evidence\az58\` | Durable local AZ-58 source PDFs, page renders, contact sheets, and working crops |
| `C:\Users\crucial\Desktop\rife machine\RIFE_CHECKPOINT.md` | Session resume checkpoint (state-sync session, 2026-09-25) |
| `C:\Users\crucial\Desktop\rife machine\RIFE_NEXT_STEPS.md` | Live "what still needs to be done" task list (T1–T10, test-by-test) |
| `C:\Users\crucial\Desktop\rife machine\simulations\az58\az58_spice_results.txt` | Latest LTspice run report; first run preserved as `az58_spice_results_first_run_20260924_2117.txt` |

AZ-58 local source files:

| File | Source/status |
|---|---|
| `evidence\az58\AZ-58-Electronic-Test.pdf` | June 1958 San Diego Testing Laboratories report; source URL in log §7.7 |
| `evidence\az58\AZ-58-Components-Assembly-Drawings.pdf` | August 1958 11-page drawing/assembly document; source URL in log §7.7 |
| `evidence\az58\AZ58-Revisited-Blain-2018.pdf` | Roger Blain 2018 technical overview; later analysis, not contemporaneous primary evidence |
| `evidence\az58\AZ-58-Components-Assembly-Drawings-p1.png` through `p11.png` | Rendered drawing pages |
| `evidence\az58\AZ-58-Electronic-Test-p1.png` | Rendered June 1958 test report |
| `evidence\az58\p6_table.png`, `p7_rot.png`, `p8_rot.png` | Working crops/rotations used for direct transcription |

`%TEMP%\rife_az58` was only a staging location and may disappear. Use `evidence\az58`. If evidence files are missing, re-download from the exact URLs preserved in log §7.7.

Current local tooling check: Python 3.12, PyMuPDF (`fitz`), Pillow, and pypdf are available. `pdftotext`, Tesseract, OCRmyPDF, ImageMagick, Ghostscript, and MuPDF CLI are not available. Windows `C:\Windows\System32\convert.exe` is not ImageMagick. Use Python/PyMuPDF/Pillow for page-11 rotation and crops, and log the exact command/script.

---

## 5. Traceability map — where each major claim lives

| Topic | Current evidence-backed position | Where to verify |
|---|---|---|
| Only granted Rife patent | US 1,727,618, microscope lamp, filed 1927, granted 1929; later cited by Bausch & Lomb and Swift | Log §3A item 1; §4; https://patents.google.com/patent/US1727618A |
| Second Rife/Thompson patent attempt | Application 512,326 filed 1955/continued 1956; no grant located | Log §3B item 10; §4 |
| Peer-reviewed microscope work | Kendall & Rife 1931; Rosenow 1932 used the Rife microscope | Log §3A items 2–3; PMC1658030 |
| Smithsonian microscope report | Smithsonian 1944 report recovered; strongest institutional microscope evidence, including 17,000× magnification/resolution wording | Log §§7.2, 7.4 |
| Beam Rays legal/corporate record | 1938 incorporation, 1939 litigation, 1940 suspension documented | Log §3B |
| 1934 La Jolla clinic claim | Still [C]; no primary record located | Log §3C |
| rifevideos RF-vs-EMF thesis | Useful lead, but advocacy/retrospective [C] | Log §7.5 |
| AZ-58 primary test | June 18, 1958: ~8.05–8.25 kV rms, 56–58 mA, ~463–467 W on serial 516M2 under stated tests | Log §7.8a |
| AZ-58 drawing specifications | 20–6,000 cps audio; 4,680 kc ±20 kc modulated carrier; <0.6% distortion; 350 W full/200 W input | Log §7.8b |
| AZ-58 architecture | 816 HV rectifiers; 812A output at ~2,900 VDC plate; low-voltage 12AT7/6AQ5/6X5GT control/audio; T106 ray tube with 10 kV shielded leads | Log §§7.9a–7.9i |
| 4.15 MHz versus 4.68 MHz | 4.68 MHz is the direct August 1958 drawing value [B]; 4.15 MHz is Blain/model-dependent retrospective detail [C] and must not be merged without model identity | Log §§3B, 7.8c, 7.11 |
| Biological mechanism | Not established by the inspected AZ-58 pages | Log §§7.8c, 7.9e, 7.9h–7.10 |
| Build hypotheses | Provisional only; evidence standard in log §§8–9 governs | Log §§8–9 |

---

## 6. AZ-58 page-by-page index

| PDF page | Content | Log entry | Status |
|---|---|---|---|
| 1 | Specifications and assembly notes | §7.8b | Read |
| 2 | Initial wiring instructions/designators | §7.8b | Read |
| 3 | Wiring steps 30–47 | §7.9g | Read |
| 4 | Assembly steps 10–17; wiring steps 18–29 | §7.9h | Read |
| 5 | Wiring steps 48–62; T106 ray-tube leads | §7.9i | Read |
| 6 | Table I socket/pin voltages | §7.9e | Read |
| 7 | Pictorial A, terminal designations | §7.9c | Read |
| 8 | Pictorial B, component layout | §7.9d | Read |
| 9 | Parts list, first page | §7.9a | Read |
| 10 | Parts list continuation | §7.9a | Read |
| 11 | Full schematic, dated 9 Aug 1958 | §7.9a | Read at overview level; node tracing open |

Important absence: the retrieved 11-page PDF references **Pictorial C** and **View D**, but neither appears in the retrieved sequence. Treat them as missing from this copy unless another source copy is found.

---

## 7. Current engineering synthesis — evidence-backed only

The August 1958 AZ-58 document describes a buildable high-voltage audio-modulated RF instrument:

- stated modulated carrier: **4,680 kc ±20 kc** [B];
- stated audio range: **20–6,000 cps in five ranges** [B];
- June 1958 tested output on one sample: approximately **8 kV rms, 56–58 mA, 463–467 W** [B];
- two RCA **816** rectifiers and an RCA **812A** output tube [B];
- Table I records approximately **2,900 VDC** at the 812A plate [B];
- low-voltage control/audio tubes: **12AT7, 6AQ5, 6X5GT** [B];
- output is to **T106, the ray tube**, through red/black H104 plugs and two wires specified as **10,000-volt shielded** [B].

This supports an audio-modulated, high-voltage RF plasma-tube architecture. It does **not** establish pathogen-specific resonance, clinical efficacy, or the mechanism of earlier Rife/Beam Ray devices.

---

## 8. Current open tasks, in priority order

**2026-09-29 controlling order:**

1. Branch 1: the five-run normalized No. 4 behavioral batch and its independent
   verifier passed. It is approved as a behavioral simulation, not a historical
   circuit replica; see log §§10.13-10.17.
2. Branch 3: translate Holland's documented procedure into common measurement
   fields, then review and implement the OM2-2012 external-system specification.
   Keep BH-2012 patent-internal topology separate from the OM2 external chain.
3. Branch 2: normalize AZ dossier/variant register and continue only primary-
   source comparison; do not resume arbitrary tuning.
4. Branch 1 is 1/3 approved. Approve Branches 2 and 3 only when each written
   gate and independent verification pass.

Detailed, test-by-test breakdown with hypotheses, commands, and success criteria: `RIFE_NEXT_STEPS.md`.

1. Continue only from the separate bounded corrected-topology diagnostic (log
   §§7.14n–7.14z); do not alter the preserved source netlist or reopen failed
   decks. Material controls show that the assumed shielded-lead capacitance is
   the dominant frequency sensitivity: 100 pF per lead moved the modeled
   carrier about -74.4 kHz. Identify cable construction/length if possible;
   otherwise keep it as a range and do not call it 50-ohm coax.
2. Keep the later Bare/Holland evidence branch separate. Bare's later patents
   explicitly use tuned coax, impedance matching, baluns, and plasma-antenna
   ignition states; Holland/Bare's later preprint uses a Phanotron, MFJ tuner,
   and 156–162 kHz pulsed fields. These are design clues, not AZ-58 component
   identifications. See `evidence/modern_bare_holland.md` and log §7.15.
3. Rebuild the audio Wien network before another audio run: the primary parts list calls C114/C115 25M/500M-ohm Midgetrol controls, while the old model incorrectly represented both as 250 pF capacitors. The 25 kΩ/500 kΩ reading is an explicitly preserved [R/C] assumption supported by Blain Figure 25, not a silent primary-source correction.
4. Search for the missing Pictorial C and View D.
5. Retrieve Ray #5 / Beam Ray schematic and the Hoyland 1939 trial transcript.
6. Cross-check Blain 2018 against primary pages without merging model identities.
7. Formalize test criteria/falsification conditions for H5/H6; the hypotheses themselves are already logged in log §8.1.
8. Keep unresolved: 1934 La Jolla clinic, 1953–54 fowl-leprosy record, Crane 1958–62 legal case, Hoyland patent search.

---

## 9. What a real device would need before any mechanism claim

Minimum measurements/controls: exact model/circuit identity; carrier and modulation frequency; waveform, duty cycle, phase, amplitude, harmonics; delivered voltage/current/power and load impedance; electrode/tube geometry, spacing, shielding, grounding, and coupling medium; calibration/drift logs; target temperature; sham, untreated, off-frequency, phase-randomized, carrier-only, modulation-only, and dose-response controls; biological markers and adverse effects; blinded independent replication; prospective clinical evidence before treatment claims.

---

## 10. Paste-ready prompt for a fresh agent

```text
You are resuming an evidence-only Rife research project.

Workspace: C:\Users\crucial\Desktop\rife machine

First read:
1. C:\Users\crucial\Desktop\rife machine\RIFE_AGENT_START_HERE.md
2. C:\Users\crucial\Desktop\rife machine\RIFE_RESEARCH_LOG.md sections 0–4, 7.2, 7.4, 7.5, 7.7–7.10, and 8–9.

Rules: preserve the append-only log, keep [A]/[B]/[C] source tiers, log failures as well as successes, and do not promote biological or historical claims beyond the cited documents.

Current next task: read log §7.14 first. Stop value tuning in the existing RF deck: its [R] placement of C104 in the grid return conflicts with Blain p.6/p.64 [C], which places C104 in the 812A plate feed. Trace primary wiring steps 30–60 and page-11 nodes around C101/C104/C105/H113/H114/H119/H120/H127/S107, then create a separate bounded diagnostic variant. The source netlist stays unchanged. Treat Pictorial C/View D as absent from the retrieved 11-page copy unless another source is found.
```

