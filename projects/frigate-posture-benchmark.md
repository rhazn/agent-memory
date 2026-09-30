# Frigate Posture Benchmark

## Evaluation Contract And Model Policy

User clarification, 2026-09-30:

- Evaluate posture-recognition quality for later Frigate integration, not the
  full production system. Frigate supplies person boxes/crops and handles alerts.
- Input remains a causal five-second clip. Any frames, crops, or video sequence
  inside it may be used. Output is two booleans: any sitting person and any
  lying person anywhere in the clip, possibly different people.
- Tracking, persistent identity, person association, transition recognition,
  alerting, and Frigate integration are not benchmark prerequisites or goals.
- Never use sensitive production data for training, fine-tuning, or benchmark
  evaluation. Existing pretrained classifiers are valid without new training.
- Quality first; model weights must be obtainable/downloadable for free.
  No paid model access/API requirement. Do not exclude models by license type
  during evaluation. Review licenses after quality identifies deployment
  candidates. This supersedes earlier permissive-only/YOLO/VideoMAE exclusions.
- Next model-search priority: freely downloadable pretrained static-posture
  classifiers for images/crops, RGB clips, or skeleton sequences. RTMPose is
  already tested, but its landmark outputs use our geometry rules; YOLO Pose
  likewise is not a ready-made sitting/lying classifier.
- Research roadmap in LAB_NOTES.md also covers full-frame/multi-crop inputs,
  pooling/ensembles, SAM 2/OWLv2/context models, label auditing, and fresh
  public-data splits. Continue separate OmniFall and Charades scores.

## Current Status

As of 2026-09-29, OmniFall has 12,000 causal five-second clips. Independent
`sitting` and `laying-down` labels mean the static posture occurs anywhere in
the clip. The primary metric is mean F0.5. Endpoint results are historical and
must not be numerically compared with the any-point clip results.

Charades was added on 2026-09-29: a fixed 120-video official-test subset
(30 each sitting-only, lying-only, both, neither), yielding 652 five-second
clips. HTTP range extraction fetched only about 290 MB from the 480p ZIP.
The custom license permits evaluation outside academia, not general commercial
use/training or redistribution. Data and visual audit assets remain ignored.

Download/preparation now default to both datasets. `evaluate_suite.py` defaults
to separate OmniFall and Charades scores using frozen `candidates.json` rules.
Its OmniFall reference is the 1,200-clip cached pilot, including development
data; the separate full frozen-validation result below is preserved.

Real-footage scores are much worse. Mean F0.5 on Charades: 0.5276 for the
MediaPipe/silhouette 2-of-3 winner, 0.4874 for silhouette top-2, 0.4221 for
RTMPose/silhouette agreement. No Charades tuning. Winner recall is only 0.2824
sitting and 0.2392 lying. The winner stays the same but runner-up order changes.

Charades negatives are annotation-reference negatives, not verified absence:
test descriptions mention sitting in 77 and lying in 18 videos without the
corresponding static label. A 12-clip assistant visual spot-check found nine
apparently consistent and three uncertain cases; no labels changed. Do not
claim label completeness or promote this as definitive false-alarm evaluation.
Pair the pretrained-classifier search with real-footage label auditing and
low-recall error analysis, using fresh evaluation splits rather than more
synthetic-only tuning.

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

Frozen validation on all remaining 10,800 clips completed on 2026-09-29 using
the new MediaPipe-only mode. Mean F0.5 is 0.7730 versus frozen matched baseline
0.6954, with no retuning. Sitting F0.5: 0.7142 vs 0.7005. Laying F0.5: 0.8318
vs 0.6903; precision: 0.8629 vs 0.7071; recall: 0.7267 vs 0.6304. Laying false
positives fall from 887 to 392 while true positives rise from 2141 to 2468.
Coverage, video exclusion, clip alignment, and frozen input hashes all passed.
This remains retrospective synthetic-data validation, not external validation.

The first full temporal geometry run stopped before final report writes,
losing in-memory predictions. The runner now saves atomic progress reports
every 25 clips and resumes the same command. Preserve the
frozen validation result; both the pilot test and remaining validation clips
have now been observed.

## Decisions

- Keep benchmark frames and labels immutable. Use no private or production data.
- RTMPose is permitted for internal deployment. The default detector is trained
  on HumanArt, whose dataset access is non-commercial, so record this
  provenance risk before external commercial redistribution.
- Historical tests rejected particular landmark-crop, image-plane geometry,
  lower-complexity MediaPipe, bilateral gate, detector-box geometry, whole-frame
  CLIP, and RTMPose-x configurations. These are not blanket rejections of every
  crop method or classifier using those model families.
- Historical endpoint silhouette geometry was weak alone, but temporal 2-of-3
  silhouette scoring is the strongest laying-down branch in the current pilot.
- Evaluation supports resumable video ranges and report merging because a
  monolithic full suite can exceed the execution limit.

## Relevant Files

- `evaluation/posture/README.md`
- `evaluation/posture/LAB_NOTES.md` is the detailed handoff and result record.
- `evaluation/posture/CHARADES.md`
- `evaluation/posture/evaluate_suite.py` and `candidates.json`
- Two-dataset reports: `evaluation/posture/results/two-dataset-suite/`
- `evaluation/posture/temporal_geometry_evaluate.py`
- `evaluation/posture/temporal_geometry_study.py`
- `evaluation/posture/temporal_frozen_validate.py`
- Local ignored reports: `evaluation/posture/results/temporal-geometry-pilot-study/`
- Frozen validation reports: `evaluation/posture/results/temporal-frozen-validation/`
- `evaluation/posture/evaluate.py`
- `evaluation/posture/calibrate.py`
- `evaluation/posture/ensemble_reports.py`
- `evaluation/posture/merge_reports.py`
- `evaluation/posture/segmentation_geometry_evaluate.py`
