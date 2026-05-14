# Cosmos-Transfer Research: Single-Dashcam Data Augmentation

Last updated: 2026-05-14

## Summary

For single dashcam augmentation, Cosmos-Transfer should be treated as a control-conditioned video-to-video domain adaptation system, not a generic text-to-video generator. The primary path is single-view `Cosmos-Transfer2.5-2B` with multi-control tuning around `edge`, `depth`, `seg`, and `vis`.

## Recommended Starting Workflow

1. Start from real dashcam RGB footage.
2. Run single-view inference with the general `Cosmos-Transfer2.5-2B` checkpoints.
3. Use a prompt to describe environmental changes such as weather, time of day, lighting, and road appearance.
4. Prefer multi-control conditioning rather than a single modality when output reliability matters.
5. Save the generated video together with the control configuration and original clip so downstream validation can trace provenance.

## Why This Is The Right Default

- NVIDIA's official product positioning describes Cosmos Transfer as a multicontrol model for simulation-to-photoreal transformation and synthetic data generation for AV training.
- The local repository README explicitly presents "Real 2 Real Augmentation" using dashcam footage as a first-class workflow.
- The local single-view inference path and JSON interface are the simplest supported public interface for real dashcam augmentation.

## Quality-Critical Tuning

### Control Roles

- `edge`: best for preserving structure, layout, and scene geometry.
- `depth`: best for 3D realism and perspective consistency.
- `seg`: best for semantic replacement and targeted structural edits, but risky alone.
- `vis`: best for preserving visual feel, lighting, and background appearance, but can collapse toward the original video if weighted too high.

### Practical Default

- Start near `guidance = 3`.
- Treat `seg + edge` as the core pair for controlled edits.
- Add `depth` when preserving perspective or road geometry matters.
- Use `vis` as a low-weight supplement rather than a dominant control.

### Known Failure Patterns

- Segmentation alone is not recommended for realistic outputs.
- `seg + vis` without `edge` is not recommended.
- Masking `vis` is explicitly discouraged because it can induce hallucinations.
- If the default edge extraction misses boundaries, pre-adjust brightness and contrast before edge generation.

## Reliability Guidance For Training Data

Cosmos-Transfer can preserve structure and motion well enough to make it useful for training-data multiplication, but safety-critical use should assume validation is mandatory. NVIDIA's simulator recipe claims preservation of anomaly behavior, trajectories, labels, and temporal consistency in its specific evaluation setup, but that should be treated as evidence for a workflow pattern rather than a blanket guarantee for arbitrary real dashcam augmentation.

## Model Selection Guidance

- Primary choice for this use case: `Cosmos-Transfer2.5-2B` single-view general checkpoints.
- Secondary reference only: `Cosmos-Transfer2.5-2B/auto` for AV-specialized or multiview workflows.
- Not the default for single dashcam augmentation: multiview world-scenario map control.

## Compute And Throughput Constraints

- Local docs list 65.4 GB VRAM for single-GPU inference on `Cosmos-Transfer2.5-2B`.
- Distilled edge inference is much faster, but it is limited to edge control and intended for short videos of strictly 93 sampled frames.
- Multiview and auto workflows require GPU count at least equal to active views, so they are not the first choice for single dashcam augmentation.

## Evidence Map

- Local repo README: `/workspace/README.md`
- Local single-view inference guide: `/workspace/docs/inference.md`
- Local auto/multiview guide: `/workspace/docs/inference_auto_multiview.md`
- Local world-scenario generation guide: `/workspace/docs/world_scenario_video_generation.md`
- Local interfaces: `/workspace/examples/inference.py`, `/workspace/cosmos_transfer2/inference.py`, `/workspace/cosmos_transfer2/config.py`
- NVIDIA product page: `https://www.nvidia.com/en-us/ai/cosmos/`
- Cosmos Cookbook control modalities: `https://nvidia-cosmos.github.io/cosmos-cookbook/core_concepts/control_modalities/overview.html`
- Cosmos Cookbook multi-control recipes: `https://nvidia-cosmos.github.io/cosmos-cookbook/recipes/inference/transfer2_5/inference-real-augmentation/inference.html`
- Cosmos Cookbook AV gallery: `https://nvidia-cosmos.github.io/cosmos-cookbook/gallery/av_inference.html`
- Cosmos Cookbook sim-to-real AV recipe: `https://nvidia-cosmos.github.io/cosmos-cookbook/recipes/inference/transfer2_5/inference-carla-sdg-augmentation/inference.html`
