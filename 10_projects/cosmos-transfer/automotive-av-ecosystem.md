# Automotive And AV Ecosystem Evidence

Last updated: 2026-05-14

## Summary

Public evidence supports Cosmos as an AV and robotics synthetic-data platform, but company-specific claims must be separated into "Cosmos platform adoption" and "Cosmos Transfer direct usage."

## Confirmed Cosmos Transfer Direct Usage

### Foretellix And Parallel Domain

NVIDIA Newsroom states that the NVIDIA Omniverse Blueprint for autonomous vehicle simulation uses Cosmos Transfer to amplify variations of physically based sensor data, and that Foretellix can vary weather and lighting for diverse driving datasets while Parallel Domain applies similar variation to sensor simulation.

Reliability: `B`, NVIDIA Newsroom. Treat as direct Cosmos Transfer ecosystem evidence.

## Confirmed Cosmos Platform / AV Ecosystem Usage

### Uber

Uber and NVIDIA announced a collaboration using NVIDIA Cosmos and DGX Cloud to support AI-powered autonomous driving development. Uber states its trip data will be paired with Cosmos and DGX Cloud to help AV partners build stronger models.

Reliability: `B`, Uber official investor press release and NVIDIA Newsroom. Treat as Cosmos platform evidence, not proof that Uber specifically uses Cosmos-Transfer2.5 in production pipelines.

### Waabi

NVIDIA Blog and Newsroom list Waabi among physical AI or AV developers working with/adopting Cosmos. Public Waabi materials emphasize neural simulation and AV safety, but the currently verified sources do not prove direct Cosmos-Transfer2.5 usage by Waabi.

Reliability: `B` for Cosmos ecosystem mention; `D/unknown` for direct Transfer2.5 usage.

### XPENG

NVIDIA Blog lists XPENG among physical AI leaders working with Cosmos. Current verified sources do not prove direct Cosmos-Transfer2.5 usage by XPENG.

Reliability: `B` for Cosmos ecosystem mention; `D/unknown` for direct Transfer2.5 usage.

### Nexar And Oxa

NVIDIA Newsroom states Nexar and Oxa are using Cosmos Predict to advance autonomous driving systems. This is relevant to the Cosmos AV ecosystem, but it is not Cosmos Transfer evidence.

Reliability: `B` for Cosmos Predict mention; not Transfer evidence.

## Research Context

Cosmos-Drive-Dreams describes a synthetic driving data generation pipeline specialized from NVIDIA Cosmos for driving-domain multiview, spatiotemporally consistent generation. It reports benefits for long-tail distribution and downstream tasks such as 3D lane detection, 3D object detection, and driving policy learning.

Reliability: `C`, NVIDIA Research/arXiv. Treat as research evidence, not deployment proof.

## Practical Interpretation

- Direct Transfer usage evidence is strongest for NVIDIA's own blueprints, Foretellix, and Parallel Domain.
- Uber is strong ecosystem evidence for Cosmos + DGX Cloud in AV development, but not a specific Transfer2.5 workflow proof.
- Waabi, XPENG, Nexar, and Oxa should not be used as proof of direct Cosmos Transfer training-data pipelines unless a direct company or NVIDIA source says so.
