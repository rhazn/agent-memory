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

2026-09-30 offline Frigate box-source handover: user again requested no more
runs and a handover for laptop closure. The 12-clip check and tests finished
before that request; no full/new long run started. Check readiness before
future inference. Latest detailed handover is in LAB_NOTES; README has commands.

Local Frigate config uses CPU default model. Local image is 0.17.2-3d4dd3a,
digest d4351369984d4a9e2a49ac59736f6490856a7ea11f7790040746d21496967010.
Copied `/cpu_model.tflite` from a temporary never-started container and removed
the container. Model file is `evaluation/posture/models/frigate_cpu_model.tflite`;
SHA-256 90bb33a634e041914cc1819aa5df99818e6c396c4d2db952c0fd7a9cffc4724f.
This is Google Coral SSD Lite MobileDet COCO, not the HumanArt detector.

New `frigate_boxes.py` runs it with ai-edge-litert 1.2.0. `ava_evaluate.py`
supports `--detector frigate-cpu`. Uses RGB uint8 320x320, static whole-frame
square padded right/bottom, person class 0, raw score floor 0.4, cutoff 0.5.
It does not reproduce Frigate motion regions, YUV decode, camera resizing,
tracking, masks, or tracked-score history. Call it offline Frigate-model boxes,
not exact Frigate event boxes or proven production-model parity.

`compare_ava_boxes.py` checks identical AVA inputs and applies frozen standalone
rules without calibration. First two Charades videos yielded 12 clips: frozen
mean F0.5 0.8410 for Frigate-model boxes vs 0.9005 for YOLOX; 25/36 vs 34/36
windows have proposals. This is execution evidence only, not general quality.
Detector confidence differs (0.5 vs 0.3); posture thresholds remain identical.
Artifacts: `results/ava-frigate-charades-smoke.json` and corresponding comparison
directory. All 61 tests, changed-code Ruff, and compilation passed. Larger
matched public-data comparison, region-fidelity discussion if needed, and exact
commercial-weight clearance remain open. HUMAN_EXPLANATION includes this state.

2026-09-30 user vocabulary clarification: keep the main comparison simple with
two paths: boxes into AVA, and boxes into skeletons into geometry rules.
Landmarks/keypoints are the skeleton's joint points; skeleton connections do
not add another model stage. MediaPipe includes person localization internally,
while RTMPose uses an explicit detector. Updated HUMAN_EXPLANATION and scoped
AGENTS to use this framing; preserve silhouette/CLIP and rule variants as history.

License source check: PyTorchVideo code is Apache-2.0; Google's AVA download
page states CC BY 4.0 for its datasets. Neither establishes asset-specific
Meta checkpoint terms or all underlying video rights. Exact pretrained-weight
commercial clearance remains open; no demonstrated AVA NC restriction found.
HumanArt README explicitly limits dataset authorization to non-commercial use;
the tested YOLOX-m detector's training provenance remains a concern. Do not
assert that dataset NC automatically bans all trained-model inference.
Boxes into AVA itself creates no special license restriction. Frigate boxes
can avoid the HumanArt detector dependency but need their own terms and quality
check. Sources and distinctions are recorded in LAB_NOTES and HUMAN_EXPLANATION.

2026-09-30 documentation requirement: user requested a plain-English explanation
of all tested approaches, grouped into a few high-level categories. Added
`evaluation/posture/HUMAN_EXPLANATION.md`: landmarks plus geometry, shape plus
geometry, learned appearance models (CLIP and AVA), and temporal/composite rules.
It explains that standalone AVA does not use our posture geometry rules, while
person boxes, score thresholds, and temporal pooling remain part of the method.
It records tested variants, results, limitations, researched-only candidates,
and next steps. README and LAB_NOTES link to it.

User requirement: keep this explanation up to date with new research. Scoped
`evaluation/posture/AGENTS.md` makes updates mandatory when experiments, findings,
conclusions, or scope/policy change. Future researchers must read README,
LAB_NOTES, and HUMAN_EXPLANATION before work. Local-link, formatting, and
approach-coverage checks passed; no inference or code changes in this task.

2026-09-30 resumed verification: all 55 tests passed with the pinned Torch
overlay; all six AVA Python files pass Ruff and compilation. README now has
download/inference/study/review commands. `ava_review.py` verifies input hashes,
exact recorded hash sampling, causal frames, and reproduction of recorded
standalone/selected metrics. All checks passed. No new inference runs launched.

Proposal coverage: Charades has boxes in 1,811/1,956 windows; all 262 sitting
positives and 247/255 lying positives have at least one proposed box. OmniFall
240 pilot has boxes in 719/720 windows and every clip. This is any-box coverage,
not measured person-detector recall or an annotation audit.

Frozen transfer confirms standalone AVA transfers better than geometry-gated
pipelines: OmniFall-to-Charades test 0.7057 standalone vs 0.5373 combined;
Charades-to-OmniFall pilot test 0.7581 standalone vs 0.6930 combined.
A shared AVA-only rule set selected from both sources' development clips
(maximize minimum source F0.5 per label) uses sitting max >= 0.74 and lying
min >= 0.02. Separate test mean F0.5: Charades 0.7355 vs geometry 0.6180;
OmniFall pilot 0.7756 vs geometry 0.7346. It sacrifices source-specific AVA
quality for a common configuration and is not a new full benchmark winner.
New reports: `evaluation/posture/results/ava-review/`, including summary,
comparison, shared/transfer predictions, all development candidates, and hashes.
The previous pause's verification/documentation tasks are now complete.
Next priority: independent public real-footage validation and full-clip error/
annotation review of frozen AVA rules; do not retune on observed test clips.

2026-09-30 AVA continuation: completed CPU SlowFast R50 Detection inference on
all 652 Charades clips and a fixed hash-selected 240-video OmniFall pilot.
Reports: `results/ava-charades.json`, `ava-omnifall-pilot240.json`, studies
under `results/ava-study/{charades,omnifall}/`. No training. Three causal
32-frame windows per clip, public YOLOX-m proposals, Torch 2.8.0/Torchvision
0.23.0/PyTorchVideo 0.1.5/RTMLib 0.0.16. MPS pooling unsupported; runs used CPU.

Charades test (same 205 clips): historical frozen 0.5440, previous optimized
geometry 0.6180, development-selected AVA standalone 0.7895, development-selected
AVA/geometry pipeline 0.7442. Standalone sitting uses second-highest >= 0.49;
lying uses max >= 0.09. Combined selection adds mean AVA sitting >= 0.21 AND
RTMPose min >= 0.05; its sitting gate loses on test. Do not promote standalone
by hindsight test selection. Lying standalone test precision 0.9516, recall
0.6782. OmniFall test is only 78 clips: frozen 0.7346, AVA standalone 0.7974,
combined 0.7949. All remain retrospective annotation-reference comparisons.

Paused at the user's request to close the laptop and avoid more long/heavy
runs. All launched workers had completed and exited. Check readiness before
another long run. Seven new targeted tests and changed-code Ruff passed;
full regressions, compilation, README reproduction commands, sampled-coverage
verification, and proposal-coverage analysis remain pending. LAB_NOTES.md has
the detailed handoff and frozen rules.

2026-09-30 continuation: added `temporal_transfer_study.py` and
`PRETRAINED_RESEARCH.md`. A source-verified search identified AVA SlowFast
detectors with static `sit` (11) and `lie/sleep` (8) heads and free public
checkpoints in MMAction2 and PyTorchVideo. New models are not yet benchmarked.
Next inference priority is an AVA head with public-detector person proposals
and strictly within-five-second windows; verify each builder's label indexing.

Cached optimization uses the original video hash split, not a fresh external
test. Charades has 84 development videos / 447 clips and 36 test videos / 205
clips. On matching test clips, frozen mean F0.5 is 0.5440, threshold-only
recalibration is 0.5532, and development-selected backend/pooling is 0.6180.
Selected: RTMPose sitting min >= 0.05 (all three frames); silhouette lying max
>= 0.80 (any frame). Lying precision falls while recall rises; negatives remain
annotation disagreements. Charades rules transfer poorly to OmniFall pilot
test (0.6796 vs original 0.7500), so no universal replacement is established.
The original OmniFall development search selects its historical rules again.
All 44 tests, changed-code Ruff, and compilation passed.

Of the frozen Charades misses, 70 sitting and 63 lying clips have zero primary
posture score across all samples; another 65 sitting and 68 lying misses have
only one nonzero frame. These are rule-score coverage diagnostics, not measured
person-detector recall. Threshold-only tuning cannot recover zero-score cases.
Artifacts: `evaluation/posture/results/temporal-transfer-study/`, including
input hashes, development candidates, miss partitions, and per-clip outputs.

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
