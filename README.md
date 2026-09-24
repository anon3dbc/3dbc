# 3D Clearance Navigation for Ground Robots with Compact Execution-Aware Body Envelopes

**Anonymous supplementary materials**

We coordinate route, posture, and execution to navigate three-dimensional body-clearance constraints.

## Overview

https://github.com/user-attachments/assets/e6371a65-e60b-4c76-b409-f452dc0088e6

## Real-Robot Experiments

https://github.com/user-attachments/assets/aa15ae23-0065-464d-9494-18eb3a2f6e0e

Three Go2 recordings show low-clearance navigation and pedestrian crossings. The paper's **85/90** hardware result concerns the gate benchmark; these clips are qualitative examples.

## Cross-Embodiment Simulation

**Go2, Go2W, and G1**

https://github.com/user-attachments/assets/c4edd35c-480e-43d1-9244-3e3f774fcd6b

![Additional simulation scenes](assets/images/simulation_scenes.jpg)

## Method

Platform-specific contracts feed a shared clearance planner, followed by sweep checking and verified dispatch.

![Method architecture](assets/images/architecture.png)

https://github.com/user-attachments/assets/67cb114b-9baf-445b-b2a0-8fa6652c4a01

## Evaluation

Go2 simulation: **338/360** safe completions. Held-out Go2W and G1 use the shared core with platform calibration. Go2 hardware: **85/90** safe completions.

![Simulation results](assets/images/evaluation.png)

The source code will be released upon acceptance.
