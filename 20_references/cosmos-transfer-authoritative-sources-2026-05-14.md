# Reference Set: Cosmos-Transfer Authoritative Sources

Last updated: 2026-05-14

## Official Technical Sources

- NVIDIA Docs Transfer2.5 Model Matrix: `https://docs.nvidia.com/cosmos/2.1.0/transfer2.5/model_matrix.html`
  - Model variants, minimum GPUs, VRAM, and inference performance.
- NVIDIA Docs Quickstart: `https://docs.nvidia.com/cosmos/2.1.0/transfer2.5/quickstart_guide.html`
  - General model inference commands and control parameter format.
- NVIDIA Docs Auto Multiview Inference: `https://docs.nvidia.com/cosmos/2.1.0/transfer2.5/auto-multiview_inference.html`
  - 8-GPU multiview requirement and world-scenario workflow.
- NVIDIA Docs World Scenario Video Generation: `https://docs.nvidia.com/cosmos/2.1.0/transfer2.5/world_scenario_video_generation.html`
  - 3D scene annotation inputs, seven camera names, and rendered map/control elements.
- Hugging Face model card: `https://huggingface.co/nvidia/Cosmos-Transfer2.5-2B`
  - Model family, license, safety responsibilities, output ownership, and model overview.
- Official GitHub: `https://github.com/nvidia-cosmos/cosmos-transfer2.5`
  - Source code, README, release notes, and docs mirrored locally in `/workspace`.

## Official Cookbook Sources

- Multi-control recipe: `https://nvidia-cosmos.github.io/cosmos-cookbook/recipes/inference/transfer2_5/inference-real-augmentation/inference.html`
  - Control roles, common recipes, guidance values, and masking examples.
- AV sim-to-real recipe: `https://nvidia-cosmos.github.io/cosmos-cookbook/recipes/inference/transfer2_5/inference-carla-sdg-augmentation/inference.html`
  - Simulator-to-real workflow, anomaly preservation claims, and 18x augmentation example.
- Auto multiview post-training: `https://nvidia-cosmos.github.io/cosmos-cookbook/recipes/post_training/transfer2_5/av_world_scenario_maps/post_training.html`
  - HD map/multiview post-training context.

## Official Research Sources

- Cosmos-Transfer2.5 research page: `https://research.nvidia.com/labs/cosmos-lab/cosmos-transfer2.5/`
  - Architecture comparison, long-video behavior, AV multiview metrics.
- World Simulation paper: `https://arxiv.org/abs/2511.00062`
  - Transfer2.5 and Predict2.5 broader model context.
- Cosmos-Drive-Dreams paper: `https://arxiv.org/abs/2506.09042`
  - Driving-domain synthetic data generation and downstream evaluation context.
- Cosmos WFM platform paper: `https://arxiv.org/abs/2501.03575`
  - Platform-level context: curation, post-training, tokenizers, WFMs.

## Official Ecosystem Sources

- NVIDIA Newsroom major release: `https://nvidianews.nvidia.com/news/nvidia-announces-major-release-of-cosmos-world-foundation-models-and-physical-ai-data-tools`
  - Cosmos adoption, Cosmos Transfer synthetic data positioning, Foretellix/Parallel Domain/Nexar/Oxa mentions.
- NVIDIA Blog Cosmos overview: `https://blogs.nvidia.com/blog/cosmos-world-foundation-models/`
  - Open model availability, training data scale, Cosmos platform positioning.
- Uber official press release: `https://investor.uber.com/news-events/news/press-release-details/2025/Uber-Teams-Up-with-NVIDIA-to-Accelerate-Autonomous-Mobility/default.aspx`
  - Uber/NVIDIA collaboration using Cosmos and DGX Cloud for AV development.

## Excluded Or Low-Trust Sources

- Third-party dataset review pages.
- Reddit discussions.
- Unaffiliated blog posts.
- Generic press summaries that do not link to primary NVIDIA or company statements.
