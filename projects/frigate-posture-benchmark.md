# Frigate Posture Benchmark

## Current Status

As of 2026-09-25, the OmniFall synthetic benchmark has 12,000 immutable,
five-second current-posture checkpoints. The benchmark scores independent
`sitting` and `laying-down` labels with mean F0.5.

The current best internal-use result is a fixed three-branch ensemble: mean
F0.5 0.7624. Sitting uses MediaPipe Pose and Pose Landmarker agreement, with
F0.5 0.7258. Laying down uses RTMPose and MediaPipe segmentation silhouette
agreement, with F0.5 0.7989 and precision 0.8365. The single calibrated
MediaPipe Pose baseline is 0.7146.

## Decisions

- Keep benchmark frames and labels immutable. Use no private or production data.
- RTMPose is permitted for internal deployment. The default detector is trained
  on HumanArt, whose dataset access is non-commercial, so record this
  provenance risk before external commercial redistribution.
- Reject landmark cropping, image-plane geometry, lower-complexity MediaPipe
  models, bilateral landmark gating, detector-box geometry, whole-frame CLIP,
  and RTMPose-x based on benchmark results.
- MediaPipe silhouette geometry is weak alone but substantially improves
  RTMPose lying-down precision when both agree.
- Evaluation supports resumable video ranges and report merging because a
  monolithic full suite can exceed the execution limit.

## Relevant Files

- `evaluation/posture/README.md`
- `evaluation/posture/evaluate.py`
- `evaluation/posture/calibrate.py`
- `evaluation/posture/ensemble_reports.py`
- `evaluation/posture/merge_reports.py`
- `evaluation/posture/segmentation_geometry_evaluate.py`
