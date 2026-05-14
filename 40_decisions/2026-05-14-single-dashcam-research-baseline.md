# Decision: Use Single-View General Transfer As The Dashcam Research Baseline

## Decision

Treat single-view `Cosmos-Transfer2.5-2B` real-to-real augmentation as the primary baseline for dashcam training-data research. Use AV multiview and world-scenario map control only as secondary references unless the data source expands beyond single dashcam footage.

## Context

The user wants to use Cosmos-Transfer to generate high-quality training data variations from original dashcam footage, where reliability matters more than maximizing novelty.

## Alternatives Considered

- Start from AV multiview or map-control workflows.
- Treat simulator-to-real and real-to-real as equal-priority workflows.
- Start from distilled edge as the default inference path.

## Consequences

- Research, validation, and note organization stay focused on the workflow that matches the stated data source.
- Specialized AV checkpoints remain useful background knowledge but do not dominate the first implementation path.
- Reliability checks stay centered on single-view structure preservation and artifact review.
