# Finding: Single-Dashcam Default Workflow

## Finding

For training-data multiplication from real dashcam footage, the correct default is single-view `Cosmos-Transfer2.5-2B` inference with multi-control conditioning, not multiview AV control or unconstrained prompt-only generation.

## Evidence

- Local README presents "Real 2 Real Augmentation" using dashcam footage.
- Local single-view inference docs provide the public JSON interface for RGB video plus control modalities.
- NVIDIA's Cosmos product page positions Cosmos Transfer as a synthetic data multiplier for AV environments and lighting changes.

## Impact

- Initial production experiments should target the general single-view checkpoints.
- Multiview and map-control should be treated as later extensions, not the baseline workflow.

## Confidence

High. This is supported consistently by the local README, local inference docs, and NVIDIA's public product positioning.

## Operational Recommendation

Start with single-view real-to-real specs and only escalate to AV-specialized multiview workflows if the data source or camera topology actually requires them.

## Reuse Trigger

Reread this when deciding which Cosmos-Transfer path to use for new AV augmentation work.
