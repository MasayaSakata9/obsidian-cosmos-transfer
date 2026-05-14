# Finding: Reliability Requires Post-Generation Validation

## Finding

Cosmos-Transfer is suitable for multiplying training data, but reliability-critical use should assume post-generation validation is mandatory. NVIDIA's strongest published preservation claims come from simulator-to-real evaluation rather than a blanket guarantee for arbitrary real dashcam edits.

## Evidence

- The Cosmos Cookbook simulator-to-real AV recipe claims preservation of anomaly behavior, trajectories, bounding boxes, labels, and temporal consistency in its evaluation scenario.
- NVIDIA's product positioning emphasizes synthetic data generation for training and validation, not automatic certification of generated outputs.
- The local code and docs expose controls and masks but do not provide a built-in quality-certification layer for generated samples.

## Impact

- Generated videos should be checked before being promoted into trusted training sets.
- Validation should focus on behavior preservation, annotation consistency, and artifact detection.

## Confidence

High. The positive preservation evidence is specific, but the absence of built-in certification in the public inference path means post-generation validation remains the safe interpretation.

## Operational Recommendation

Require a validation pass for any generated clip that will influence safety-relevant model behavior, especially when labels or trajectories are expected to remain trustworthy.

## Reuse Trigger

Reread this before trusting generated samples as high-quality supervision data.
