# HANDOFF — Rife machine research (historical handoff)

> **2026-09-29 completion notice:** the three-simulation phase is complete at
> 3/3 independently verified bounded packages. Use
> `evidence/THREE_BRANCH_SIMULATION_APPROVAL.md`, not the old task list below.
> The result does not approve complete replicas or biological claims.

> **Fresh agents:** start with `C:\Users\crucial\Desktop\rife machine\RIFE_AGENT_START_HERE.md`. That file is the current navigation/priority layer and points back into the authoritative append-only log. This older handoff is retained for historical context; where its task list conflicts with the START HERE file, use START HERE and the main log.

## What this project is
Evidence-only research into Royal Raymond Rife's ORIGINAL work, in 3 parts:
(a) his microscopes, (b) his patents, (c) the frequency-based machine
("beam ray" / Rife Ray -> Beam Rays Inc. -> AZ-58).

## Hard rules from the user
1. NO safe/hedged claims. Only claims that have EVIDENCE behind them —
   patents, court records, peer-reviewed papers, dated lab/engineering docs.
2. "If you're wondering why it didn't go through, don't look at the
   headlines": judge the suppression/rejection question from DOCUMENTS, and
   treat both promotional and debunking narratives as headlines until a
   record backs them.
3. Maintain RIFE_RESEARCH_LOG.md after every batch: append to section 2
   (search log), 3 (claims), 5 (open threads). Never delete failed attempts —
   the failure list saves the next model from repeating them.

## Files
- C:\Users\crucial\Desktop\rife machine\RIFE_RESEARCH_LOG.md  (full state)
- C:\Users\crucial\Desktop\rife machine\RIFE_HANDOFF.md        (this file)

## Already established (see LOG section 3 for full detail + sources)
- ONLY granted Rife patent: US 1,727,618 (microscope lamp, 1929),
  full text obtained, later cited by Bausch & Lomb + Swift Instruments.
- Second filing (Rife & Thompson app. 512,326, 1955/56): NO grant.
- Peer-reviewed: Kendall & Rife 1931 (Calif West Med, PMC1658030);
  Rosenow (Mayo) used the Rife microscope in Science 1932;
  Seidel & Winter "The New Microscopes," J Franklin Inst Feb 1944,
  reprinted by Smithsonian 1945; Smithsonian Annual Report 1944 p.207ff.
- Contemporaneous magnification claim = 17,000x (NYT 1931-11-22), not 31,000x.
- Frequency machine engineering: Hoyland #5 (photo May 1938); Beam Rays Inc.
  (CA incorporation 1938-06-01, state suspension 1940-01-06); full 1939
  court records (Hoyland v. Beam Rays — judgment 1939-12-06; London
  Blewett/Gonin/Parsons $28,000 suit citing "defects in that machine").
- MOR lab notebooks (late 1920s-1932), #4 device frequency charts (1935),
  Gables Lab reports (1939), AZ-58: 6 models 1953-57, 4.15 MHz Hartley
  carrier + 50 Hz-6 kHz square-wave audio (Blain dating), Stafford clinical
  reports 1957/1963.

## The NEXT 8 tasks (in priority order)
1. Smithsonian 1944 Annual Report p.207ff VERBATIM — old link 404s; search
   HathiTrust + Smithsonian Libraries; log the exact quote.
2. Kendall-Rife 1931 full text: PDF at PMC (scan, needs OCR).
3. Capture real PDF hrefs from rife.org (fetch strips links; format=json
   failed): target docs = "AZ-58 Revisited", AZ-58 drawings, trial
   transcripts, correspondence 1929-1934. Try search engines with
   site:rife.org queries, or Mojeek/Startpage.
4. The 1934 La Jolla clinic — currently [C] unverified. Confirm via
   correspondence 1929-1934 / 1935-1936 or downgrade permanently.
5. 1953-54 fowl leprosy experiment — find primary record; also fetch
   https://rifevideos.com/chapter_14_life_labs_1950s_pad_instrument_without_ray_tube.html
   https://rifevideos.com/chapter_24_dr_rifes_rf_method_or_the_emf_method.html
6. 1958-62 Crane legal case — absent from rife.org court-cases (only 1939
   cases there). Needs external court-record search.
7. Fetch rife.org/microscope-optics-blueprints (Rife+Crane-signed optical
   drawings), /laboratory-pictures, /more-resources.
8. Google/FreePatentsOnline search: any patent filed by Philip HOYLAND.

## Tooling gotchas (learned the hard way this session)
- fetch_web_content: reliable; pass requests[] {url, prompt}. Long content
  gets middle-truncated ~50k chars — prefer MediaWiki API wikitext.
- web_search: FAILED all session (parameter serialization issue) — retry
  carefully or route queries through fetch_web_content.
- Search engines: DuckDuckGo = bot challenge. Bing = ignores long queries;
  use short / site: queries. Mojeek/Startpage untested — try them.
- rife.org = Squarespace; content text OK, hrefs stripped, ?format=json
  useless (empty mainContent).
- Wikipedia: /w/api.php?action=parse&page=Royal_Rife&section=N&prop=wikitext
  (section 1 = Life and work, 2 = health fraud, refs at 5).

## Definition of done
A cited report where every claim has a source + tier, covering: the 5
microscopes + patent(s); the full frequency-device lineage with real
circuit values; court records; and a document-based explanation of the
venture's actual failure points — with anything unverifiable clearly
marked [C].

## PROGRESS UPDATE — 2026-09-24 session 2 (read this first)
- TASK 1 DONE: Smithsonian 1944 verbatim text EXTRACTED. The old library.si.edu URL is dead; use
  https://archive.org/details/in.ernet.dli.2015.279589
  OCR text: https://archive.org/download/in.ernet.dli.2015.279589/2015.279589.Annual-Report_djvu.txt (1.25 MB)
  It contains the FULL "The New Microscopes" article by E.E. Seidel & M. Elizabeth Winter, pp. 195-220,
  Rife section pp. 207-215, with plates. Verbatim quotes are in LOG section 7.4b.
  TO RE-EXTRACT: download the djvu.txt, then grep locally:
  Select-String -Path <file> -Pattern 'Rife' -Context 2,25
- BIGGEST NEW FACT: 17,000 diameters is stated as magnification AND RESOLUTION (p.210), on the same
  smaller Rife scope used with Kendall in 1931; plus full engineering specs (5,682 parts, NA 1.40,
  40/100 TPI, glycerine post, 200 lb, 24 in tall, fine adjust 700x more sensitive).
- Wikipedia's "reprinted 1945" note is wrong/secondary: the article is IN the 1944 report itself.
- TASK 5 PARTIAL: rifevideos ch.14 + ch.24 fetched; their RF-carrier vs EMF/contact-pad thesis is
  logged in LOG 7.5 as [C] (advocacy source) — must be cross-checked against the Hoyland 1939 trial
  transcript / Ray #5 schematic / 1958 AZ-58 test report before promotion.
- Wikipedia refs fully recovered (LOG 7.3) incl. Popular Science June 1931 profile (Rife's own
  "medical fakers" quote) and the Daily Californian 1971 obituary reprint URL.
- STILL OPEN: the complete Zeiss graticule comparison has now been extracted into LOG 7.6f-7.6i (done); it
  supports clean high-magnification viewing but does not independently calculate 17,000x resolution.
  Other open items: PDF recovery from rife.org; 1934 La Jolla clinic; fowl leprosy; Crane 1958-62 case;
  Hoyland patent search; primary cross-check of RF-versus-contact-pad claims.
- AZ-58 PDFs RETRIEVED (LOG 7.7): June 1958 electronic test, August 1958 components/assembly/drawings,
  and Blain's July 2018 technical overview. They are image-only scans; current environment lacks OCR,
  so circuit values and measured results remain unverified. Next action is OCR/visual transcription
  before making any engineering claim.

## BUILD OBJECTIVE (read before continuing)
The purpose is now mechanism-first: gather evidence to decide what a useful, personalized system could contain. Do not assume that Rife's name, a copied circuit, a single frequency, or a shared endpoint proves a mechanism. Track competing hypotheses and the measurements that would distinguish them.

Minimum evidence needed for any proposed component:
- primary engineering record with delivered frequency/waveform/phase/amplitude/power and model identity;
- controlled biological or tissue experiment with calibrated target delivery;
- sham, untreated, heat/force/chemistry-only, dose-response, phase-randomized, and off-target controls;
- intermediate biological markers and adverse-effect measurements;
- independent apparatus and result replication;
- prospective clinical evidence before treatment claims.

Current immediate action: OCR or visually transcribe the AZ-58 June 1958 electronic test and August 1958 assembly/circuit drawings. The three PDFs are already downloaded locally; they are image-only scans and no circuit value has been promoted to fact. Then compare the primary records with Blain's 2018 analysis and any Ray #5/Beam Ray schematic. Keep the mechanism matrix in LOG section 9 current; do not erase earlier hypotheses or failed retrievals.





## AZ-58 PRIMARY-RECORD UPDATE (2026-09-24)
Task 1 is substantially complete for the June 1958 test report and first two pages of the August 1958 assembly document. See LOG §7.8 for the direct visual transcription.

Verified primary values:
- June 18, 1958 San Diego Testing Laboratories report, lab SD13-2084M, Allied Industries, samples 516M1/516M2.
- Measured audio bands: 66–237 cps; to 1,176 cps; to 5,664 cps (lower endpoints for later bands unresolved).
- Lead insulation breakdown: 15,000 V rms at 60 cps.
- Output tests on 516M2: 8,250 V / 56 mA / 463 W; 8,050 V / 58 mA / 467 W; 8,175 V / 57 mA / 465 W.
- August 1958 drawing page 1: 20–6,000 cps in five ranges; 4,680 kc ±20 kc modulated carrier; distortion <0.6% ±50 cps; 350 W full to 200 W input; 105–125 V, 60 Hz; 4 7/8 × 2 9/16 × 13 in.
- Assembly instructions and component designators are recorded in LOG §7.8. Pictorials A–C/topology remain unresolved.

IMPORTANT RECONCILIATION: earlier 4.15 MHz / 50 Hz–6 kHz figures are Blain-derived/provisional; the 1958 primary drawing explicitly says 4.68 MHz ±20 kc. Do not merge these without identifying the model. The primary test establishes substantial high-voltage power, not biological efficacy.

Next evidence targets: Pictorials A–C, all remaining AZ-58 drawing pages, Ray #5/Beam Ray schematics, and the Hoyland 1939 trial transcript. The mechanism-selection framework remains a research hypothesis, not a finding.
