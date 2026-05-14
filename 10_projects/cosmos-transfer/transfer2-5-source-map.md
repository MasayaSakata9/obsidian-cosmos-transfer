# Cosmos-Transfer2.5 Source Map

Last updated: 2026-05-14

## Purpose

This note classifies reliable sources for Cosmos-Transfer2.5 research. Use it before accepting claims into durable findings.

## Reliability Grades

- `A`: NVIDIA docs, local code, official GitHub, official Hugging Face model card.
- `B`: NVIDIA Newsroom, NVIDIA Blog, or official partner/company press releases.
- `C`: NVIDIA Research pages or arXiv papers. Strong technical evidence, but not an operational guarantee.
- `D`: third-party summaries, Reddit, SEO dataset reviews, or unaffiliated commentary. Do not use for decisions unless corroborated by A/B/C sources.

## A-Grade Sources

- NVIDIA Docs Transfer2.5 Model Matrix: `https://docs.nvidia.com/cosmos/2.1.0/transfer2.5/model_matrix.html`
- NVIDIA Docs Quickstart: `https://docs.nvidia.com/cosmos/2.1.0/transfer2.5/quickstart_guide.html`
- NVIDIA Docs Auto Multiview Inference: `https://docs.nvidia.com/cosmos/2.1.0/transfer2.5/auto-multiview_inference.html`
- NVIDIA Docs World Scenario Video Generation: `https://docs.nvidia.com/cosmos/2.1.0/transfer2.5/world_scenario_video_generation.html`
- Hugging Face model card: `https://huggingface.co/nvidia/Cosmos-Transfer2.5-2B`
- Official GitHub/local checkout: `/workspace`
- Local public interfaces: `/workspace/cosmos_transfer2/config.py`, `/workspace/cosmos_transfer2/inference.py`, `/workspace/examples/inference.py`

## B-Grade Sources

- NVIDIA Newsroom major Cosmos release: `https://nvidianews.nvidia.com/news/nvidia-announces-major-release-of-cosmos-world-foundation-models-and-physical-ai-data-tools`
- NVIDIA Blog Cosmos overview: `https://blogs.nvidia.com/blog/cosmos-world-foundation-models/`
- Uber official press release: `https://investor.uber.com/news-events/news/press-release-details/2025/Uber-Teams-Up-with-NVIDIA-to-Accelerate-Autonomous-Mobility/default.aspx`

## C-Grade Sources

- NVIDIA Cosmos-Transfer2.5 research page: `https://research.nvidia.com/labs/cosmos-lab/cosmos-transfer2.5/`
- World Simulation with Video Foundation Models for Physical AI: `https://arxiv.org/abs/2511.00062`
- Cosmos-Drive-Dreams paper/project: `https://arxiv.org/abs/2506.09042`
- Cosmos-Transfer1 paper: `https://arxiv.org/abs/2503.14492`

## Use Policy

- Use A-grade sources for implementation details and model constraints.
- Use B-grade sources for ecosystem and adoption claims.
- Use C-grade sources for research performance and evaluation context.
- Do not turn C-grade evaluation results into safety guarantees.
- Do not use D-grade sources for Obsidian durable memory unless they only point to a primary source that is then verified.
