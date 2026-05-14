# Finding: Multi-Control Quality Rules

## Finding

High-quality dashcam augmentation depends on multi-control tuning. `edge` and `seg` are the main structural levers, `depth` helps preserve 3D consistency, and `vis` should usually be a low-weight supplement rather than a dominant control.

## Evidence

- Cookbook control-modality guidance states that multi-control tuning is required for high-fidelity, structurally consistent results.
- Cookbook guidance explicitly discourages segmentation-only use, `seg + vis` without `edge`, and masked `vis`.
- The AV gallery repeatedly shows weather and lighting variations using mixed control weights rather than a single control modality.

## Impact

- Prompt-only or single-modality runs are a poor default for safety-relevant training data.
- Quality reviews should inspect whether `vis` is too strong or whether edge extraction is too weak.

## Confidence

High for the qualitative guidance, because the Cookbook states these practices directly and the AV gallery uses mixed controls in examples.

## Operational Recommendation

Treat `edge + seg` as the first tuning surface, add `depth` when geometry matters, and keep `vis` low unless the output is drifting too far from plausible appearance.

## Reuse Trigger

Reread this when setting control weights or debugging low-realism outputs.
