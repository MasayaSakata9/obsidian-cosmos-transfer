# Japanese Dashcam Implications

Last updated: 2026-05-14

## Position

For Japanese dashcam inputs, start with inference-time tuning before post-training. The distribution shift is real, but Cosmos-Transfer2.5's control-conditioned design means structure from the source video can often be preserved without immediate model tuning.

Reliability: `A + inference`. The control mechanics are verified by docs/code; the Japan-specific conclusion is an operational inference.

## Why Japan Is A Domain Shift

Japanese dashcam footage can differ from generic AV examples in:

- left-hand traffic
- narrow roads and dense urban layouts
- Japanese traffic signs and road text
- different lane markings, stop lines, crosswalks, guardrails, poles, and signals
- kei cars, taxis, buses, scooters, bicycles, and pedestrian density patterns
- tunnels, expressways, rainy night roads, snow regions, and mountain roads

## First-Line Tuning

Use existing inference with Japan-specific prompts and conservative controls:

- Prompt explicitly names Japan, left-hand traffic, road type, weather, time of day, and lighting.
- `edge`: primary structure-preservation control.
- `seg + edge`: preferred core pair for controlled edits.
- `depth`: add when perspective, road geometry, distance, or fog/rain realism matters.
- `vis`: keep low when variation is the goal; high `vis` can pull output back toward the source appearance.
- `guidance`: start near `3`, then sweep upward only if prompt adherence is weak.

## When Post-Training Becomes Necessary

Post-training becomes worth considering if repeated inference sweeps show:

- left-hand traffic context is visually or semantically degraded
- Japanese signs, road markings, or traffic lights become implausible
- vehicle/pedestrian positions drift enough to break labels or behavior assumptions
- night/rain/snow/tunnel outputs show systematic artifacts
- the generated video is not useful after control-weight and prompt sweeps

## Required Assets For Japan-Specific Post-Training

Based on local single-view post-training docs:

- Japanese dashcam MP4 clips.
- Captions in English or reliably model-compatible English descriptions, one JSON per video.
- 720p recommended, at least 3 seconds, 10-60 FPS, and at least 93 frames for the default setup.
- Edge/vis can start without precomputed controls.
- Depth requires precomputed depth videos for training.
- Seg requires precomputed segmentation videos for training.
- 8x H100/A100 80GB is the documented hardware target for 2B post-training.

## Validation Needs

Generated Japanese dashcam clips must be filtered before entering trusted training sets:

- label and trajectory consistency
- traffic-side consistency
- sign/signal plausibility
- road-marking consistency
- temporal stability
- artifact and hallucination review

## Current Recommendation

Do not start with post-training. Build a small Japanese dashcam inference benchmark first, sweep prompt/control settings, score outputs, then decide whether failures are systematic enough to justify post-training.
