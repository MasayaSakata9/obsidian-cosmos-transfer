# Cosmos-Transfer2.5 Model Capabilities And Limits

Last updated: 2026-05-14

## Core Capability

Cosmos-Transfer2.5 is a control-conditioned world-to-world generation system. It can generate photorealistic videos from text plus one or more spatial/video controls such as Canny edge, blurred RGB, segmentation, and depth.

Reliability: `A`, verified by NVIDIA Docs, Hugging Face model card, official GitHub/local code, and NVIDIA Research.

## Public Model Paths

- `Cosmos-Transfer2.5-2B`: general checkpoint for Physical AI and robotics; minimum 1 GPU; documented VRAM requirement is 65.4 GB for single-GPU inference.
- `Cosmos-Transfer2.5-2B Auto`: specialized AV checkpoint; documented minimum is 8 GPUs.
- `Cosmos-Transfer2.5-2B/auto/multiview`: AV multiview workflow using seven world-scenario control videos.

Reliability: `A`, verified by NVIDIA Docs model matrix and Hugging Face model card.

## Input And Output Shape

- General model: text prompt plus up to four control input videos: edge, blurred RGB/vis, segmentation, and depth.
- Automatic extraction is available for edge and blur/vis when only RGB video is provided.
- Hugging Face model card states the general model produces 720p video at 16 FPS.
- Auto/multiview model uses seven camera views and world-scenario controls, producing view-consistent multiview frames.

Reliability: `A`, verified by Hugging Face model card, NVIDIA Docs quickstart, and local `config.py`.

## Local Interface Facts

- `guidance` is constrained to `0..7` in local config; default is `3`.
- `control_weight` is constrained to `0.0..1.0`.
- Inference requires at least one control key: `edge`, `vis`, `depth`, or `seg`.
- `edge` uses Canny edge generation on the fly when no control video is provided.
- `vis` uses blur generation on the fly when no control video is provided.
- `depth` can use VideoDepthAnything on the fly for inference, but post-training docs recommend/prefer precomputed depth data for training.
- `seg` can use GroundDINO + SAM2 on the fly for inference, but post-training docs require segmentation masks for seg training.

Reliability: `A`, verified by `/workspace/cosmos_transfer2/config.py` and local post-training docs.

## Post-Training Requirements

For local single-view post-training:

- Hardware: 8x H100/A100 80GB for the 2B model.
- Dataset: MP4 videos, 720p recommended, at least 3 seconds, 10-60 FPS.
- Captions: one JSON per video, shaped like `{"caption": "..."}`.
- Default temporal setup: `state_t=24`, `num_frames=93`, `context_parallel_size=8`.
- Recommended starting control: edge, because it requires no preprocessing.
- Depth training requires precomputed depth maps.
- Seg training requires precomputed segmentation masks.

Reliability: `A`, verified by `/workspace/docs/post-training_singleview.md`.

## Distilled Edge Constraint

The distilled edge model is faster but narrower:

- It uses `num_steps=4`.
- It is intended for short videos of strictly 93 sampled frames.
- Local code warns that distilled Transfer2.5 is not trained for autoregressive generation.

Reliability: `A`, verified by `/workspace/docs/inference.md` and `/workspace/cosmos_transfer2/inference.py`.

## License And Safety Constraints

- Hugging Face model card lists the license as NVIDIA Open Model License.
- The model card states commercial/non-commercial use is allowed under the license.
- The model card states NVIDIA does not claim ownership of outputs, but users are responsible for safe integration, guardrails, and other safety mechanisms.
- The model card warns that bypassing or disabling safety guardrails or technical limitations can terminate license rights.

Reliability: `A`, verified by official Hugging Face model card.

## Implication For Safety-Critical Training Data

Cosmos-Transfer2.5 can multiply training data, but it is not a quality-certification system. Generated clips need validation before being used as reliable autonomous-driving training data.

Reliability: `A+C`, based on public interface facts, model card responsibility statements, and research/recipe evaluation context.
