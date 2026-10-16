# Three-branch master map

Simulation-phase status (2026-09-29): **3 of 3 bounded branch packages
approved and independently verified.** See
`evidence/THREE_BRANCH_SIMULATION_APPROVAL.md` for the controlling approval
matrix and limitations. This status does not convert any branch into a complete
historical replica.

Established: 2026-09-29  
Status: working lineage map; branch membership is evidence-controlled

## Purpose

Reconstruct three electrical lineages independently, simulate each only after
its own evidence gate passes, and then compare functions—not copied values—to
rank bounded interpretations of missing AZ-58 details.

## Branch 1 — pre-Crane / Rife-Hoyland-Beam Rays

### Confirmed or located evidence groups

- Pre-1935 laboratory photographs show Colin B. Kennedy equipment.
- 1935 No. 4 settings and worksheet scans are located but not yet visually
  transcribed into this project.
- Milbank Johnson's October 15, 1935 letter refers to a Hoyland chart giving
  kilocycle frequencies, settings for two groups, and switch limits; the
  enclosure itself has not been located.
- May 1938 photographs show Rife, Hoyland, the No. 5 cabinet, and a flask-type
  plasma tube; no exact extant No. 5 instrument is currently identified.
- 1939 corporate/court material and a non-official trial manuscript survive;
  the official reporter transcript has not been located.
- A 1939 laboratory film is reported, but surviving presentations may combine
  original frames with later Crane narration or additions.
- Gables Laboratory reports, British shipment trails, and Gruner fonds are
  leads requiring document-level inspection.

### Devices/revisions requiring separate dossiers

1. Kennedy-assisted early laboratory arrangement(s), exact revision unknown.
2. No. 4 ray device, 1935.
3. No. 5 / Beam Rays-era device, 1938–1939.
4. Gruner device assembled circa 1942 from Milbank Johnson material.

The Scoon/Eico-377 machine is excluded as a 1938–1939 source because its audio
section indicates a 1950s-or-later construction. It may later receive a
transitional dossier, not a pre-Crane one.

### Simulation gate

No Branch-1 device is approved for simulation yet. Approval requires a bounded
functional topology identifying signal source, frequency-selection method,
carrier/modulation relationship, output coupling, and load. Unknown component
values may be ranged; unknown functional connections may not be silently
invented.

## Branch 2 — Crane/Thompson/Marsh/AZ-58

### Confirmed evidence groups

- June 18, 1958 San Diego Testing Laboratories report.
- August 1958 component/assembly drawing set, retrieved as an 11-page copy.
- Later Blain 2018 reconstruction/correction account, retained as tier [C].
- Preserved source netlist and full per-attempt LTspice run family.

### Current state

- Original source netlist is preserved with SHA-256
  `67178D93EA5103FAF37A45996D06E31644BCA06941F2A1DB465BD72505173BB2`.
- A separate corrected-topology diagnostic runs bounded under lumped,
  four-section ladder, and ideal transmission-line cable representations.
- These successful runs demonstrate numerical behavior of explicit
  reconstructions; they do not establish the missing historical wiring.

### Evidence blockers

- Pictorial C / View D are absent from the retrieved drawing copy.
- C114/C115 are resistance controls in the primary parts list, not the 250 pF
  capacitors used by the old audio model; actual Wien-network connections remain
  unresolved.
- C104 placement differs between the preserved reconstruction and Blain's later
  account.
- Output-lead length, construction, dielectric, loss, and shield termination are
  unknown.
- A historical nonlinear ray-tube load and locally validated tube models are
  unavailable.

### Simulation gate

Branch 2 has an approved **bounded diagnostic**, not an approved complete
historical simulation. Further frequency trimming is stopped until the branch
comparison and missing-source work constrain the topology and load.

## Branch 3 — James Bare engineering / Holland downstream use

### Confirmed primary patent families

- US 5,908,441 and US 6,221,094: audio/RF/plasma-tube architecture with tuned
  coax, RF amplification, and antenna tuning.
- US 8,269,571: later amplitude-modulated pulse transmitter.
- US 8,652,184: later resonant-frequency device with impedance matching,
  optional balun, short coax, and plasma ignition-state impedance change.

### Role boundary

Anthony Holland is placed downstream of Bare for the hardware discussed in his
TEDx account: Holland describes taking Bare's device into the laboratory to
search/test frequencies. Holland's experimental and presentation role is
preserved; it is not treated as an independent hardware-invention lineage
without separate primary evidence.

### Devices/revisions requiring separate dossiers

1. 1997/1999 `US5908441` architecture.
2. 1998/2001 continuation/family revision `US6221094`.
3. 2009/2012 AM pulse transmitter `US8269571`.
4. 2009/2014 matcher/balun/plasma architecture `US8652184`.
5. `BH-HOLLAND-OM2-2012`: documented OM2 prototype laboratory chain.
6. `BH-HOLLAND-EARLY-UNKNOWN`: first circa-2005 apparatus remains unidentified.

### Simulation gate

No Branch-3 simulation is approved yet. Patent figures, claims, component
relationships, and revision differences must first be extracted into device
dossiers. A patent-disclosed architecture may be simulated as disclosed; an
undocumented Holland laboratory configuration may not be synthesized from
multiple Bare revisions without an explicit variant label.

## Cross-branch comparison rule

Compare these functional categories only after branch dossiers exist:

| Category | Branch 1 | Branch 2 | Branch 3 |
|---|---|---|---|
| signal source | pending | partly documented | patent extraction pending |
| carrier | pending | 4,680 kc target documented | revision-specific |
| modulation | pending | audio/RF relationship incomplete | revision-specific |
| feedback | pending | disputed/reconstructed | patent extraction pending |
| output coupling | pending | shielded leads; details missing | tuner/coax/matcher disclosed |
| discharge load | flask/tube images; parameters missing | effective load only | ignition-state change disclosed |
| measurement method | pending | test report plus drawings | patent/test-report dependent |

Agreement does not prove inheritance. A preferred AZ-58 interpretation remains
`[R] triangulated reconstruction` unless contemporaneous evidence confirms it.
