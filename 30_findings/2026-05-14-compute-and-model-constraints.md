# Finding: Compute And Model Constraints Matter

## Finding

The fastest or most specialized Cosmos-Transfer paths are not interchangeable with the safest default for single dashcam augmentation. General single-view inference is heavier but broader; distilled edge is faster but constrained; multiview is specialized and GPU-hungry.

## Evidence

- Local inference docs list 65.4 GB VRAM for single-GPU `Cosmos-Transfer2.5-2B` inference.
- Local docs and code state that the distilled edge model is intended for short videos of strictly 93 sampled frames and requires `num_steps = 4`.
- Local auto/multiview docs require GPU count at least equal to active views.

## Impact

- Throughput planning and model selection should be made explicitly rather than treating all checkpoints as drop-in substitutes.
- For short-burst edge-preserving experiments, distilled edge may be useful.
- For general dashcam variation generation, the broader single-view path remains the safer baseline.

## Confidence

High for the documented constraints, because they come directly from local inference docs and config/code behavior.

## Operational Recommendation

Choose the model path based on required control types and clip length first, then optimize for speed only within those constraints.

## Reuse Trigger

Reread this when balancing quality, latency, and hardware availability.
