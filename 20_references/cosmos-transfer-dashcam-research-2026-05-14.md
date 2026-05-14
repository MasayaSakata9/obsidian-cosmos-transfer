# Reference Set: Cosmos-Transfer Dashcam Research

Last updated: 2026-05-14

## Primary Sources

### Local Repository

- `/workspace/README.md`
  - Defines Transfer2.5 as a multi-controlnet for multiple video modalities.
  - Shows both sim-to-real and real-to-real workflows.
  - Separates general vs. AV-specialized model families.
- `/workspace/docs/inference.md`
  - Defines the public single-view inference interface.
  - Lists VRAM and inference-time constraints.
  - Documents mask support and distilled edge restrictions.
- `/workspace/docs/inference_auto_multiview.md`
  - Confirms multiview GPU requirements and active-view coupling.
- `/workspace/docs/world_scenario_video_generation.md`
  - Documents map-control generation for AV workflows.
- `/workspace/examples/inference.py`
  - Confirms the main single-view CLI entrypoint.
- `/workspace/cosmos_transfer2/inference.py`
  - Confirms multi-control inference loading, guardrail flow, and distilled-video restrictions.
- `/workspace/cosmos_transfer2/config.py`
  - Confirms public model variants, control weights, masks, guidance range, and default steps.

### NVIDIA Official

- https://www.nvidia.com/en-us/ai/cosmos/
  - Product positioning for AV synthetic data generation and environment/light variation.
- https://github.com/nvidia-cosmos/cosmos-transfer2.5
  - Official repository overview, model family, and release status.

### Cosmos Cookbook

- https://nvidia-cosmos.github.io/cosmos-cookbook/core_concepts/control_modalities/overview.html
  - Best-practice semantics for `edge`, `depth`, `seg`, `vis`, and masking caveats.
- https://nvidia-cosmos.github.io/cosmos-cookbook/recipes/inference/transfer2_5/inference-real-augmentation/inference.html
  - Recipe-level tuning guidance for real-world augmentation and multi-control workflows.
- https://nvidia-cosmos.github.io/cosmos-cookbook/gallery/av_inference.html
  - Dashcam-oriented AV examples with prompt and control-weight patterns.
- https://nvidia-cosmos.github.io/cosmos-cookbook/recipes/inference/transfer2_5/inference-carla-sdg-augmentation/inference.html
  - Reliability evidence for ground-truth preservation in a simulator-to-real validation setting.
- https://nvidia-cosmos.github.io/cosmos-cookbook/recipes/post_training/transfer2_5/av_world_scenario_maps/post_training.html
  - Context on when multiview world-scenario control matters and why it is a different workflow class.

## Cross-Check Summary

- The local README, product page, and Cookbook agree that Cosmos Transfer is intended for controlled augmentation rather than unconstrained generation.
- The local code and docs agree that single-view JSON-driven inference is the direct public path for dashcam augmentation.
- The Cookbook and AV gallery agree that multi-control tuning is the practical route to higher quality.
- The simulator recipe provides evidence for structure preservation, but it does not remove the need for downstream validation on real dashcam-derived samples.
