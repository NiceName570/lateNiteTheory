# EVIDENCE REVIEW: Protocol Merit Assessment + Lin et al. 2025 Comparison

*Added: 2026-09-27 | Research session follow-up*

---

## PART 1: COMPARISON WITH Lin et al. 2025 (Science, DOI 10.1126/science.adp0176)

**Paper:** "Reactivation of mammalian regeneration by turning on an evolutionarily disabled genetic switch"
(Wei Wang Lab, NIBS Beijing, published 26-Jun-2025)

### Key finding
- Regenerative mammals (rabbits, spiny mice) activate **Aldh1a2** in wound-induced
  fibroblasts (WIFs) after injury -> produces **retinoic acid (RA)** -> RA signaling
  drives blastema-based regeneration.
- Lab mice/rats have the gene but its enhancer is evolutionarily "disconnected" --
  RA synthesis too weak, RA breakdown too fast.
- **Fixes that worked:** (a) rabbit enhancer transplanted to switch Aldh1a2 on in
  WIFs, or (b) **simply applying RA locally** -> mice regenerated ear tissue
  (cartilage, dermis, hair follicles, nerves) largely scar-free.

### Relationship to this folder's protocol

| | This protocol | Lin et al. 2025 |
|---|---|---|
| Paradigm | Epigenetic reprogramming (Guan 2022 barriers) | Endogenous program reactivation -- no reprogramming |
| RA/RAR role | Barrier 5 (1 of 7) | The sole, sufficient switch |
| Delivery | Systemic oral/sublingual | Local, at wound site |
| Cells | Dedifferentiation toward youth/pluripotency | Cells keep identity; injury-response only |

**Verdict:** Distant cousins. Shared node = RAR/RA signaling. The paper actually
*validates* Barrier 5 -- and argues it alone may suffice for regeneration, making
the other 6 barriers a *different project* (rejuvenation, not regeneration).

### CORRECTION to cocktail.txt (line 47)
"Carrot seed EO -> Carotenoids -> Vitamin A/RAR agonism" is **WRONG.**
Carrot seed *essential oil* is steam-distilled; carotenoids are non-volatile
pigments and do NOT survive distillation. Carrot seed EO is mostly carotol
(a sesquiterpene alcohol) with zero provitamin-A activity. The RAR link needs
preformed retinol/retinyl esters or actual dietary beta-carotene.

### Key lesson from the paper
RA is made **locally** by cells expressing Aldh1a2 -- the liver rations vitamin A
tightly. Oral carotenoids will NOT raise RA at a wound. Evolution needed only one
enhancer change to disable regeneration -> targeted/local delivery beats systemic.

---

## PART 2: LITERATURE SEARCH -- DOES THE PROTOCOL HAVE MERIT?

### PILLAR STRENGTH RANKING (strongest to weakest)

#### 1. ALPHA-KETOGLUTARATE (Part C) -- STRONGEST PILLAR
- **Chin et al. 2014, Nature 510:397** (PMID 24828042): alpha-KG extends lifespan
  (C. elegans) by inhibiting ATP synthase and TOR.
- **Asadi Shahmirzadi et al. 2020:** CaAKG extended mouse lifespan ~10% and
  compressed morbidity. REAL in-vivo mammalian data.
- **Carey et al. 2015, Nature (nature13981):** intracellular alpha-KG maintains ESC
  pluripotency -- supports the TET/demethylation mechanism directly.
- AKG also ameliorates age-related bone loss in mice (Nat Commun 2020).
- **Rejuvant (CaAKG + vitamins) study (PMC8660611):** avg **~8-year reduction** on
  TruAge DNA-methylation clock after ~7 months. (Caveats: not randomized, single
  vendor clock -- treat as preliminary.)

#### 2. SODIUM BUTYRATE (Part B) -- REAL MOLECULE, DOSE GAP
- Genuine pan-HDAC inhibitor; biochemistry not in dispute.
- In-vivo oral evidence EXISTS: oral butyrate inhibits hepatic HDAC3 -> induces
  FGF21 in mouse liver (PMC3314370); benefit in colitis/NASH models.
- **The gap:** plasma PK studies (e.g., PMID 10321503) show oral sodium butyrate
  is rapidly metabolized -- low micromolar plasma. In-vitro reprogramming
  chemistry uses **millimolar** culture-medium concentrations. Reprogramming-
  relevant intracellular [butyrate] in distant tissues orally = the protocol's
  biggest unproven leap.

#### 3. VITAMIN C + B12 COFACTORS -- SOLID CHEMISTRY, INDIRECT EVIDENCE
- Blaschke et al. 2013 (Nature): vitamin C is a TET cofactor; improves iPSC
  reprogramming quality -- Barrier 6's demethylation claim is real chemistry.
- Nat Metab 2023: B12 is a limiting factor for reprogramming in mice -- real.
- These are permissive cofactors, not drivers. Necessary but not sufficient.

#### 4. RESVERATROL -- WEAK IN-VIVO TRANSLATION
- **High absorption but VERY low bioavailability** (DMD 2004, 32(12):1377; later
  meta-analyses agree): rapid sulfation/glucuronidation -> free plasma resveratrol
  orders of magnitude below in-vitro effective concentrations for GSK3beta/Wnt.
- RCTs on hard endpoints have underwhelmed.
- As the stand-in for CHIR99021 (a precise GSK3beta inhibitor), this is the weakest
  substitution in the whole barrier map.

#### 5. ESSENTIAL OIL BLENDS (Part A) -- NO CREDIBLE MECHANISTIC SUPPORT
- No peer-reviewed evidence that sublingual mg-dose essential oils modulate
  JNK, ROCK, GSK3beta, or chromatin state in humans.
- Boswellic acids (the actual frankincense bioactive) are poorly absorbed and
  act on 5-LOX, not ROCK -- the "Y27632 substitute" mapping is not supported.
- Carrot seed EO contains no carotenoids (correction above).
- **Recommend dropping or demoting this layer in any evidence-weighted version.**

---

## PART 3: HUMAN EVIDENCE FOR SUPPLEMENT-DRIVEN EPIGENETIC AGE CHANGE

- **Fahy et al. 2019 (TRIIM, Aging Cell, PMC6826138):** rhGH + metformin + DHEA ->
  thymus regrowth + epigenetic age reversal (~1.5-3 yrs Horvath; later reanalysis
  claimed up to ~9 yrs). Drugs, not supplements -- but proves clocks can move in
  adults via systemic intervention.
- **Fitzgerald et al. 2021 (PMC8064200):** diet+lifestyle pilot -> ~3.3 yr Horvath
  clock reduction. Small, uncontrolled -- closest precedent to a "natural stack."
- **McGee et al. 2024 (GeroScience, s11357-024-01138-8):** combination nutritional
  supplement reduced DNA methylation age **only in older adults with raised
  epigenetic age** -- first strong-ish evidence a supplement blend can move a clock.
- **Polyphenol immune-age pilot (PMC11612904):** weak but directionally positive.
- **Bottom line:** moving a methylation clock via oral interventions is now
  *demonstrated but small; health-outcome benefit unproven.*

---

## PART 4: REVISED VERDICT

1. **Pillars are real molecules with real mechanisms** -- none are pseudoscience
   at the biochemistry level. AKG is the standout (genuine in-vivo lifespan data);
   butyrate/VitC/B12 have solid permissive-cofactor roles.
2. **The translation leap is the weak point** -- in-vitro iPSC chemistry runs at
   controlled mM/uM concentrations; oral supplements face bioavailability,
   first-pass metabolism, and local-vs-systemic gating. Lin 2025 is a pointed
   reminder that the body gates powerful programs locally.
3. **Drop or demote the essential-oil layer** -- no mechanistic or PK support.
4. **Make it falsifiable (fits IDEA.md's $5,000 budget):** before/after
   methylation clock (TruAge etc., ~$200-500/test) across a 6-12 month run of
   the AKG + butyrate + VitC + B12 stack. Optionally add CRP/IGF-1/metabolic
   panels. This converts the protocol from theory into data.

## NEW REFERENCES (from this review)
- Chin et al. 2014, Nature 510:397 (PMID 24828042) -- alpha-KG lifespan
- Asadi Shahmirzadi et al. 2020, Cell Metab 32(3) -- CaAKG lifespan/morbidity in mice
- PMC8660611 -- Rejuvant CaAKG TruAge study
- PMID 10321503 -- butyrate plasma PK, oral vs IV
- PMC3314370 -- oral butyrate -> hepatic HDAC3 -> FGF21
- Fahy et al. 2019, Aging Cell (PMC6826138) -- TRIIM trial
- Fitzgerald et al. 2021 (PMC8064200) -- diet/lifestyle clock pilot
- McGee et al. 2024, GeroScience -- supplement blend vs DNA methylation age
- Lin et al. 2025, Science -- DOI 10.1126/science.adp0176
