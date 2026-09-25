# Frigate Posture Benchmark

## Current Status

As of 2026-09-25, the OmniFall synthetic benchmark has 12,000 immutable,
five-second current-posture checkpoints. The benchmark scores independent
`sitting` and `laying-down` labels with mean F0.5.

The current best commercially eligible result is a fixed ensemble of MediaPipe
Pose and MediaPipe Pose Landmarker: mean F0.5 0.7177. It uses MediaPipe Pose
for sitting only when both backends agree (thresholds 0.59 and 0.54), and uses
an OR rule for laying-down (thresholds 0.12 and 0.32). The single calibrated
MediaPipe Pose baseline is 0.7146.

## Decisions

- Keep benchmark frames and labels immutable. Use no private or production data.
- Treat RTMPose as experimental until its exact distributed weights have a
  confirmed commercial-use license. It scores 0.7475 F0.5 on laying-down but
  is not in the eligible winner.
- Reject landmark cropping, image-plane geometry, lower-complexity MediaPipe
  models, and bilateral landmark gating based on benchmark results.
- Evaluation supports resumable video ranges and report merging because a
  monolithic full suite can exceed the execution limit.

## Relevant Files

- `evaluation/posture/README.md`
- `evaluation/posture/evaluate.py`
- `evaluation/posture/calibrate.py`
- `evaluation/posture/ensemble_reports.py`
- `evaluation/posture/merge_reports.py`
