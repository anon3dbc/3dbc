# Demonstration and Evaluation Details

This page explains which footage is shown and how it relates to the paper's reported results. The five original narrated clips are 1920 × 1080, 30 fps, H.264/AAC, with burned-in English captions. The three-column hardware clip is 1920 × 1080, 30 fps, H.264, and silent. The README's full-length overview playback copy is 1280 × 720 to fit GitHub's video-attachment limit. Separate English SRT files for the narrated clips are available under `assets/subtitles/`.

## Video provenance

| File | What the viewer sees | Relationship to the source |
|---|---|---|
| `assets/videos/overview.mp4` | Narrated full demonstration, 176 s | Edited film combining method illustrations, simulation, aggregate figures, and real footage. |
| `assets/videos/overview_inline.mp4` | Same narrated demonstration, 176 s, at 720p | Smaller README playback copy of `overview.mp4`; not a separate experiment. |
| `assets/videos/three_trial_hardware.mp4` | Three side-by-side Go2 recordings, 20.13 s | Continuous source recordings `real_demo_1`, `real_demo_3`, and `real_demo_4` play at their source rate. Shorter panels hold and label their final frame. Faces and incidental venue lettering are obscured. |
| `assets/videos/hardware_clearance.mp4` | Go2 low-gate sequence, 20.13 s | Continuous full `real_demo_4` recording within synchronized full/detail views and narrated film graphics. |
| `assets/videos/pedestrian_crossings.mp4` | Go2 stairs, obstacles, pedestrian crossings, 13.87 s | Continuous 3.0–16.87 s excerpt from a separate `real_demo_1` recording. |
| `assets/videos/cross_embodiment.mp4` | Spiral-scene Go2, Go2W, G1 footage, 19 s | Three separate continuous 19 s excerpts. Source offsets are 8 s (Go2), 11 s (Go2W), and 70 s (G1). Detail views are cropped from the same decoded frames as their full views. |
| `assets/videos/mechanism.mp4` | Execution response, interval sweeps, dispatch checks, 51 s | Illustration extracted from the overview. Photo-derived standing/lowered poses are illustrations, not synthesized experimental motion. |

The four focused clips reproduce sections of the overview; the three-column video reuses recordings also shown elsewhere. These edits are viewing aids and do not add trials to the paper's reported experiment counts. The source playback rate is labeled relative to the recordings because its relationship to wall-clock time has not been independently verified. Real-footage colors are preserved; faces and incidental location text are obscured for anonymous review.

## Paper-reported results

The numerical summary is in [JSON](../assets/data/paper_reported_results.json). The available material contains the manuscript's aggregates, not raw logs indexed by trial ID. The video footage cannot independently establish aggregate success rates, confidence intervals, or contact counts.

### Simulation navigation (Table III)

The main Go2 suite contains 360 static-obstacle tasks across six families, three difficulty levels, and 20 layouts per family/level cell. Safe completion requires arrival within 60 s without forbidden contact, margin violation, fall, or contract loss. Our method reports 338/360 safe completions (93.9%). The strongest native-system comparator reports 90.0%; the adapted Rollout-CBF matched control reports 92.2%. These comparison tracks use different interfaces and should not be pooled.

For the matched-control track, p95 **full-cycle** latency is 14.6 ms for our method and 16.8 ms for the Rollout-CBF adaptation. Traversal time is calculated on the **180-task common-safe intersection**: 22.6 s for our method and 27.9 s for stop-lower-go. The Rollout-CBF 3D/posture interface was adapted for this paper and is not a published native implementation or published score.

The [evaluation plot](../assets/images/evaluation.png) uses 120 tasks per difficulty level. Its added-delay study uses 100 tasks per condition; at 150 ms added delay, reported safe completions are 87/100 (ours), 74/100 (fixed preview), and 61/100 (Posture CBF). Those counts do not describe pedestrian encounters.

### Cross-platform transfer (Table II)

Go2 is the development platform; Go2W and G1 are held out. A frozen clearance core still receives platform-specific calibrated geometry, response, support, and command interfaces. It therefore denotes **unchanged core parameters**, not zero adaptation. On the separate 120-task common-feasible sets, frozen/retuned success is 95.0/95.8% (Go2W) and 93.3/94.2% (G1). Actual target adaptation time is 52/112 min and 68/120 min, respectively.

### Hardware (Table VI)

The physical platform is a Go2 EDU with Livox Mid-360 lidar, Intel RealSense D435i, and onboard NVIDIA Orin NX 16 GB Super. The 90-trial gate benchmark contains 30 low-gate, 30 turning-gate, and 30 successive-gate trials. The paper reports 85/90 safe completions and 15.4 ms p95 full-cycle latency for our method. The pedestrian video is a **separate qualitative demonstration**; no pedestrian-specific 90-trial success rate is claimed.

## Scene images and guarantee scope

The Spiral, Building, and Plaza stills are snapshots from supplied Go2W simulator recordings. They show the scenario layouts and are not a comparison of method success. The multilevel environment preview in the beginning of the overview shows colored reference paths and prescribed moving obstacles; no robot-navigation run was carried out in that specific preview scene.

The paper's clearance statement is conditional on static-obstacle geometry and a verified finite execution segment. It requires valid body and sweep containment, supported platform dynamics and contacts, bounded model/map error, and fresh timing/queue information. The pedestrian recording shows behavior in a dynamic scene but does not extend that conditional statement to a general dynamic-pedestrian guarantee.
