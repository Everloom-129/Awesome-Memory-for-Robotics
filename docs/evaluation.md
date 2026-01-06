# Evaluation of Memory Systems in Robotics

Author: Jie Wang

This document outlines evaluation methodologies, metrics, and benchmarks for assessing memory systems in robotics, with emphasis on capabilities that pose genuine challenges to memory mechanisms.

## Overview

Evaluating memory systems in robotics requires considering multiple dimensions: task performance, memory efficiency, generalization, and long-term robustness. This document organizes evaluation approaches by the specific memory challenges they address and provides references to state-of-the-art benchmarks.

---

## Key Memory Challenges

Effective evaluation of memory systems should assess capabilities that genuinely require memory mechanisms:

| Challenge | Description | Why Memory Matters |
|-----------|-------------|-------------------|
| **Partial Observability** | Occlusions, hidden states, deferred rewards | Agent must remember past observations to infer current state |
| **Long-Horizon Tasks** | Multi-step tasks requiring recall of earlier observations/instructions | Working memory must persist across many timesteps |
| **Distribution Shift** | New scenes, objects, layouts | Semantic memory must generalize learned knowledge |
| **Recovery & Retry** | Diagnosing failures and retrying | Episodic memory of mistakes enables learning from failure |
| **Object Permanence** | Tracking objects that leave field of view | Spatial memory must maintain object locations |
| **Temporal Reasoning** | Understanding sequences and causality | Sequential memory for action-outcome relationships |

---

## Evaluation Metrics

### Task Performance Metrics

Standard metrics for measuring overall task success:

| Metric | Description | Formula/Definition |
|--------|-------------|-------------------|
| **Success Rate (SR)** | Percentage of tasks completed successfully | `SR = successful_episodes / total_episodes` |
| **Goal Condition Success (GCS)** | Percentage of goal conditions satisfied | `GCS = satisfied_conditions / total_conditions` |
| **Task Completion Time** | Time required to complete tasks | Mean/median episode duration |
| **Path Length Ratio** | Efficiency of navigation path | `PLR = actual_path / optimal_path` |
| **SPL (Success weighted by Path Length)** | Success normalized by path efficiency | `SPL = SR × (optimal_path / max(actual_path, optimal_path))` |

### Memory-Specific Metrics

Metrics designed to evaluate memory capabilities:

| Metric | Description | Applicable Tasks |
|--------|-------------|------------------|
| **Object Memory Accuracy** | Correct recall of object properties after occlusion | ShellGame, RememberColor/Shape |
| **Spatial Memory Accuracy** | Correct recall of spatial positions | TakeItBack, RotateLenient |
| **Sequential Memory Accuracy** | Correct recall of ordered sequences | ChainOfColors, SeqOfColors |
| **Memory Capacity** | Maximum items that can be reliably stored | BunchOfColors (3/5/7 items) |
| **Retrieval Latency** | Time to retrieve relevant memories | Real-time systems |
| **Memory Persistence** | Retention over extended time periods | Lifelong learning tasks |

### Generalization Metrics

Metrics for assessing transfer and generalization:

| Metric | Description |
|--------|-------------|
| **Zero-shot Performance** | Performance on unseen tasks/environments without fine-tuning |
| **Few-shot Learning** | Performance with limited examples (1-10 demonstrations) |
| **Cross-Embodiment Transfer** | Performance when transferring to different robot platforms |
| **Scene Generalization** | Performance in novel environments |
| **Object Generalization** | Performance with unseen object categories |

### Long-term Performance Metrics

Metrics for continual and lifelong learning:

| Metric | Description |
|--------|-------------|
| **Catastrophic Forgetting Rate** | Performance degradation on old tasks after learning new ones |
| **Forward Transfer** | Improvement on new tasks due to prior learning |
| **Backward Transfer** | Improvement on old tasks after learning new ones |
| **Average Accuracy** | Mean performance across all learned tasks |
| **Learning Curve Area** | Cumulative performance during learning |

---

## Evaluation Benchmarks

### Memory-Intensive Manipulation Benchmarks

#### MemoryBench

Benchmark dataset designed to evaluate spatial memory and action recall in robotic manipulation, accompanying the SAM2Act framework.

| Attribute | Details |
|-----------|---------|
| **Tasks** | 3 memory-dependent tasks: Reopen Drawer, Put Block Back, Rearrange Block |
| **Memory Types** | 3D spatial memory (z-axis), 2D spatial memory (x-y plane), backward reasoning |
| **Platform** | RLBench (same version as PerAct) |
| **Data** | 100 training + 25 test episodes per task |
| **Year** | 2025 |
| **Links** | [[Dataset]](https://huggingface.co/datasets/hqfang/memorybench) [[Paper]](https://arxiv.org/abs/2501.18564) [[Code]](https://github.com/sam2act/sam2act) |

**Task Descriptions:**

| Task | Memory Challenge | Description |
|------|------------------|-------------|
| Reopen Drawer | 3D Spatial (z-axis) | Tests spatial memory along the z-axis |
| Put Block Back | 2D Spatial (x-y plane) | Evaluates spatial memory in the x-y plane |
| Rearrange Block | Backward Reasoning | Requires reasoning based on prior actions |



#### MIKASA-Robo

The first benchmark specifically designed for testing agent memory in robotic manipulation.

| Attribute | Details |
|-----------|---------|
| **Tasks** | 32 memory-intensive tasks in 12 groups |
| **Memory Types** | Object, Spatial, Sequential, Capacity |
| **Platform** | ManiSkill3 (GPU parallelization) |
| **Metrics** | Success rate per memory type |
| **Links** | [[Paper]](https://arxiv.org/abs/2502.10550) [[Code]](https://github.com/CognitiveAISystems/MIKASA-Robo) |

**Task Categories:**

| Task Group | Memory Type | Description |
|------------|-------------|-------------|
| ShellGame | Object | Track ball position under moving cups |
| Intercept | Spatial | Estimate velocity from remembered positions |
| RotateLenient/Strict | Spatial/Object | Remember initial orientation |
| TakeItBack | Spatial | Return object to initial position |
| RememberColor/Shape | Object | Recall visual properties |
| BunchOfColors | Capacity | Remember multiple simultaneous items |
| SeqOfColors | Capacity | Remember sequential presentations |
| ChainOfColors | Sequential | Recall ordered sequence |

#### RoboCerebra

Large-scale benchmark for long-horizon robotic manipulation with System 2 reasoning.

| Attribute | Details |
|-----------|---------|
| **Focus** | System 2 capabilities in manipulation |
| **Tasks** | Long-horizon tasks with large state spaces |
| **Year** | 2025 |
| **Links** | [[Paper]](https://arxiv.org/abs/2506.06677) |

#### VLABench

Large-scale benchmark for language-conditioned robotics manipulation.

| Attribute | Details |
|-----------|---------|
| **Focus** | Language-conditioned long-horizon manipulation |
| **Features** | Standardized evaluation suite |
| **Year** | 2025 |
| **Links** | [[Paper]](https://openaccess.thecvf.com/content/ICCV2025/html/Zhang_VLABench_A_Large-Scale_Benchmark_for_Language-Conditioned_Robotics_Manipulation_with_Long-Horizon_ICCV_2025_paper.html) |

### Embodied Agent Benchmarks

#### EmbodiedBench

Comprehensive benchmark for evaluating MLLMs as embodied agents.

| Attribute | Details |
|-----------|---------|
| **Tasks** | 1,128 testing tasks |
| **Environments** | EB-ALFRED, EB-Habitat, EB-Navigation, EB-Manipulation |
| **Action Levels** | High-level (planning) and Low-level (control) |
| **Links** | [[Paper]](https://arxiv.org/abs/2502.09560) [[Project]](https://embodiedbench.github.io/) |

**Six Critical Capabilities Evaluated:**

| Capability | Description | Memory Relevance |
|------------|-------------|------------------|
| Basic Task Solving | Fundamental task completion | Baseline performance |
| Commonsense Reasoning | World knowledge application | Semantic memory |
| Complex Instruction Understanding | Multi-step instruction parsing | Working memory |
| Spatial Awareness | 3D spatial reasoning | Spatial memory |
| Visual Perception | Object recognition and tracking | Perceptual memory |
| Long-Horizon Planning | Multi-step task planning | Episodic + working memory |

**Error Types Identified:**

| Error Type | Stage | Description |
|------------|-------|-------------|
| Perception Errors | Visual state description | Incorrect observation of environment |
| Reasoning Errors | Reflection and reasoning | Failure to apply correct logic |
| Planning Errors | Plan generation | Incorrect action sequencing |

#### Embodied Arena

Flexible integration of 22 evaluation benchmarks across three core leaderboard types.

| Attribute | Details |
|-----------|---------|
| **Benchmarks** | 22 integrated benchmarks |
| **Features** | Consistent evaluation protocols |
| **Links** | [[Project]](https://embodied-arena.com/) |

#### Embodied Agent Interface

Benchmark for LLMs in embodied decision making.

| Attribute | Details |
|-----------|---------|
| **Focus** | LLM-based embodied reasoning |
| **Venue** | NeurIPS 2024 |
| **Links** | [[Paper]](https://proceedings.neurips.cc/paper_files/paper/2024/hash/b631da756d1573c24c9ba9c702fde5a9-Abstract-Datasets_and_Benchmarks_Track.html) |

### Navigation Benchmarks

#### ReMEmbR

Building and reasoning over long-horizon spatio-temporal memory for robot navigation.

| Attribute | Details |
|-----------|---------|
| **Dataset** | NaVQA (navigation video QA) |
| **Focus** | Perceptual question-answering |
| **Memory Challenge** | Long-horizon spatio-temporal reasoning |
| **Links** | [[Paper]](https://ieeexplore.ieee.org/abstract/document/11127706/) [[Project]](https://rasc.usc.edu/blog/remembr/) |

#### HM3D-OVON

Open Vocabulary Object Goal Navigation benchmark.

| Attribute | Details |
|-----------|---------|
| **Focus** | Open-vocabulary navigation |
| **Memory Challenge** | Semantic generalization |
| **Links** | [[Paper]](https://ieeexplore.ieee.org/document/10802709/) |

### World Model Benchmarks

#### EWMBench (Embodied World Model Benchmark)

Evaluation suite for embodied world models.

| Attribute | Details |
|-----------|---------|
| **Dimensions** | Physical realism, dynamic motion, semantic alignment |
| **Year** | 2025 |
| **Links** | [[Info]](https://www.emergentmind.com/topics/ewmbench-embodied-world-model-benchmark) |

### Long-Horizon Task Benchmarks

#### BEHAVIOR-1K

Human-centered embodied AI benchmark with 1,000 everyday activities.

| Attribute | Details |
|-----------|---------|
| **Activities** | 1,000 household tasks |
| **Demonstrations** | 10,000 human trajectories |
| **Memory Challenge** | Long-horizon state tracking |
| **Links** | [[Paper]](https://arxiv.org/abs/2403.09227) [[Project]](https://behavior.stanford.edu/) |

#### Mini-BEHAVIOR

Procedurally generated benchmark for long-horizon decision-making.

| Attribute | Details |
|-----------|---------|
| **Tasks** | 20 long-horizon tasks |
| **Features** | Procedural generation |
| **Links** | [[Paper]](https://arxiv.org/abs/2310.01824) |

#### Benchmark for Observation Space Shift in Long-Horizon Task

Evaluates visual-servoing robots on previously unseen long-horizon tasks.

| Attribute | Details |
|-----------|---------|
| **Focus** | Observation space shift |
| **Year** | 2025 |
| **Links** | [[Paper]](https://arxiv.org/abs/2502.15679) |

---

## Evaluation Protocols

### Standardized Testing

| Protocol | Description |
|----------|-------------|
| **Held-out Test Sets** | Evaluation on unseen scenes/tasks |
| **Cross-validation** | K-fold validation across environments |
| **Ablation Studies** | Systematic removal of memory components |
| **Baseline Comparisons** | Comparison with memoryless baselines |

### Real-World Evaluation

| Protocol | Description |
|----------|-------------|
| **Sim-to-Real Transfer** | Performance gap between simulation and reality |
| **Field Tests** | Evaluation in unstructured real environments |
| **Long-term Deployment** | Extended operation (hours/days) |
| **User Studies** | Human evaluation of robot behavior |

### Reliability Metrics

Recent work on robot reliability in real-world settings:

| Metric | Description | Reference |
|--------|-------------|-----------|
| **Drop Rate** | Frequency of dropped items | Science Robotics 2025 |
| **Recovery Rate** | Success of failure recovery | - |
| **Mean Time Between Failures** | Reliability measure | - |

---

## Benchmark Comparison

| Benchmark | Year | Tasks | Memory Focus | Action Level |
|-----------|------|-------|--------------|--------------|
| MIKASA-Robo | 2025 | 32 | Object/Spatial/Sequential/Capacity | Low |
| MemoryBench | 2025 | 3 | Spatial/Backward Reasoning | Low |
| EmbodiedBench | 2025 | 1,128 | 6 capabilities | High + Low |
| RoboCerebra | 2025 | Long-horizon | System 2 reasoning | High |
| VLABench | 2025 | Language-conditioned | Long-horizon | High |
| BEHAVIOR-1K | 2024 | 1,000 | State tracking | High |
| Mini-BEHAVIOR | 2023 | 20 | Long-horizon | High |
| ReMEmbR | 2025 | Navigation QA | Spatio-temporal | High |

---

## Evaluation Tools

### AutoEval

Autonomous evaluation framework for generalist robot manipulation.

| Feature | Description |
|---------|-------------|
| **Metrics** | Binary success, per-episode success rate |
| **Automation** | Autonomous evaluation pipeline |
| **Links** | [[Paper]](https://www2.eecs.berkeley.edu/Pubs/TechRpts/2025/EECS-2025-42.pdf) |

### RoboEval

Structured evaluation for robotic manipulation with behavioral metrics.

| Feature | Description |
|---------|-------------|
| **Metrics** | Behavioral metrics beyond binary success |
| **Finding** | Behavioral metrics correlate with success in >50% of task-metric pairs |
| **Links** | [[Project]](https://robo-eval.github.io/) |

### RoboAfford-Eval

Benchmark correlating affordance accuracy with real-robot performance.

| Feature | Description |
|---------|-------------|
| **Correlation** | Affordance accuracy → pick-and-place SR (up to 61.4%) |
| **Links** | [[Info]](https://www.emergentmind.com/topics/roboafford-eval-benchmark) |

---
