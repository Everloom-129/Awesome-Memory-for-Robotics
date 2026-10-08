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

#### MIKASA-Robo-VLA

Extension of MIKASA-Robo evaluating Vision-Language-Action models on memory-intensive tabletop manipulation tasks.

| Attribute | Details |
|-----------|---------|
| **Tasks** | 90 memory tasks across 10 memory types |
| **Memory Types** | Object, Spatial, Sequential, Capacity, and more |
| **Platform** | ManiSkill3 with language-conditioned variants |
| **Data** | 6M+ transitions for reproducible VLA training |
| **Venue** | ICLR 2026 |
| **Links** | [[Paper]](https://arxiv.org/abs/2502.10550) [[Project]](https://mikasarobo.github.io/) [[Code]](https://github.com/CognitiveAISystems/MIKASA-Robo) |

#### RoboCerebra

Large-scale benchmark for long-horizon robotic manipulation with System 2 reasoning.

| Attribute | Details |
|-----------|---------|
| **Focus** | System 2 capabilities in manipulation |
| **Tasks** | Long-horizon tasks with large state spaces |
| **Year** | 2025 |
| **Links** | [[Paper]](https://arxiv.org/abs/2506.06677) |

#### RoboMemArena

Large-scale robotic memory benchmark with multimodal memory annotations and paired real-world tasks.

| Attribute | Details |
|-----------|---------|
| **Tasks** | 26 long-horizon tasks |
| **Trajectory Length** | Average trajectory length exceeds 1,000 steps |
| **Memory Challenge** | Partial observability, memory formation, keyframe recall, long-horizon task dynamics |
| **Real-World Evaluation** | Paired real-world memory tasks |
| **Year** | 2026 |
| **Links** | [[Paper]](https://arxiv.org/abs/2605.10921) [[Project]](https://robomemarena.github.io/) |

#### RoboMME

Standardized benchmark for evaluating memory in robotic generalist policies.

| Attribute | Details |
|-----------|---------|
| **Tasks** | 16 manipulation tasks |
| **Memory Types** | Temporal, spatial, object, and procedural memory |
| **Focus** | Comparing memory representations and integration strategies for VLA policies |
| **Venue** | ICML 2026 |
| **Links** | [[Paper]](https://arxiv.org/abs/2603.04639) [[Project]](https://robomme.github.io/) [[Code]](https://github.com/RoboMME/robomme_benchmark) |

#### RoboMME-Interference

Cross-session extension of RoboMME testing whether relevant prior demonstrations remain usable among unrelated robot experiences.

| Attribute | Details |
|-----------|---------|
| **Tasks** | 9 RoboMME task families |
| **Memory Challenge** | Cross-session interference and retrieval of relevant prior experience |
| **Protocol** | Vary the number of unrelated sessions in the history buffer |
| **Year** | 2026 |
| **Links** | [[Paper]](https://arxiv.org/abs/2606.22338) [[Project]](https://robotmemorybench.com/) [[Code]](https://github.com/SoumilRathi/robomme-interference) |

#### RMBench

Simulation benchmark for memory-dependent robotic manipulation policy design.

| Attribute | Details |
|-----------|---------|
| **Tasks** | 9 manipulation tasks |
| **Focus** | Multiple levels of memory complexity and controlled ablations with Mem-0 |
| **Platform** | RoboTwin-based simulation |
| **Year** | 2026 |
| **Links** | [[Paper]](https://arxiv.org/abs/2603.01229) [[Project]](https://rmbench.github.io/) [[Code]](https://github.com/RoboTwin-Platform/RMBench) |

#### LIBERO-Mem

Object-centric non-Markovian manipulation suite for stress-testing object-level memory.

| Attribute | Details |
|-----------|---------|
| **Focus** | Object tracking and temporally sequenced subgoals |
| **Memory Challenge** | Object-level partial observability and visually similar object instances |
| **Venue** | AAAI 2026 |
| **Links** | [[Paper]](https://arxiv.org/abs/2511.11478) |

#### MemMimic

Non-Markovian benchmark introduced with Gated Memory Policy.

| Attribute | Details |
|-----------|---------|
| **Focus** | Imitation tasks with varying memory requirements |
| **Memory Regimes** | In-trial working memory and cross-trial reference memory |
| **Year** | 2026 |
| **Links** | [[Paper]](https://arxiv.org/abs/2604.18933) [[Project]](https://gated-memory-policy.github.io/) |

#### RuleSafe

Non-Markovian articulated manipulation benchmark introduced with VQ-Memory.

| Attribute | Details |
|-----------|---------|
| **Focus** | Safe unlocking tasks with key locks, password locks, and logic locks |
| **Memory Challenge** | Temporal modeling, task-phase memory, multi-stage reasoning |
| **Year** | 2026 |
| **Links** | [[Paper]](https://arxiv.org/abs/2603.09513) [[Project]](https://vqmemory.github.io/) |

#### LIBERO-Recovery

Perturbation-injection protocol introduced with HELM for evaluating memory-conditioned failure recovery.

| Attribute | Details |
|-----------|---------|
| **Focus** | Long-horizon VLA recovery under controlled perturbations |
| **Memory Challenge** | Episodic memory, pre-execution verification, rollback and replanning |
| **Year** | 2026 |
| **Links** | [[Paper]](https://arxiv.org/abs/2604.18791) |

#### ReMemBench

Household manipulation benchmark introduced with PRISM to evaluate distinct short-term memory requirements.

| Attribute | Details |
|-----------|---------|
| **Tasks** | 8 household manipulation tasks |
| **Memory Types** | Spatial, prospective, object-associative, and object-set memory |
| **Year** | 2026 |
| **Links** | [[Paper]](https://arxiv.org/abs/2606.16178) [[Project]](https://shahrutav.github.io/short-term-memory/) [[Code]](https://github.com/ShahRutav/ReMemBench) |

#### MemoryRTBench

Memory-dependent manipulation benchmark introduced with MemoAct.

| Attribute | Details |
|-----------|---------|
| **Tasks** | 6 manipulation tasks |
| **Memory Types** | Sequential, spatial, and episodic memory |
| **Platform** | RoboTwin 2.0 |
| **Year** | 2026 |
| **Links** | [[Paper]](https://arxiv.org/abs/2603.18494) [[Project]](https://memoact-project.github.io/MemoActPage/) |

#### MEMOBench

Process-level benchmark that distinguishes memory errors from failures to execute a manipulation.

| Attribute | Details |
|-----------|---------|
| **Tasks** | 30 history-dependent tasks |
| **Diagnostics** | Executable checkpoints for memory storage, update, and compression |
| **Metrics** | Memory Storage Rate, Memory Update Rate, Memory Compression Rate, and task success |
| **Year** | 2026 |
| **Links** | [[Paper]](https://arxiv.org/abs/2609.07047) [[Code]](https://github.com/Collab-Gen/MEMOBench) |

#### HIDE

Skill-level manipulation memory benchmark accompanying the SEEK framework.

| Attribute | Details |
|-----------|---------|
| **Tasks** | 15 tasks |
| **Memory Challenge** | Repetition counting, historical-state recall, and execution-progress tracking |
| **Platform** | RLBench |
| **Availability** | Code and data listed as coming soon on the project page |
| **Year** | 2026 |
| **Links** | [[Paper]](https://arxiv.org/abs/2609.38886) [[Project]](https://nanamma.github.io/HIDE-SEEK/) |

#### LIBERO-RoboHarness

Robustness benchmark introduced with RoboHarness for evaluating memory-assisted adaptation of frozen VLA policies.

| Attribute | Details |
|-----------|---------|
| **Focus** | Robustness to perceptual noise and environmental variation, including long-horizon task chaining |
| **Memory Challenge** | Retrieval of prior execution traces, failure attribution, and reuse of consolidated experience |
| **Venue** | IROS 2026 |
| **Links** | [[Paper]](https://arxiv.org/abs/2603.24060) [[Code]](https://github.com/LZY-1021/RoboHarness) |

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

#### MemoryArena

Benchmark for evaluating agent memory across interdependent multi-session agentic tasks, where agents acquire memory during interaction and rely on it in later sessions.

| Attribute | Details |
|-----------|---------|
| **Tasks** | Web navigation, planning with constraints, information search, formal reasoning |
| **Memory Challenge** | Cross-session memory acquisition and retrieval in interdependent task chains |
| **Key Finding** | Agents strong on long-context benchmarks fail at interdependent task structures |
| **Year** | 2026 |
| **Links** | [[Paper]](https://arxiv.org/abs/2602.16313) |

#### STARBench

A benchmark for spatiotemporal object search in dynamic household environments.

| Attribute | Details |
|-----------|---------|
| **Tasks** | 360 tasks across visible, interactive, and commonsense settings |
| **Focus** | Spatiotemporal object search |
| **Platform** | Simulated and real (Tiago robot) |
| **Year** | 2025 |
| **Links** | [[Paper]](https://arxiv.org/abs/2511.14004) [[Project]](https://amrl.cs.utexas.edu/STAR/) |

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

#### Sequential-EQA

Sequential embodied question answering evaluation introduced in *Beyond Episodic Evaluation*, carrying scene memory across questions.

| Attribute | Details |
|-----------|---------|
| **Data** | 50 HM3D scenes with 498 questions derived from OpenEQA |
| **Protocol** | Paired episodic and sequential runs on the same scene-level question sequences |
| **Memory Challenge** | Accumulating and reusing spatially grounded visual-semantic evidence |
| **Real-World Evaluation** | Mobile robot validation |
| **Venue** | IROS 2026 |
| **Links** | [[Paper]](https://arxiv.org/abs/2607.21571) [[Code]](https://github.com/jangablox/sequential-eqa) |

#### EvoNav-Bench

Lifelong navigation benchmark in which the environment changes between navigation subtasks.

| Attribute | Details |
|-----------|---------|
| **Platform** | ProcTHOR |
| **Protocol** | Controlled scene modifications between tasks in a persistent environment |
| **Memory Challenge** | Updating stale scene observations while preserving useful prior experience |
| **Year** | 2026 |
| **Links** | [[Paper]](https://arxiv.org/abs/2609.08292) |

#### MemTransfer

Navigation benchmark testing whether stored experience transfers when test conditions differ from demonstrations.

| Attribute | Details |
|-----------|---------|
| **Tasks** | 100 navigation cases across 10 task types |
| **Platform** | Simulated warehouse |
| **Protocol** | Vary starting pose, route availability, and the amount and relevance of history |
| **Memory Challenge** | Reusing experience under mismatched execution conditions |
| **Year** | 2026 |
| **Links** | [[Paper]](https://arxiv.org/abs/2609.32313) |

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

#### FindingDory: A Benchmark to Evaluate Memory in Embodied Agents

Evaluates tasks that demand fine-grained recall and multi-hop reasoning over past observations.

| Attribute | Details |
|-----------|---------|
| **Focus** | Long-range embodied tasks |
| **Year** | 2025 |
| **Links** | [[Paper]](https://arxiv.org/abs/2506.15635) |

---

## Evaluation Protocols

### Standardized Testing

| Protocol | Description |
|----------|-------------|
| **Held-out Test Sets** | Evaluation on unseen scenes/tasks |
| **Cross-validation** | K-fold validation across environments |
| **Ablation Studies** | Systematic removal of memory components |
| **Baseline Comparisons** | Comparison with memoryless baselines |

### Counterfactual Memory Audit (CMA)

CMA tests whether history guides the action warranted by a robot's past. It pairs different histories that lead to the same verified current input, queries a frozen policy with shared randomness, and evaluates the saved actions under both histories. The audit distinguishes action sensitivity from correct choice, physical value, and reliability for each pair. [[Paper]](https://arxiv.org/abs/2609.27247)

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
| MIKASA-Robo-VLA | 2026 | 90 | 10 memory types, language-conditioned | Low |
| MemoryArena | 2026 | Multi-session agentic tasks | Cross-session interdependent memory | High |
| MemoryBench | 2025 | 3 | Spatial/Backward Reasoning | Low |
| EmbodiedBench | 2025 | 1,128 | 6 capabilities | High + Low |
| RoboCerebra | 2025 | Long-horizon | System 2 reasoning | High |
| VLABench | 2025 | Language-conditioned | Long-horizon | High |
| RoboMemArena | 2026 | 26 | Memory annotations and long-horizon physical evaluation | High + Low |
| RoboMME | 2026 | 16 | Temporal/Spatial/Object/Procedural memory | Low |
| RoboMME-Interference | 2026 | 9 task families | Cross-session interference and retrieval | Low |
| ReMemBench | 2026 | 8 | Spatial/Prospective/Object-Associative/Object-Set memory | Low |
| MemoryRTBench | 2026 | 6 | Sequential/Spatial/Episodic memory | Low |
| MEMOBench | 2026 | 30 | Storage/Update/Compression diagnostics | Low |
| HIDE | 2026 | 15 | Repetition/Historical recall/Execution progress | Low |
| LIBERO-RoboHarness | 2026 | Robustness and task chaining | Failure attribution and experience reuse | High + Low |
| Sequential-EQA | 2026 | 498 questions in 50 scenes | Persistent visual-semantic scene memory | High |
| EvoNav-Bench | 2026 | Lifelong navigation sequences | Stale memory and scene updates | High |
| MemTransfer | 2026 | 100 cases, 10 task types | Memory transfer under changed conditions | High |
| RMBench | 2026 | 9 | Memory complexity and policy design ablations | Low |
| LIBERO-Mem | 2026 | Object-centric tasks | Object-level non-Markovian memory | Low |
| MemMimic | 2026 | Non-Markovian imitation | In-trial and cross-trial memory | Low |
| RuleSafe | 2026 | Articulated manipulation | Non-Markovian task-phase memory | Low |
| LIBERO-Recovery | 2026 | Failure recovery | Episodic memory and rollback | Low |
| BEHAVIOR-1K | 2024 | 1,000 | State tracking | High |
| Mini-BEHAVIOR | 2023 | 20 | Long-horizon | High |
| ReMEmbR | 2025 | Navigation QA | Spatio-temporal | High |
| STARBench | 2025 | 360 | Spatiotemporal object search | High + Low |

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
