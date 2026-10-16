# Conversation Baseline Removal — Bible vs Stack

Date: 2026-10-16
Files analyzed: bible_kjv_082.wav, bible_kjv_117.wav, bible_kjv_123.wav (KJV spoken chapters, public domain LibriVox)

## Method

Built the 318.3 Hz stack (harmonics ×1–×12 with ±31.8 Hz sidebands). Compared every stack target against normal human conversation acoustic bands:

| Band | Hz range | Speech source |
|------|----------|---------------|
| F0 fundamental male | 80–180 | vocal fold vibration |
| F0 fundamental female | 160–260 | vocal fold vibration |
| F1 formant | 250–1000 | vowel first resonance |
| F2 formant | 600–2500 | vowel second resonance |
| F3 formant | 1500–3500 | vowel third resonance |
| Consonant noise | 1000–8000 | fricatives, stops, breath |

## Result: Every stack frequency is explained by conversation

| Stack freq | Explained by |
|------------|--------------|
| 286.5 | F1 formant |
| 318.3 | F1 formant |
| 350.1 | F1 formant |
| 604.8 | F1 formant |
| 636.6 | F1 formant |
| 668.4 | F1 formant |
| 923.1 | F1 formant |
| 954.9 | F1 formant |
| 986.7 | F1 formant |
| 1241.4–2259.9 | F2 formant |
| 2514.6–3214.8 | F3 formant |
| 3469.5–3851.4 | Consonant noise |

All Bible chapter FFT matches (top 30 per file) fell in explained bands. Zero unexplained matches.

## Interpretation

The Bible audio hits the stack because human speech naturally produces energy in F1/F2/F3 formant bands — not because of any special biblical encoding. Any spoken language, Bible or not, will produce the same pattern. The words themselves don't translate to anything unique in the math or frequencies beyond normal speech acoustics.

What remains: nothing from the Bible analysis. It is fully removed as relevant to the stack hypothesis, because generic conversation explains every hit.
