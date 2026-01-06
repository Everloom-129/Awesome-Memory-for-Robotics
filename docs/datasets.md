# Datasets for Memory in Robotics

This document catalogs datasets relevant to memory research in robotics, organized by application domain and memory-related characteristics.

## Overview

Datasets play a crucial role in training and evaluating memory systems for robotics. This collection includes datasets for manipulation, navigation, perception, and lifelong learning tasks, with emphasis on those that pose challenges requiring memory capabilities such as long-horizon planning, partial observability, and temporal reasoning.

---

## Large-Scale Robot Learning Datasets

### Open X-Embodiment Dataset

The largest open-source real robot dataset, designed for cross-embodiment generalization.

| Attribute | Details |
|-----------|---------|
| **Size** | 1M+ real robot trajectories |
| **Embodiments** | 22 robot types |
| **Institutions** | 21 collaborating institutions |
| **Skills** | 527 skills (160,266 tasks) |
| **Modalities** | RGB, depth, proprioception |
| **Memory Challenge** | Cross-embodiment transfer, skill generalization |
| **Links** | [[Paper]](https://arxiv.org/abs/2310.08864) [[Project]](https://robotics-transformer-x.github.io/) [[GitHub]](https://github.com/google-deepmind/open_x_embodiment) [[HuggingFace]](https://huggingface.co/datasets/jxu124/OpenX-Embodiment) |

### OXE-AugE

Large-scale augmentation of Open X-Embodiment dataset with additional robot embodiments.

| Attribute | Details |
|-----------|---------|
| **Embodiments** | 9 additional robot types |
| **Datasets** | 16 augmented datasets |
| **Memory Challenge** | Enhanced cross-embodiment learning |
| **Links** | [[Paper]](https://arxiv.org/abs/2512.13100) |

### DROID Dataset

Large-scale in-the-wild robot manipulation dataset with diverse environments.

| Attribute | Details |
|-----------|---------|
| **Size** | 76,000 demonstration trajectories |
| **Duration** | 350 hours of interaction data |
| **Scenes** | 564 unique scenes |
| **Tasks** | 86 manipulation tasks |
| **Collectors** | 50 data collectors |
| **Modalities** | RGB-D, proprioception |
| **Memory Challenge** | Scene diversity, task generalization |
| **Links** | [[Project]](https://droid-dataset.github.io/) |

### BridgeData V2

Large and diverse dataset of robotic manipulation behaviors for scalable robot learning.

| Attribute | Details |
|-----------|---------|
| **Size** | 60,096 trajectories |
| **Skills** | 13 foundational manipulation skills |
| **Tasks** | Pick-and-place, pushing, sweeping, etc. |
| **Modalities** | RGB, proprioception |
| **Memory Challenge** | Multi-skill learning, compositional generalization |
| **Links** | [[Paper]](https://arxiv.org/abs/2308.12952) [[Project]](https://rail-berkeley.github.io/bridgedata/) |

### RoboMIND

Multi-embodiment intelligence normative data for robot manipulation.

| Attribute | Details |
|-----------|---------|
| **Focus** | Multi-embodiment robot manipulation |
| **Year** | 2024 |
| **Memory Challenge** | Cross-embodiment transfer |
| **Links** | [[Paper]](https://arxiv.org/abs/2412.13877) |

### AgiBot World Colosseo

Full-stack large-scale robot learning platform for bimanual manipulation.

| Attribute | Details |
|-----------|---------|
| **Focus** | Bimanual manipulation |
| **Award** | IROS 2025 Award Finalist |
| **Memory Challenge** | Coordinated bimanual control, long-horizon tasks |
| **Links** | [[GitHub]](https://github.com/OpenDriveLab/AgiBot-World) |

### LeRobot

Open-source models, datasets, and tools for real-world robotics in PyTorch.

| Attribute | Details |
|-----------|---------|
| **Focus** | Democratizing robot learning |
| **Modalities** | Various robot platforms |
| **Links** | [[HuggingFace]](https://huggingface.co/lerobot) |

---

## Memory-oriented Manipulation Datasets

Unfortunately, there are not many memory-oriented datasets for manipulation tasks. Here we include some relevant ones for open discussion. Please feel free to criticize and add more datasets to the list.

### MIKASA-Robo Datasets

32 visual-based datasets specifically designed for memory-intensive robotic manipulation tasks.

| Attribute | Details |
|-----------|---------|
| **Tasks** | 32 memory-intensive tasks in 12 groups |
| **Episodes per Task** | 250 episodes |
| **Memory Types Tested** | Object, Spatial, Sequential, Capacity |
| **Task Categories** | ShellGame, Intercept, Rotate, RememberColor/Shape, ChainOfColors |
| **Modalities** | RGB images, proprioception |
| **Memory Challenge** | Object permanence, spatial reasoning, sequence recall |
| **Links** | [[Paper]](https://arxiv.org/abs/2502.10550) [[GitHub]](https://github.com/CognitiveAISystems/MIKASA-Robo) [[HuggingFace]](https://huggingface.co/datasets) |

### RoboTwin 2.0

Scalable framework for data generation and benchmarking in bimanual robotic manipulation.

| Attribute | Details |
|-----------|---------|
| **Focus** | Bimanual manipulation |
| **Features** | Procedural data generation |
| **Memory Challenge** | Coordinated long-horizon bimanual tasks |
| **Links** | [[Project]](https://robotwin-platform.github.io/) |

---

## Navigation Datasets

### Habitat-Matterport 3D (HM3D)

Large-scale 3D environments for embodied AI navigation research.

| Attribute | Details |
|-----------|---------|
| **Scenes** | 1,000+ large-scale 3D environments |
| **Source** | Real-world 3D scans |
| **Metrics** | Navigable area, navigation complexity |
| **Robot Model** | Cylindrical robot (0.1m radius, 1.5m height) |
| **Memory Challenge** | Large-scale spatial memory, exploration |
| **Links** | [[Paper]](https://arxiv.org/abs/2109.08238) [[Project]](https://aihabitat.org/datasets/hm3d/) [[GitHub]](https://github.com/facebookresearch/habitat-matterport3d-dataset) |

### HM3D Semantics (HM3DSEM)

Largest dataset of 3D real-world spaces with dense semantic annotations.

| Attribute | Details |
|-----------|---------|
| **Annotations** | Dense semantic labels |
| **Tasks** | Object Goal Navigation |
| **Memory Challenge** | Semantic scene understanding |
| **Links** | [[Paper]](https://openaccess.thecvf.com/content/CVPR2023/html/Yadav_Habitat-Matterport_3D_Semantics_Dataset_CVPR_2023_paper.html) |

### HM3D-OVON

Open Vocabulary Object Goal Navigation benchmark.

| Attribute | Details |
|-----------|---------|
| **Focus** | Open-vocabulary navigation |
| **Year** | 2024 |
| **Memory Challenge** | Semantic generalization, novel object recognition |
| **Links** | [[Paper]](https://ieeexplore.ieee.org/document/10802709/) |

### NaVQA Dataset

Long-horizon robot navigation videos for question answering.

| Attribute | Details |
|-----------|---------|
| **Focus** | Spatio-temporal memory for navigation |
| **Tasks** | Perceptual question-answering |
| **Memory Challenge** | Long-horizon reasoning, semantic memory |
| **Links** | [[Project]](https://rasc.usc.edu/blog/remembr/) |

### VLNGo2-Matterport

Vision-Language Navigation dataset for quadruped robots.

| Attribute | Details |
|-----------|---------|
| **Focus** | Quadruped robot navigation |
| **Year** | 2025 |
| **Memory Challenge** | Continuous navigation, language grounding |
| **Links** | [[Paper]](https://www.researchgate.net/publication/390799350) |

---

## Embodied AI Benchmarks with Datasets

### BEHAVIOR-1K

Human-centered embodied AI benchmark with 1,000 everyday activities.

| Attribute | Details |
|-----------|---------|
| **Activities** | 1,000 everyday household tasks |
| **Demonstrations** | 10,000 human trajectories (200 per task) |
| **Duration** | 1,200+ hours of demonstration data |
| **Knowledge Base** | Crowdsourced activity definitions |
| **Memory Challenge** | Long-horizon planning, state tracking |
| **Links** | [[Paper]](https://arxiv.org/abs/2403.09227) [[Project]](https://behavior.stanford.edu/) |

### Mini-BEHAVIOR

Procedurally generated benchmark for long-horizon decision-making.

| Attribute | Details |
|-----------|---------|
| **Tasks** | 20 long-horizon, human-centered tasks |
| **Features** | Procedural generation |
| **Memory Challenge** | Multi-step planning, state persistence |
| **Links** | [[Paper]](https://arxiv.org/abs/2310.01824) |

### EmbodiedBench

Comprehensive benchmark for evaluating MLLMs as embodied agents.

| Attribute | Details |
|-----------|---------|
| **Tasks** | 1,128 testing tasks |
| **Environments** | 4 (ALFRED, Habitat, Navigation, Manipulation) |
| **Capabilities Tested** | 6 critical agent capabilities |
| **Memory Challenge** | Long-horizon planning, spatial awareness |
| **Links** | [[Paper]](https://arxiv.org/abs/2502.09560) [[Project]](https://embodiedbench.github.io/) [[HuggingFace]](https://huggingface.co/datasets) |

### CookBench

Long-horizon embodied planning benchmark for complex cooking scenarios.

| Attribute | Details |
|-----------|---------|
| **Focus** | Cooking tasks |
| **Year** | 2025 |
| **Memory Challenge** | Multi-step procedural planning |
| **Links** | [[Paper]](https://arxiv.org/abs/2508.03232) |

---

## Lifelong Learning Datasets

### Humanoid Everyday

Comprehensive robotic dataset for humanoid robots in everyday activities.

| Attribute | Details |
|-----------|---------|
| **Focus** | Full-body humanoid capabilities |
| **Tasks** | Locomotion to dexterous manipulation |
| **Year** | 2025 |
| **Memory Challenge** | Continual skill acquisition |
| **Links** | [[Paper]](https://arxiv.org/abs/2510.08807) |

### RealSource Dataset

Open-source robot dataset from RealMan Robotics.

| Attribute | Details |
|-----------|---------|
| **Environments** | 10 real-world simulated environments |
| **Source** | RealMan Beijing Humanoid Robot Data Training Center |
| **Year** | 2025 |
| **Links** | [[News]](https://www.therobotreport.com/realman-robotics-open-sources-realsource-robot-dataset/) |

---

## Dataset Comparison

| Dataset | Year | Size | Embodiments | Memory Focus |
|---------|------|------|-------------|--------------|
| Open X-Embodiment | 2023 | 1M+ trajectories | 22 | Cross-embodiment |
| DROID | 2023 | 76K trajectories | 1 | Scene diversity |
| BridgeData V2 | 2023 | 60K trajectories | 1 | Multi-skill |
| MIKASA-Robo | 2025 | 32 datasets | 1 | Memory-intensive |
| HM3D | 2021 | 1000 scenes | N/A | Navigation |
| BEHAVIOR-1K | 2024 | 10K demos | N/A | Long-horizon |
| EmbodiedBench | 2025 | 1128 tasks | N/A | MLLM evaluation |

---

## Contributing Datasets

If you know of a relevant dataset that should be included, please:

1. Open an issue or submit a pull request
2. Include all relevant information about the dataset:
   - Name and description
   - Size (trajectories, episodes, hours)
   - Modalities (RGB, depth, proprioception, etc.)
   - Memory-related challenges it addresses
   - Links to paper, download, and project page
3. Ensure the dataset is publicly available or has clear access instructions

---
