# Frigate Posture Benchmark

## Current Status

As of 2026-09-29, OmniFall has 12,000 causal five-second clips. Independent
`sitting` and `laying-down` labels mean the static posture occurs anywhere in
the clip. The primary metric is mean F0.5. Endpoint results are historical and
must not be numerically compared with the any-point clip results.

The current full any-point baseline is MediaPipe Heavy with three frames and
top-2 score means: F0.5 0.7065, calibrated on the full manifest.

A completed 1,200-clip pilot caches MediaPipe posture, silhouette geometry,
and RTMPose on the same three frames. A deterministic video-disjoint split
gives 828 development / 372 test clips. Development-selected rules are:
- Sitting: MediaPipe score >= 0.71 in at least two frames.
- Laying down: silhouette score >= 0.83 in at least two frames.

Test mean F0.5 is 0.7500 versus matched development-calibrated baseline 0.6907.
Test laying precision is 0.9053; false positives fall from 20 to 9 and true
positives rise from 77 to 86. RTMPose agreement loses to silhouette alone on
development and is not needed by this selected rule. This pilot is not a new
full benchmark winner. Its test split is retrospective because these videos
influenced historical experiments; scene/actor independence is not established.

The first full temporal geometry run stopped before final report writes,
losing in-memory predictions. The runner now saves atomic progress reports
every 25 clips and resumes the same command. Next: validate the frozen pilot
rules on the remaining 10,800 clips, ideally with a MediaPipe-only mode, then
investigate temporal Pose Landmarker sitting. Do not retune on pilot test clips.

## Decisions

- Keep benchmark frames and labels immutable. Use no private or production data.
- RTMPose is permitted for internal deployment. The default detector is trained
  on HumanArt, whose dataset access is non-commercial, so record this
  provenance risk before external commercial redistribution.
- Reject landmark cropping, image-plane geometry, lower-complexity MediaPipe
  models, bilateral landmark gating, detector-box geometry, whole-frame CLIP,
  and RTMPose-x based on benchmark results.
- Historical endpoint silhouette geometry was weak alone, but temporal 2-of-3
  silhouette scoring is the strongest laying-down branch in the current pilot.
- Evaluation supports resumable video ranges and report merging because a
  monolithic full suite can exceed the execution limit.

## Relevant Files

- `evaluation/posture/README.md`
- `evaluation/posture/LAB_NOTES.md` is the detailed handoff and result record.
- `evaluation/posture/temporal_geometry_evaluate.py`
- `evaluation/posture/temporal_geometry_study.py`
- Local ignored reports: `evaluation/posture/results/temporal-geometry-pilot-study/`
- `evaluation/posture/evaluate.py`
- `evaluation/posture/calibrate.py`
- `evaluation/posture/ensemble_reports.py`
- `evaluation/posture/merge_reports.py`
- `evaluation/posture/segmentation_geometry_evaluate.py`
