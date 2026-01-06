# Awesome-Memory-for-Robotics[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)


Research summary of memory for robotics, including long-horizon manipulation, embodied agents, active perception with memory, mapping &amp; localization memory, episodic/semantic memory, retrieval-augmented policies, world models, and lifelong learning.


> 🤖 Memory is a fundamental capability to store, retrieve, and utilize past experiences for improved perception, planning, and decision-making. This mechanism enables robots to learn from experience, adapt to new situations, and operate effectively in complex, dynamic environments.

Here we organized a list of resources on **memory for robotics**, including papers, code, datasets, and benchmarks.

<p align="center">
  <img src="assets/banner.png" alt="Awesome Robotics Memory" width="800">
</p>


> Scope: **Robotics + Memory** , not generic LLM memory. We favor items with **robotic embodiment**, **closed-loop control**, **long-horizon tasks**, or **real-world evaluation**.

---

## 📋 Table of Contents

- [Surveys & Overviews](#surveys--overviews)
- [Memory Systems & Cognitive Architecture](#memory-systems--cognitive-architecture)
- [Episodic Memory](#episodic-memory)
- [Semantic Memory](#semantic-memory)
- [Spatial & Scene Memory](#spatial--scene-memory)
  - [3D Scene Memory](#3d-scene-memory)
  - [Spatial Memory & SLAM](#spatial-memory--slam)
- [Visual Memory for Navigation](#visual-memory-for-navigation)
- [Memory for Manipulation](#memory-for-manipulation)
- [LLM/VLM-based Memory Systems](#llmvlm-based-memory-systems)
- [World Models & Memory](#world-models--memory)
- [Lifelong Learning & Continual Learning](#lifelong-learning--continual-learning)
  - [Experience Replay](#experience-replay)
  - [Skill Transfer & Memory](#skill-transfer--memory)
- [Working Memory & Short-term Memory](#working-memory--short-term-memory)
- [Benchmarks & Datasets](#benchmarks--datasets)
- [Open-Source Projects](#open-source-projects)
- [Contributing](#contributing)

---

## Taxonomy

Memory in robotics often mixes multiple axes:

- **Timescale**
  - *Working memory* (within-episode, short-term)
  - *Episodic memory* (experience replay / trajectories / videos)
  - *Semantic memory* (facts, object affordances, task graphs)
  - *Long-term / lifelong memory* (continual accumulation across tasks)
- **Representation**
  - key-value / slot memory, RNN/Transformer state
  - retrieval over embeddings (vector DB)
  - 3D maps / NeRF / Gaussian splats / voxel grids
  - symbolic graphs (scene graphs / task graphs)
- **Usage**
  - policy conditioning (retrieve then act)
  - planning (search over remembered states)
  - perception (temporal integration / object permanence)
  - safety & failure recovery (remember mistakes)

Read more: [`docs/taxonomy.md`](docs/taxonomy.md)

---


---

## Surveys & Overviews

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| A Survey on Memory Mechanisms in the Era of LLMs | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2504.15965) |
| A Survey on the Memory Mechanism of Large Language Model-based Agents | ACM | 2025 | [[Paper]](https://dl.acm.org/doi/10.1145/3748302) |
| Foundation Models in Robotics: Applications, Challenges, and the Future | IJRR | 2025 | [[Paper]](https://journals.sagepub.com/doi/abs/10.1177/02783649241281508) |
| Foundation Model Driven Robotics: A Comprehensive Review | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2507.10087) |
| Skill Transfer Learning for Autonomous Robots and Human-Robot Cooperation: A Survey | RAS | 2020 | [[Paper]](https://www.sciencedirect.com/science/article/pii/S0921889019309972) |

---

## Memory Systems & Cognitive Architecture

Memory systems that provide comprehensive cognitive capabilities for robots, often inspired by human memory architecture.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| RoboMemory: A Brain-inspired Multi-memory Agentic Framework for Lifelong Learning | OpenReview | 2025 | [[Paper]](https://openreview.net/forum?id=HHGzG1Choi) |
| Structured Memory for Robots | EmergentMind | 2025 | [[Paper]](https://www.emergentmind.com/topics/structured-memory-system-for-robots) |
| A Memory System of a Robot Cognitive Architecture and its Implementation in ArmarX | RAS | 2023 | [[Paper]](https://www.sciencedirect.com/science/article/abs/pii/S0921889023000544) [[PDF]](https://h2t.iar.kit.edu/pdf/Peller2023.pdf) |
| A Memory System for a Conscious Robot | Frontiers | 2018 | [[Paper]](https://pmc.ncbi.nlm.nih.gov/articles/PMC7805698/) |
| Memory as the Substrate of Cognition: A Developmental Cognitive Robotics Perspective | ResearchGate | 2015 | [[Paper]](https://www.researchgate.net/profile/Paul-Baxter-6/publication/277799284) |
| Dynamic Learning in Cognitive Robotics through a Procedural Long Term Memory | EAAI | 2013 | [[Paper]](https://link.springer.com/article/10.1007/s12530-013-9079-4) |

---

## Episodic Memory

Episodic memory enables robots to store and recall specific experiences and events.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| Beyond Recall: Evaluating Forgetting Mechanisms for Multi-Robot Systems | H2T | 2025 | [[Paper]](https://h2t.iar.kit.edu/pdf/Plewnia2025.pdf) |
| Episodic Memory Banks for Lifelong Robot Learning | OpenReview | 2024 | [[Paper]](https://openreview.net/forum?id=BBgDA4y0B9) |
| Forgetting in Robotic Episodic Long-Term Memory | ECAI | 2024 | [[Paper]](https://events.infovaya.com/uploads/documents/pdfviewer/0a/40/131281-2412.pdf) |
| Long Horizon Episodic Decision Making for Cognitively Inspired Robots | COGSYS | 2024 | [[Paper]](https://www.sciencedirect.com/science/article/pii/S1389041724000536) |
| Synthesizing the Temporal Self: Robotic Models of Episodic Memory | PMC | 2024 | [[Paper]](https://pmc.ncbi.nlm.nih.gov/articles/PMC11523108/) |
| Episodic Memory Model for Learning Robotic Manipulation | arXiv | 2021 | [[Paper]](https://arxiv.org/abs/2104.10218) |
| ART Neural Network-based Integration of Episodic Memory and Semantic Memory for Task Planning | AURO | 2019 | [[Paper]](https://link.springer.com/article/10.1007/s10514-019-09868-x) |
| Deep Episodic Memory: Encoding, Recalling, and Predicting Episodic Experiences for Robot Action Execution | IEEE RAL | 2018 | [[Paper]](https://ieeexplore.ieee.org/abstract/document/8421022/) |
| Storing and Retrieving Perceptual Episodic Memories for Long-term Manipulation Tasks | ICAR | 2017 | [[Paper]](https://ieeexplore.ieee.org/document/8023492/) |
| Towards an Episodic Memory for Cognitive Robots | ECAI Workshop | 2008 | [[Paper]](http://tams-www.informatik.uni-hamburg.de/paper/2008/jockel_ECAI08towards.pdf) |

---

## Semantic Memory

Semantic memory provides robots with structured knowledge about concepts, objects, and their relationships.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| Enter the Mind Palace: Reasoning and Planning for Long-term Active Embodied Question Answering | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2507.12846) |
| Memory-Centric Embodied Question Answering | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2505.13948) |
| CRESTA: A Cognitivist Framework for Semantic-driven Task Awareness | RAS | 2025 | [[Paper]](https://www.sciencedirect.com/science/article/pii/S0921889025004002) |
| Meta-Memory: Retrieving and Integrating Semantic-Spatial Memory | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2509.20754) |
| A Semantic Memory System for Task Planning under Uncertainties | IROS | 2010 | [[Paper]](https://ieeexplore.ieee.org/document/5650956/) |
| Robot Task Planning using Semantic Maps | RAS | 2008 | [[Paper]](https://www.sciencedirect.com/science/article/pii/S0921889008001188) |

---

## Spatial & Scene Memory

### 3D Scene Memory

Memory systems for representing and reasoning about 3D environments.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| 3D-Mem: 3D Scene Memory for Embodied Exploration and Reasoning | CVPR | 2025 | [[Paper]](https://arxiv.org/abs/2411.17735) [[Project]](https://umass-embodied-agi.github.io/3D-Mem/) |
| What Is The Best 3D Scene Representation for Robotics? | arXiv | 2025 | [[Paper]](https://arxiv.org/html/2512.03422v1) |
| SnapMem: 3D Scene Memory for Embodied Exploration | OpenReview | 2024 | [[Paper]](https://openreview.net/forum?id=mz8unSsSsB) |
| Embodied-RAG: General Non-parametric Embodied Memory for Retrieval and Generation | arXiv | 2024 | [[Paper]](https://arxiv.org/abs/2409.18313) |
| CLIP-Fields: Weakly Supervised Semantic Fields for Robotic Memory | arXiv | 2022 | [[Paper]](https://arxiv.org/abs/2210.05663) |
| Hierarchical Representations and Explicit Memory: Learning Effective Navigation Policies on 3D Scene Graphs | ICRA | 2022 | [[Paper]](https://ieeexplore.ieee.org/abstract/document/9812179/) |

### Spatial Memory & SLAM

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| Unsupervised Online Learning for Robotic Interestingness with Visual Memory | IEEE TOR | 2021 | [[Paper]](https://arxiv.org/abs/2111.09793) [[Code]](https://github.com/wang-chen/interestingness) |
| Cognitive Memory and Mapping in a Brain-like System for Robotic Navigation | Neural Networks | 2017 | [[Paper]](https://www.sciencedirect.com/science/article/pii/S0893608016301861) |
| SLAM-Based Spatial Memory for Behavior-Based Robots | IFAC | 2015 | [[Paper]](https://www.sciencedirect.com/science/article/pii/S2405896315026579) |

---

## Memory for Navigation

Memory mechanisms that enable robots to navigate using visual information.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| Spatially-Enhanced Recurrent Memory for Long-Range Mapless Navigation via End-to-End Reinforcement Learning | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2506.05997) |
| MemoNav: Working Memory Model for Visual Navigation | arXiv | 2024 | [[Paper]](https://arxiv.org/abs/2402.19161) |
| Memory-Maze: Scenario Driven Benchmark for Visual Navigation | arXiv | 2024 | [[Paper]](https://arxiv.org/abs/2405.07060) |
| Emergence of Maps in the Memories of Blind Navigation Agents | ICLR | 2023 | [[Paper]](https://openreview.net/forum?id=3HL8sQ7j8j) [[Project]](https://wijmans.xyz/publication/eom/) |
| Memory-Augmented Reinforcement Learning for Image-Goal Navigation | IROS | 2022 | [[Paper]](https://arxiv.org/abs/2101.05181) |
| Deep Visual Odometry With Adaptive Memory | PAMI | 2022 | [[Paper]](https://arxiv.org/abs/2008.01655) |
| Structured Scene Memory for Vision-Language Navigation | CVPR | 2021 | [[Paper]](https://openaccess.thecvf.com/content/CVPR2021/) |
| Visual Graph Memory with Unsupervised Representation for Visual Navigation | ICCV | 2021 | [[Paper]](https://openaccess.thecvf.com/content/ICCV2021/) |
| MultiON: Benchmarking Semantic Map Memory using Multi-Object Navigation | NeurIPS | 2020 | [[Paper]](https://proceedings.neurips.cc/paper/2020/) |
| Scene Memory Transformer for Embodied Agents in Long-Horizon Tasks | CVPR | 2019 | [[Paper]](https://openaccess.thecvf.com/content_CVPR_2019/) |
| Visual Memory for Robust Path Following | NeurIPS | 2018 | [[Paper]](https://saurabhg.web.illinois.edu/pdfs/kumar2018visual.pdf) |
| Learning Indoor Robot Navigation using Visual and Sensorimotor Map | PMC | 2013 | [[Paper]](https://pmc.ncbi.nlm.nih.gov/articles/PMC3791472/) |
| Image-based Robot Navigation from an Image Memory | RAS | 2007 | [[Paper]](https://www.sciencedirect.com/science/article/pii/S0921889006001734) |
| 3D Navigation based on a Visual Memory | ICRA | 2006 | [[Paper]](https://ieeexplore.ieee.org/document/1642112/) |

---

## Memory for Manipulation

Memory systems for robotic manipulation tasks.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| Learning Long-Context Diffusion Policies via Past-Token Prediction | CoRL | 2025 | [[Paper]](https://arxiv.org/abs/2505.09561) [[Project]](https://long-context-dp.github.io/) |
| SAM2Act: Integrating Visual Foundation Model with A Memory Architecture for Robotic Manipulation | ICML | 2025 | [[Paper]](https://arxiv.org/abs/2501.18564) |
| DynaMem: Online Dynamic Spatio-Semantic Memory for Open World Mobile Manipulation | arXiv | 2024 | [[Paper]](https://arxiv.org/abs/2411.04999) |
| Out of Sight, Still in Mind: Reasoning and Planning about Unobserved Objects with Video Tracking Enabled Memory Models | ICRA | 2024 | [[Paper]](https://arxiv.org/abs/2309.15278) |
| Deep Episodic Memory for Robot Action Execution | IEEE RAL | 2018 | [[Paper]](https://ieeexplore.ieee.org/abstract/document/8421022/) |
| Storing and Retrieving Perceptual Episodic Memories for Long-term Manipulation Tasks | ICAR | 2017 | [[Paper]](https://ieeexplore.ieee.org/document/8023492/) |

---

## LLM/VLM-based Memory Systems

Memory systems leveraging Large Language Models and Vision-Language Models.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| ELLMER: Embodied Large Language Model-Enabled Robot Framework | Nature MI | 2025 | [[Paper]](https://www.nature.com/articles/s42256-025-01005-x) |
| Grounding VLMs for Robotics through Self-Generated Memory | arXiv | 2025 | [[Paper]](https://arxiv.org/html/2507.16713v1) |
| LLM-empowered Embodied Agent for Memory-Augmented Task Planning in Household Robotics | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2504.21716) |
| Scaling up Memory for Robotic Control via Experience Retrieval (MemER) | OpenReview | 2025 | [[Paper]](https://openreview.net/forum?id=1dH4ARGdwD) [[Project]](https://jen-pan.github.io/memer/) |
| CLFR-M: Continual Learning Framework for Robots via Human Feedback and Dynamic Memory | IEEE | 2024 | [[Paper]](https://ieeexplore.ieee.org/document/10672832/) |
| Nadine: An LLM-driven Intelligent Social Robot with Affective Capabilities and Human-like Memory | arXiv | 2024 | [[Paper]](https://arxiv.org/abs/2405.20189) |
| ReMEmbR: Building and Reasoning Over Long-Horizon Spatio-Temporal Memory for Robots | arXiv | 2024 | [[Paper]](https://arxiv.org/abs/2409.13682) [[Project]](https://rasc.usc.edu/blog/remembr/) [[Blog]](https://developer.nvidia.com/blog/using-generative-ai-to-enable-robots-to-reason-and-act-with-remembr/) |
| VLM Agents Generate Their Own Memories (ICAL) | NeurIPS | 2024 | [[Paper]](https://arxiv.org/abs/2406.14596) [[Project]](https://ical-learning.github.io/) |
| JARVIS-1: Open-World Multi-task Agents with Memory-Augmented Multimodal Language Models | arXiv | 2023 | [[Paper]](https://arxiv.org/abs/2311.05997) |
| Open-ended Instructable Embodied Agents with Memory-Augmented Large Language Models | EMNLP Findings | 2023 | [[Paper]](https://aclanthology.org/2023.findings-emnlp.226/) |

---

## World Models & Memory

World models that incorporate memory for prediction and planning.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| Mastering Diverse Control Tasks through World Models | Nature | 2025 | [[Paper]](https://www.nature.com/articles/s41586-025-08744-2) |
| Mastering Memory Tasks with World Models (R2I) | arXiv | 2024 | [[Paper]](https://arxiv.org/abs/2403.04253) |
| Ctrl-World: A Controllable Generative World Model for Robot Manipulation | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2510.10125) |
| Genie 3: A New Frontier for World Models | Google DeepMind | 2025 | [[Blog]](https://deepmind.google/blog/genie-3-a-new-frontier-for-world-models/) |
| Titans + MIRAS: Helping AI have Long-term Memory | Google Research | 2025 | [[Blog]](https://research.google/blog/titans-miras-helping-ai-have-long-term-memory/) |

---

## Lifelong Learning & Continual Learning

### Experience Replay

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| Effective Generative Replay with Strong Memory for Continual Learning | KBS | 2025 | [[Paper]](https://www.sciencedirect.com/science/article/abs/pii/S0950705125005234) |
| AdaER: An Adaptive Experience Replay Approach for Continual Lifelong Learning | Neurocomputing | 2024 | [[Paper]](https://www.sciencedirect.com/science/article/abs/pii/S0925231223013279) |
| Lifelong Robotic Reinforcement Learning by Retaining Experiences | CoLLAs | 2022 | [[Paper]](https://proceedings.mlr.press/v199/xie22a.html) |
| Selective Experience Replay for Lifelong Learning | AAAI | 2018 | [[Paper]](https://ojs.aaai.org/index.php/AAAI/article/view/11595) |

### Lifelong Learning Frameworks

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| Preserving and Combining Knowledge in Robotic Lifelong Learning | Nature MI | 2025 | [[Paper]](https://www.nature.com/articles/s42256-025-00983-2) |
| Task-agnostic Lifelong Robot Learning with Retrieval-based Memory | OpenReview | 2025 | [[Paper]](https://openreview.net/forum?id=FBaFSOjgI2) [[arXiv]](https://arxiv.org/abs/2410.02995) |
| Towards General Purpose Robots at Scale: Memory and Lifelong Learning | arXiv | 2024 | [[Paper]](https://arxiv.org/abs/2501.10395) |
| Continual Robot Learning | CMU Thesis | 2023 | [[Paper]](https://www.ri.cmu.edu/app/uploads/2023/09/snpowers_phd_ri_2023.pdf) |
| A Lifelong Learning Approach to Mobile Robot Navigation | IEEE RAL | 2021 | [[Paper]](https://ieeexplore.ieee.org/abstract/document/9345478/) |

### Skill Transfer & Memory

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| Efficient Policy Learning by Extracting Transferable Robot Skills | arXiv | 2024 | [[Paper]](https://arxiv.org/html/2406.17768v3) |
| Unsupervised Skill Transfer Learning for Autonomous Robots | RAS | 2021 | [[Paper]](https://www.sciencedirect.com/science/article/abs/pii/S0921889021001202) |
| Skill Transfer Learning for Autonomous Robots and Human-Robot Cooperation: A Survey | RAS | 2020 | [[Paper]](https://www.sciencedirect.com/science/article/pii/S0921889019309972) |

---

## Working Memory & Short-term Memory

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| An Incremental Learning Model for Mobile Robot: From Short-term Memory to Long-term Memory | IEEE TAI | 2021 | [[Paper]](https://ieeexplore.ieee.org/abstract/document/9665293/) |
| A Working Memory Model Improves Cognitive Control in Agents and Robots | COGSYS | 2018 | [[Paper]](https://www.sciencedirect.com/science/article/pii/S1389041717300943) |
| Short-term Memory Mechanisms in Neural Network Learning of Robot Navigation Tasks | IEEE | 2010 | [[Paper]](https://ieeexplore.ieee.org/abstract/document/5418323/) |
| A Hierarchical Autonomous Robot Controller for Learning and Memory | Adaptive Behavior | 2009 | [[Paper]](https://journals.sagepub.com/doi/abs/10.1177/1059712309105814) |



## Core Topics

---

## Benchmarks & Evaluation

We care these features that actually pose challenges to memory:

- **Partial observability:** occlusions, hidden states, deferred rewards
- **Long-horizon:** requires recalling earlier observations/instructions
- **Distribution shift:** new scenes, objects, layouts
- **Recovery:** can the agent use memory to diagnose and retry?

Read more: [`docs/evaluation.md`](docs/evaluation.md)

- *Benchmark* — tasks, what memory it tests. [[paper]](LINK) [[code]](LINK)

---

## Datasets

- *Dataset* — modalities (RGB-D, tactile, proprioception), duration, embodiment, labels. [[paper]](LINK) [[download]](LINK)

See: [`docs/datasets.md`](docs/datasets.md)


---

## Related Awesome Lists

- Awesome Memory for Agents — [[repo]](https://github.com/TsinghuaC3I/Awesome-Memory-for-Agents)
- Awesome Multimodal Memory — [[repo]](https://github.com/patrick-tssn/Awesome-Multimodal-Memory)
- Awesome LLM Robotics — [[repo]](https://github.com/GT-RIPL/Awesome-LLM-Robotics)

---

## Contributing

PRs welcome! Please read the [contribution guidelines](CONTRIBUTING.md).

To add a new paper or resource:
1. Fork this repository
2. Add your entry in the appropriate section
3. Submit a pull request

Please ensure your PR follows the existing format and includes:
- Paper title
- Venue and year
- Links to paper, code, and project page (if available)

---


## Citation

If you find this repository useful, please consider citing:

```bibtex
@misc{awesome-memory-for-robotics,
  author = {Jie Wang},
  title = {Awesome Memory for Robotics},
  year = {2025},
  publisher = {GitHub},
  howpublished = {\url{https://github.com/Everloom-129/Awesome-Memory-for-Robotics}}
}
```


---

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

This work is licensed under [CC0 1.0 Universal](LICENSE).

---

<p align="center">
  <b>⭐ Star this repository if you find it useful! ⭐</b>
</p>
