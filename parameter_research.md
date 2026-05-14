# Parameter Research — ComfyUI

## CFG Scale (Classifier-Free Guidance)

Controls how strictly the model follows the text prompt.

| Value | Effect |
|-------|--------|
| 1–3 | Ignores prompt almost completely, very creative/random |
| 5–7 | Balanced — natural look, reasonable prompt adherence |
| 8–12 | Strong prompt adherence, can cause over-saturation |
| 13+ | Artifacts, distortion, unnatural colors |

**QA Note:** Values above 12 frequently cause defects. Recommended range: 6–9.

---

## Sampling Steps

How many iterations the model runs to refine the image.

| Steps | Effect |
|-------|--------|
| 10–15 | Fast but rough, visible noise |
| 20–30 | Good quality/speed balance |
| 40–50 | Diminishing returns, slower |
| 60+ | Rarely improves quality, wastes compute |

**QA Note:** 20–30 steps is the sweet spot for most use cases.

---

## Sampler

Algorithm used for the diffusion process.

| Sampler | Characteristic |
|---------|---------------|
| Euler | Fast, slightly rough edges |
| Euler a | More creative, less predictable |
| DPM++ 2M Karras | Sharp details, stable, good default |
| DDIM | Consistent results, good for testing |

**QA Note:** For reproducible QA testing, prefer DDIM or DPM++ 2M Karras.

---

## Denoise Strength (img2img / LoRA)

How much the model changes the input image.

| Value | Effect |
|-------|--------|
| 0.1–0.3 | Subtle change, preserves original |
| 0.4–0.6 | Balanced transformation |
| 0.7–0.9 | Heavy transformation, may lose original structure |
| 1.0 | Full regeneration, original ignored |

---

## LoRA Weight

Strength of a LoRA model applied on top of the base model.

| Weight | Effect |
|--------|--------|
| 0.3–0.5 | Subtle style influence |
| 0.6–0.8 | Clear style applied, usually safe |
| 0.9–1.0 | Strong influence, risk of artifacts |
| 1.0+ | Frequent defects, distortion |

**QA Note:** Test each LoRA at 0.5, 0.75, and 1.0 to find the safe range.
