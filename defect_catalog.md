# Defect Catalog — Generative Image QA

Common defects encountered during image generation testing.

---

## DEF-001 — Anatomical Distortion

**Description:** Incorrect number of fingers, merged limbs, broken proportions.
**Common cause:** Low steps, high CFG, weak base model.
**Severity:** Major
**Fix direction:** Increase steps to 25+, lower CFG to 7, add negative prompt: "deformed, extra fingers, bad anatomy"

---

## DEF-002 — Prompt Mismatch

**Description:** Generated image does not reflect key elements of the prompt.
**Common cause:** CFG too low, conflicting prompt elements.
**Severity:** Major
**Fix direction:** Raise CFG to 7–9, simplify prompt, move key elements to start.

---

## DEF-003 — Color Oversaturation

**Description:** Colors appear burned out, neon, or unrealistic.
**Common cause:** CFG above 12, certain samplers.
**Severity:** Minor / Major depending on use case
**Fix direction:** Reduce CFG to 8 or below, switch sampler to DPM++ 2M Karras.

---

## DEF-004 — Noise / Unfinished Texture

**Description:** Image looks grainy, blurry, or unrefined.
**Common cause:** Too few steps (under 15).
**Severity:** Minor
**Fix direction:** Increase steps to 20–25 minimum.

---

## DEF-005 — LoRA Style Bleed

**Description:** LoRA style applies to elements it shouldn't (background, objects).
**Common cause:** LoRA weight too high (above 0.9).
**Severity:** Minor
**Fix direction:** Reduce LoRA weight to 0.6–0.75, use targeted LoRA trigger words.

---

## DEF-006 — Face Deformation

**Description:** Face looks melted, asymmetric, or has multiple overlapping features.
**Common cause:** Low resolution, low steps, bad base model for portraits.
**Severity:** Critical for portrait use cases
**Fix direction:** Use face-focused upscaler, enable ADetailer, increase steps.
