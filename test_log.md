# Test Log

## Run #001
**Date:** 2025-05-14
**Prompt:** portrait of a young woman, soft lighting, warm tones
**Negative:** deformed, blurry, bad anatomy, extra fingers

| Parameter | Value |
|-----------|-------|
| Model | v1-5-pruned |
| Sampler | DPM++ 2M Karras |
| Steps | 20 |
| CFG | 7 |
| LoRA | none |

**Result:** Clean output. Natural skin tones. Minor noise in background.
**Defects found:** None critical. Background texture slightly rough (DEF-004).
**Verdict:** Pass

---

## Run #002
**Date:** 2025-05-14
**Prompt:** same as #001
**Change:** CFG raised to 14

| Parameter | Value |
|-----------|-------|
| CFG | 14 |
| Everything else | same as #001 |

**Result:** Colors oversaturated. Skin looks plastic.
**Defects found:** DEF-003 (color oversaturation)
**Verdict:** Fail — CFG above 12 not recommended

---

## Run #003
**Date:** 2025-05-14
**Prompt:** same as #001
**Change:** Steps reduced to 8

| Parameter | Value |
|-----------|-------|
| Steps | 8 |
| Everything else | same as #001 |

**Result:** Noisy output, unfinished texture on face.
**Defects found:** DEF-004 (noise / unfinished texture)
**Verdict:** Fail — minimum 20 steps recommended

---

## Run #004
**Date:** 2025-05-14
**Prompt:** same as #001
**Change:** LoRA added at weight 1.0

| Parameter | Value |
|-----------|-------|
| LoRA weight | 1.0 |
| Everything else | same as #001 |

**Result:** Strong style applied but background elements distorted.
**Defects found:** DEF-005 (LoRA style bleed)
**Verdict:** Partial pass — LoRA weight reduced to 0.7 in next run
