# Finding: Japanese Dashcam Tuning Strategy

## Finding

Japanese dashcam footage should first be handled with inference-time prompt/control tuning. Post-training should be reserved for repeated, measurable failures that remain after prompt and control sweeps.

## Evidence

- Local inference config supports prompt, guidance, control weights, edge/vis/depth/seg controls, masks, and on-the-fly control generation.
- Local post-training docs require substantial assets and 8x H100/A100 80GB for 2B single-view training.
- The main expected Japan-specific issues are domain-shift concerns rather than proof that the base model cannot work.

## Impact

- The first engineering milestone should be a Japanese dashcam inference benchmark, not model post-training.
- Dataset curation for post-training should start only after systematic failures are identified.

## Confidence

Medium-high. The model mechanics and post-training requirements are A-grade facts; the Japan-specific priority order is an operational inference.

## Operational Recommendation

Create a benchmark set covering Japanese road types, left-hand traffic, rain/night/tunnel scenes, and road markings; tune inference first; use post-training only if failures are repeatable.

## Reuse Trigger

Reread this when deciding whether to train a Japan-specific checkpoint.
