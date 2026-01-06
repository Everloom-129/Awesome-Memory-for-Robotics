# Taxonomy of Memory for Robotics

Author: Jie Wang

This document provides a comprehensive taxonomy of memory approaches and techniques used in robotics research, organized by multiple dimensions including temporal scope, function, implementation, and application domain.

## Overview

Memory in robotics serves as a fundamental capability enabling robots to store, retrieve, and utilize past experiences for improved perception, planning, and decision-making. This taxonomy organizes memory approaches by their characteristics, use cases, and implementation strategies, drawing from cognitive science foundations and recent advances in embodied AI.

---

## Categories by Temporal Scope

### Working Memory (Short-term)

Working memory maintains task-relevant information during immediate execution, typically within a single episode. It enables robots to track object states, maintain spatial awareness, and hold intermediate computation results.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| Scaling Short-Term Memory of Visuomotor Policies (PRISM) | NeurIPS | 2025 | [[Paper]](https://openreview.net/forum?id=5SMNtmJFGa) |
| MemAgent: Reshaping Long-Context LLM with Multi-Conv RL-based Memory Agent | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2505.00675) |
| Memo: Training Memory-Efficient Embodied Agents | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2510.19732) |

### Episodic Memory

Episodic memory stores specific events and experiences from the robot's past, enabling recall of particular situations, trajectories, and outcomes. This type of memory is crucial for learning from demonstrations and experience replay.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| Episodic Memory Banks for Lifelong Robot Learning | CoRL | 2025 | [[Paper]](https://openreview.net/forum?id=BBgDA4y0B9) |
| Deep Episodic Memory: Encoding, Recalling, and Predicting Episodic Experiences for Robot Action Execution | IEEE RA-L | 2018 | [[Paper]](https://ieeexplore.ieee.org/abstract/document/8421022/) |
| Synthesizing the Temporal Self: Robotic Models of Episodic and Semantic Memory | Phil. Trans. R. Soc. B | 2024 | [[Paper]](https://royalsocietypublishing.org/doi/10.1098/rstb.2023.0415) |
| An Episodic Long-Term Memory for Robots: The Bender Case | RoboCup | 2016 | [[Paper]](https://www.researchgate.net/publication/308925380) |
| Storing and Retrieving Perceptual Episodic Memories for Long-Term Manipulation Tasks | IROS | 2017 | [[Paper]](https://ieeexplore.ieee.org/abstract/document/8023492/) |

### Semantic Memory

Semantic memory represents general knowledge, facts, object affordances, and task structures independent of specific experiences. It enables robots to understand object categories, spatial relationships, and action preconditions.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| ART Neural Network-based Integration of Episodic Memory and Semantic Memory for Task Planning | Autonomous Robots | 2019 | [[Paper]](https://link.springer.com/article/10.1007/s10514-019-09868-x) |
| Utilizing a Deep Neural Network for Robot Semantic Classification | Scientific Reports | 2025 | [[Paper]](https://www.nature.com/articles/s41598-025-07921-7) |
| Learning Spatially Semantic Representations for Cognitive Robot Navigation | Robotics and Autonomous Systems | 2013 | [[Paper]](https://www.sciencedirect.com/science/article/pii/S0921889013001346) |

### Long-term / Lifelong Memory

Long-term memory enables continuous accumulation of knowledge across tasks and sessions, supporting lifelong learning and adaptation without catastrophic forgetting.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| Preserving and Combining Knowledge in Robotic Lifelong Reinforcement Learning | Nature Machine Intelligence | 2025 | [[Paper]](https://www.nature.com/articles/s42256-025-00983-2) |
| Towards General Purpose Robots at Scale: Lifelong Learning and Learning to Use Memory | PhD Thesis | 2024 | [[Paper]](https://arxiv.org/abs/2501.10395) |
| Online Active Continual Learning for Robotic Lifelong Object Recognition | IEEE T-NNLS | 2023 | [[Paper]](https://ieeexplore.ieee.org/document/10251045/) |
| DRAE: Dynamic Retrieval-Augmented Expert Networks for Lifelong Learning and Task Adaptation in Robotics | ACL | 2025 | [[Paper]](https://aclanthology.org/2025.acl-long.1127/) |
| Effective Generative Replay with Strong Memory for Continual Learning | Knowledge-Based Systems | 2025 | [[Paper]](https://www.sciencedirect.com/science/article/abs/pii/S0950705125005234) |

---

## Categories by Representation

### Key-Value / Slot Memory

Explicit memory slots that store and retrieve information using attention mechanisms or addressing schemes.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| Mem0: Building Production-Ready AI Agents with Scalable Long-Term Memory | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2505.00675) [[Code]](https://github.com/mem0ai/mem0) |
| MemOS: An Operating System for Memory-Augmented Generation in LLMs | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2505.00675) |
| LightMem: Lightweight and Efficient Memory-Augmented Generation | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2505.00675) |

### Neural State Memory (RNN/Transformer)

Memory encoded in recurrent neural network hidden states or transformer attention patterns.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| Long Horizon Episodic Decision Making for Cognitively Inspired Robots | Cognitive Systems Research | 2024 | [[Paper]](https://www.sciencedirect.com/science/article/pii/S1389041724000536) |
| Scaling Short-Term Memory of Visuomotor Policies (PRISM) | NeurIPS | 2025 | [[Paper]](https://openreview.net/forum?id=5SMNtmJFGa) |

### Retrieval-based Memory (Vector DB)

Memory systems using embedding-based retrieval over stored experiences or knowledge.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| STRAP: Robot Sub-Trajectory Retrieval for Augmented Policy Learning | ICLR | 2025 | [[Paper]](https://arxiv.org/abs/2412.15182) [[Project]](https://weirdlabuw.github.io/strap/) |
| Retrieval-Augmented Policy Training for Cooperative Push Manipulation | IEEE RA-L | 2024 | [[Paper]](https://ieeexplore.ieee.org/document/10801334/) |
| Retrieval-Augmented Hierarchical In-Context Reinforcement Learning | ICRA | 2025 | [[Paper]](https://ieeexplore.ieee.org/abstract/document/11128105/) |

### 3D Spatial Memory (Maps / NeRF / Gaussian Splats)

Memory representations encoding 3D spatial information about the environment.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| 3D-Mem: 3D Scene Memory for Embodied Exploration and Reasoning | CVPR | 2025 | [[Paper]](https://arxiv.org/abs/2411.17735) [[Project]](https://umass-embodied-agi.github.io/3D-Mem/) |
| 3DLLM-Mem: Long-Term Spatial-Temporal Memory for Embodied 3D LLM | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2505.22657) |
| Vision to Geometry: 3D Spatial Memory for Sequential Embodied MLLM Reasoning | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2512.02458) |
| What Is The Best 3D Scene Representation for Robotics? | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2512.03422) |
| mindmap: 3D Diffusion Policy with Semantic 3D Reconstruction | Hugging Face | 2025 | [[Model]](https://huggingface.co/nvidia/PhysicalAI-Robotics-mindmap-Checkpoints) |

### Symbolic Graphs (Scene Graphs / Task Graphs)

Structured symbolic representations capturing object relationships and task structures.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| Hierarchical Representations and Explicit Memory: Learning Navigation Policies on 3D Scene Graphs | ICRA | 2022 | [[Paper]](https://ieeexplore.ieee.org/abstract/document/9812179/) |
| Scene Representations for Robotic Spatial Perception | Annual Review of Control | 2024 | [[Paper]](https://www.annualreviews.org/content/journals/10.1146/annurev-control-040423-030709) |

---

## Categories by Usage

### Policy Conditioning (Retrieve-then-Act)

Memory used to condition policy execution by retrieving relevant past experiences.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| STRAP: Robot Sub-Trajectory Retrieval for Augmented Policy Learning | ICLR | 2025 | [[Paper]](https://arxiv.org/abs/2412.15182) |
| MemoryVLA: Dual-Memory for Robotic Manipulation | arXiv | 2025 | [[Paper]](https://www.emergentmind.com/topics/memoryvla) |
| Planning with an Embodied Learnable Memory | NeurIPS | 2025 | [[Paper]](https://openreview.net/forum?id=79BOATBal9) |

### Planning (Search over Remembered States)

Memory supporting planning by maintaining and searching over possible world states.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| Ctrl-World: A Controllable Generative World Model for Robot Manipulation | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2510.10125) [[Project]](https://ctrl-world.github.io/) |
| FOCUS: Object-Centric World Models for Robotic Manipulation | Frontiers in Neurorobotics | 2025 | [[Paper]](https://www.frontiersin.org/articles/10.3389/fnbot.2025.1585386/full) |
| IRASim: A Fine-Grained World Model for Robot Manipulation | ICCV | 2025 | [[Paper]](https://openaccess.thecvf.com/content/ICCV2025/papers/Zhu_IRASim_A_Fine-Grained_World_Model_for_Robot_Manipulation_ICCV_2025_paper.pdf) |

### Perception (Temporal Integration / Object Permanence)

Memory enabling temporal integration of sensory information and tracking of occluded objects.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| Memory Proxy Maps for Visual Navigation | arXiv | 2024 | [[Paper]](https://arxiv.org/abs/2411.09893) |
| Spatial Memory-Augmented Visual Navigation Based on SLAM | Knowledge-Based Systems | 2024 | [[Paper]](https://www.sciencedirect.com/science/article/abs/pii/S0950705123011061) |
| Move to Understand a 3D Scene: Bridging Visual Grounding and Exploration | ICCV | 2025 | [[Paper]](https://openaccess.thecvf.com/content/ICCV2025/html/Zhu_Move_to_Understand_a_3D_Scene_Bridging_Visual_Grounding_and_ICCV_2025_paper.html) |

### Safety & Failure Recovery

Memory for remembering mistakes and enabling recovery from failures.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| ReasoningBank: Scaling Agent Self-Evolving with Reasoning Memory | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2505.00675) |
| Agent Learning via Early Experience | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2505.00675) |

---

## Categories by Application Domain

### Long-Horizon Manipulation

Memory approaches enabling robots to perform complex, multi-step manipulation tasks over extended time horizons.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| Memory, Benchmark & Robots: A Benchmark for Solving Complex Tasks with RL (MIKASA-Robo) | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2502.10550) [[Code]](https://github.com/CognitiveAISystems/MIKASA-Robo) |
| RoboCerebra: A Large-scale Benchmark for Long-horizon Robotic Manipulation | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2506.06677) |
| VLABench: A Large-Scale Benchmark for Language-Conditioned Robotics Manipulation | ICCV | 2025 | [[Paper]](https://openaccess.thecvf.com/content/ICCV2025/html/Zhang_VLABench_A_Large-Scale_Benchmark_for_Language-Conditioned_Robotics_Manipulation_with_Long-Horizon_ICCV_2025_paper.html) |

### Embodied Navigation

Memory systems for spatial mapping, localization, and navigation tasks.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| ReMEmbR: Building and Reasoning Over Long-Horizon Spatio-Temporal Memory for Robot Navigation | ICRA | 2025 | [[Paper]](https://ieeexplore.ieee.org/abstract/document/11127706/) [[Project]](https://rasc.usc.edu/blog/remembr/) |
| Neural Topological SLAM for Visual Navigation | CVPR | 2020 | [[Paper]](http://openaccess.thecvf.com/content_CVPR_2020/html/Chaplot_Neural_Topological_SLAM_for_Visual_Navigation_CVPR_2020_paper.html) |
| Memory-Efficient Visual SLAM With Sliding Window Map Sparsification | JFR | 2024 | [[Paper]](https://onlinelibrary.wiley.com/doi/10.1002/rob.22431) |

### Active Perception

Memory-enhanced perception systems that actively gather and utilize information.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| EASE: Embodied Active Event Perception via Self-Supervision | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2506.17516) |
| MP5: A Multi-Modal Open-Ended Embodied System in Minecraft via Active Perception | IEEE TPAMI | 2024 | [[Paper]](https://ieeexplore.ieee.org/abstract/document/10657187/) |

### Embodied Agents with LLM/VLM

Memory systems designed for LLM/VLM-based embodied agents.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| KARMA: Augmenting Embodied AI Agents with Long-and-Short Term Memory Systems | ICRA | 2025 | [[Paper]](https://ieeexplore.ieee.org/document/11128047/) |
| Embodied AI Agents: Modeling the World | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2506.22355) |
| Cognitive Architectures in Autonomous Robotics: A Systematic Review | IEEE Access | 2025 | [[Paper]](https://ieeexplore.ieee.org/abstract/document/11232472/) |

---

