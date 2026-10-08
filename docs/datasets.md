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

### RoboMME

Large-scale manipulation dataset and benchmark for memory-augmented robotic generalist policies.

| Attribute | Details |
|-----------|---------|
| **Tasks** | 16 manipulation tasks |
| **Memory Types** | Temporal, spatial, object, and procedural memory |
| **Memory Challenge** | History-dependent manipulation, counting, object permanence, reference, and imitation |
| **Links** | [[Paper]](https://arxiv.org/abs/2603.04639) [[Project]](https://robomme.github.io/) [[GitHub]](https://github.com/RoboMME/robomme_benchmark) |

### RoboMemArena

Large-scale benchmark data for robotic memory with generated trajectories and memory annotations.

| Attribute | Details |
|-----------|---------|
| **Tasks** | 26 long-horizon memory tasks |
| **Annotations** | Subtask instructions and native keyframe annotations |
| **Memory Challenge** | Memory formation, long-horizon partial observability, real-world memory evaluation |
| **Links** | [[Paper]](https://arxiv.org/abs/2605.10921) [[Project]](https://robomemarena.github.io/) |

### RMBench

Memory-dependent manipulation benchmark built on RoboTwin.

| Attribute | Details |
|-----------|---------|
| **Tasks** | 9 manipulation tasks |
| **Platform** | RoboTwin-based simulation |
| **Memory Challenge** | Multiple levels of memory complexity for policy design analysis |
| **Links** | [[Paper]](https://arxiv.org/abs/2603.01229) [[Project]](https://rmbench.github.io/) [[GitHub]](https://github.com/RoboTwin-Platform/RMBench) |

### LIBERO-Mem

Object-centric benchmark suite for non-Markovian robotic manipulation.

| Attribute | Details |
|-----------|---------|
| **Focus** | Object tracking and sequenced subgoals |
| **Memory Challenge** | Object identity, object-level partial observability, persistent interaction history |
| **Links** | [[Paper]](https://arxiv.org/abs/2511.11478) |

### MemMimic

Non-Markovian imitation benchmark introduced with Gated Memory Policy.

| Attribute | Details |
|-----------|---------|
| **Focus** | Memory-dependent visuomotor imitation |
| **Memory Regimes** | In-trial working memory and cross-trial reference memory |
| **Links** | [[Paper]](https://arxiv.org/abs/2604.18933) [[Project]](https://gated-memory-policy.github.io/) |

### RoboMME-Interference

Cross-session benchmark data and evaluation results built on RoboMME task families.

| Attribute | Details |
|-----------|---------|
| **Tasks** | 9 task families with controlled history conditions |
| **Memory Challenge** | Retrieving a relevant prior demonstration among unrelated sessions |
| **Links** | [[Paper]](https://arxiv.org/abs/2606.22338) [[Project]](https://robotmemorybench.com/) [[GitHub]](https://github.com/SoumilRathi/robomme-interference) |

### ReMemBench

Household manipulation benchmark introduced with PRISM for short-term memory research.

| Attribute | Details |
|-----------|---------|
| **Tasks** | 8 household manipulation tasks |
| **Memory Types** | Spatial, prospective, object-associative, and object-set memory |
| **Links** | [[Paper]](https://arxiv.org/abs/2606.16178) [[Project]](https://shahrutav.github.io/short-term-memory/) [[GitHub]](https://github.com/ShahRutav/ReMemBench) |

### MemoryRTBench

RoboTwin 2.0 manipulation task suite introduced with MemoAct.

| Attribute | Details |
|-----------|---------|
| **Tasks** | 6 manipulation tasks |
| **Memory Challenge** | Ordered execution, recall of initial scene state, and repetition tracking |
| **Memory Types** | Sequential, spatial, and episodic memory |
| **Links** | [[Paper]](https://arxiv.org/abs/2603.18494) [[Project]](https://memoact-project.github.io/MemoActPage/) |

### MEMOBench

History-dependent manipulation dataset with annotations for process-level memory diagnostics.

| Attribute | Details |
|-----------|---------|
| **Tasks** | 30 history-dependent tasks |
| **Data** | 1,500 expert demonstrations and executable memory checkpoints |
| **Annotations** | Language descriptions and simulator predicates for storage, update, and compression |
| **Links** | [[Paper]](https://arxiv.org/abs/2609.07047) [[GitHub]](https://github.com/Collab-Gen/MEMOBench) |

### HIDE

RLBench task suite accompanying SEEK for memory-dependent skills under partial observability.

| Attribute | Details |
|-----------|---------|
| **Tasks** | 15 tasks |
| **Memory Challenge** | Repetition counting, historical-state recall, and execution-progress tracking |
| **Availability** | Code and data listed as coming soon on the project page |
| **Links** | [[Paper]](https://arxiv.org/abs/2609.38886) [[Project]](https://nanamma.github.io/HIDE-SEEK/) |

### LIBERO-RoboHarness

Manipulation robustness and task-chaining benchmark introduced with RoboHarness.

| Attribute | Details |
|-----------|---------|
| **Focus** | Frozen VLA adaptation under perceptual noise and environmental variation |
| **Memory Challenge** | Reusing prior execution experience and consolidating failure-derived knowledge |
| **Links** | [[Paper]](https://arxiv.org/abs/2603.24060) [[GitHub]](https://github.com/LZY-1021/RoboHarness) |

### Camo-Dataset

Real-robot UR5e dataset introduced with Chameleon for episodic recall and memory-dependent manipulation.

| Attribute | Details |
|-----------|---------|
| **Platform** | UR5e real robot |
| **Tasks** | Episodic recall, spatial tracking, sequential manipulation |
| **Memory Challenge** | Perceptual aliasing, geometry-grounded recall, long-horizon control |
| **Links** | [[Paper]](https://arxiv.org/abs/2603.24576) |

### MoMani

Automated benchmark and trajectory-generation setup introduced with EchoVLA for long-horizon mobile manipulation.

| Attribute | Details |
|-----------|---------|
| **Focus** | Mobile manipulation with navigation and manipulation |
| **Data Generation** | MLLM-guided planning and feedback-driven refinement, supplemented with real-robot demonstrations |
| **Memory Challenge** | Scene memory, episodic memory, changing spatial contexts |
| **Links** | [[Paper]](https://arxiv.org/abs/2511.18112) |

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

### Sequential-EQA

Scene-level question sequences for studying memory accumulation across embodied question-answering queries.

| Attribute | Details |
|-----------|---------|
| **Data** | 50 HM3D scenes and 498 questions derived from OpenEQA |
| **Protocol** | Scene memory persists across successive questions |
| **Memory Challenge** | Reusing spatially grounded visual-semantic evidence across queries |
| **Links** | [[Paper]](https://arxiv.org/abs/2607.21571) [[GitHub]](https://github.com/jangablox/sequential-eqa) |

### EvoNav-Bench

ProcTHOR-based lifelong navigation task suite with scene changes between subtasks.

| Attribute | Details |
|-----------|---------|
| **Focus** | Repeated navigation in evolving environments |
| **Memory Challenge** | Detecting and updating outdated persistent scene memory |
| **Links** | [[Paper]](https://arxiv.org/abs/2609.08292) |

### MemTransfer

Warehouse navigation benchmark with expert demonstrations supplying prior experience.

| Attribute | Details |
|-----------|---------|
| **Tasks** | 100 cases across 10 task types |
| **Variations** | Starting pose, route availability, history amount, and history relevance |
| **Memory Challenge** | Transferring stored experience to changed execution conditions |
| **Links** | [[Paper]](https://arxiv.org/abs/2609.32313) |

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
| RoboMME-Interference | 2026 | 9 task families | N/A | Cross-session interference |
| ReMemBench | 2026 | 8 tasks | N/A | Four short-term memory categories |
| MemoryRTBench | 2026 | 6 tasks | N/A | Sequential/Spatial/Episodic |
| MEMOBench | 2026 | 30 tasks, 1,500 demonstrations | N/A | Storage/Update/Compression |
| HIDE | 2026 | 15 tasks; data coming soon | N/A | Hidden task states and skill progress |
| LIBERO-RoboHarness | 2026 | Robustness and task chaining | N/A | Experience reuse and failure memory |
| Sequential-EQA | 2026 | 50 scenes, 498 questions | N/A | Persistent visual-semantic evidence |
| EvoNav-Bench | 2026 | Evolving navigation sequences | N/A | Updating stale scene memory |
| MemTransfer | 2026 | 100 cases, 10 task types | N/A | Memory transfer |
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
