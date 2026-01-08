# Awesome-Memory-for-Robotics[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

Research summary of memory for robotics, including long-horizon manipulation, embodied agents, active perception with memory, mapping & localization memory, episodic/semantic memory, retrieval-augmented policies, world models, and lifelong learning.

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
- [Contexual Memory](#contexual-memory)
- [Episodic Memory](#episodic-memory)
- [Semantic Memory](#semantic-memory)
- [Memory for Manipulation](#memory-for-manipulation)
  - [VLAs](#vlas)
  - [Mobile Manipulation](#mobile-manipulation)
  - [General Manipulation](#general-manipulation)
- [Memory for Locomotion](#memory-for-locomotion)
- [Memory for Navigation](#memory-for-navigation)
- [Spatial & Scene Memory](#spatial--scene-memory)
  - [3D Scene Memory](#3d-scene-memory)
  - [Spatial Memory & SLAM](#spatial-memory--slam)
- [World Models & Memory](#world-models--memory)
- [Lifelong Learning & Continual Learning](#lifelong-learning--continual-learning)
  - [Experience Replay](#experience-replay)
  - [Skill Transfer & Memory](#skill-transfer--memory)
- [Benchmarks & Evaluation](#benchmarks)
- [Datasets](#datasets)
- [Contributing](#contributing)

---

## Taxonomy

Memory in robotics often mixes multiple axes:

- **Timescale**
  - *Contexual memory* (within-episode, short-term working memory)
  - *Episodic memory* (experience replay / trajectories / videos)
  - *Semantic memory* (facts, object affordances, task graphs)
  - *Long-term / lifelong memory* (continual learning across tasks)
- **Representation**
  - key-value / slot memory, RNN / LSTM / Transformer state
  - retrieval over embeddings (RAG / vector DB)
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

There hasn't been a comprehensive survey on memory for robotics, we hope this list can help.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| From Human Memory to AI Memory: A Survey on Memory Mechanisms in the Era of LLMs | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2504.15965) |
| Foundation Models in Robotics: Applications, Challenges, and the Future | IJRR | 2025 | [[Paper]](https://journals.sagepub.com/doi/abs/10.1177/02783649241281508) |
| Foundation Model Driven Robotics: A Comprehensive Review | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2507.10087) |
| Partially Observable Markov Decision Processes in Robotics: A Survey | IEEE T-RO | 2022 | [[Paper]](https://ieeexplore.ieee.org/document/9664288) |
| Skill Transfer Learning for Autonomous Robots and Human-Robot Cooperation: A Survey | RAS | 2020 | [[Paper]](https://www.sciencedirect.com/science/article/pii/S0921889019309972) |

---

## Memory Systems & Cognitive Architecture

Often inspired by human memory architecture.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| RoboMemory: A Brain-inspired Multi-memory Agentic Framework for Lifelong Learning | OpenReview | 2025 | [[Paper]](https://openreview.net/forum?id=HHGzG1Choi) |
| Structured Memory for Robots | EmergentMind | 2025 | [[Paper]](https://www.emergentmind.com/topics/structured-memory-system-for-robots) |
| A Memory System of a Robot Cognitive Architecture and its Implementation in ArmarX | RAS | 2023 | [[Paper]](https://www.sciencedirect.com/science/article/abs/pii/S0921889023000544) [[PDF]](https://h2t.iar.kit.edu/pdf/Peller2023.pdf) |
| A Memory System for a Conscious Robot | Frontiers | 2018 | [[Paper]](https://pmc.ncbi.nlm.nih.gov/articles/PMC7805698/) |
| Memory as the Substrate of Cognition: A Developmental Cognitive Robotics Perspective | ResearchGate | 2015 | [[Paper]](https://www.researchgate.net/profile/Paul-Baxter-6/publication/277799284) |
| Dynamic Learning in Cognitive Robotics through a Procedural Long Term Memory | EAAI | 2013 | [[Paper]](https://link.springer.com/article/10.1007/s12530-013-9079-4) |
| The Development of Embodied Cognition: Six Lessons from Babies | Artificial Life | 2005 | [[Paper]](https://www.cs.cmu.edu/~bziebart/publications/alife05-smith.pdf) |

---

## Contexual Memory

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| An Incremental Learning Model for Mobile Robot: From Short-term Memory to Long-term Memory | IEEE TAI | 2021 | [[Paper]](https://ieeexplore.ieee.org/abstract/document/9665293/) |
| A Working Memory Model Improves Cognitive Control in Agents and Robots | COGSYS | 2018 | [[Paper]](https://www.sciencedirect.com/science/article/pii/S1389041717300943) |
| Short-term Memory Mechanisms in Neural Network Learning of Robot Navigation Tasks | IEEE | 2010 | [[Paper]](https://ieeexplore.ieee.org/abstract/document/5418323/) |
| A Hierarchical Autonomous Robot Controller for Learning and Memory | Adaptive Behavior | 2009 | [[Paper]](https://journals.sagepub.com/doi/abs/10.1177/1059712309105814) |

---

## Episodic Memory


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

Language provides robots with structured knowledge about concepts, objects, and their relationships.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| Enter the Mind Palace: Reasoning and Planning for Long-term Active Embodied Question Answering | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2507.12846) |
| Memory-Centric Embodied Question Answering | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2505.13948) |
| CRESTA: A Cognitivist Framework for Semantic-driven Task Awareness | RAS | 2025 | [[Paper]](https://www.sciencedirect.com/science/article/pii/S0921889025004002) |
| Meta-Memory: Retrieving and Integrating Semantic-Spatial Memory | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2509.20754) |
| A Semantic Memory System for Task Planning under Uncertainties | IROS | 2010 | [[Paper]](https://ieeexplore.ieee.org/document/5650956/) |
| Robot Task Planning using Semantic Maps | RAS | 2008 | [[Paper]](https://www.sciencedirect.com/science/article/pii/S0921889008001188) |

---

## Memory for Manipulation

### VLAs

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| MemER: Scaling Up Memory for Robot Control via Experience Retrieval | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2510.20328) [[Project]](https://jen-pan.github.io/memer/) |
| MemoryVLA: Perceptual-Cognitive Memory in Vision-Language-Action Models for Robotic Manipulation | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2508.19236) |


### Mobile Manipulation

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| DynaMem: Online Dynamic Spatio-Semantic Memory for Open World Mobile Manipulation | arXiv | 2024 | [[Paper]](https://arxiv.org/abs/2411.04999) |
| CLIP-Fields: Weakly Supervised Semantic Fields for Robotic Memory | RSS | 2023 | [[Paper]](https://www.roboticsproceedings.org/rss19/p074.pdf) [[Project]](https://mahis.life/clip-fields) |

### General Manipulation

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| Learning Long-Context Diffusion Policies via Past-Token Prediction | CoRL | 2025 | [[Paper]](https://arxiv.org/abs/2505.09561) [[Project]](https://long-context-dp.github.io/) |
| SAM2Act: Integrating Visual Foundation Model with A Memory Architecture for Robotic Manipulation | ICML | 2025 | [[Paper]](https://arxiv.org/abs/2501.18564) |
| Out of Sight, Still in Mind: Reasoning and Planning about Unobserved Objects with Video Tracking Enabled Memory Models | ICRA | 2024 | [[Paper]](https://arxiv.org/abs/2309.15278) |
| RoboEXP: Action-Conditioned Scene Graph via Interactive Exploration for Robotic Manipulation | CoRL | 2024 | [[Paper]](https://arxiv.org/abs/2402.15487) [[Project]](https://jianghanxiao.github.io/roboexp-web/) |

---

## Memory for Navigation

Memory is of great importance for navigation, there has been rich research on it. 

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| Spatially-Enhanced Recurrent Memory for Long-Range Mapless Navigation via End-to-End Reinforcement Learning | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2506.05997) |
| MemoNav: Working Memory Model for Visual Navigation | CVPR | 2024 | [[Paper]](https://arxiv.org/abs/2402.19161) |
| Memory-Maze: Scenario Driven Benchmark and Visual Language Navigation Model for Guiding Blind People | arXiv | 2024 | [[Paper]](https://arxiv.org/abs/2405.07060) |
| Visual Language Maps for Robot Navigation (VLMaps) | ICRA | 2023 | [[Paper]](https://arxiv.org/abs/2210.05714) [[Project]](https://vlmaps.github.io/) |
| Emergence of Maps in the Memories of Blind Navigation Agents | ICLR | 2023 | [[Paper]](https://arxiv.org/abs/2301.13261) [[Project]](https://wijmans.xyz/publication/eom/) |
| Memory-Augmented Reinforcement Learning for Image-Goal Navigation | IROS | 2022 | [[Paper]](https://arxiv.org/abs/2101.05181) |
| Structured Scene Memory for Vision-Language Navigation | CVPR | 2021 | [[Paper]](https://openaccess.thecvf.com/content/CVPR2021/papers/Wang_Structured_Scene_Memory_for_Vision-Language_Navigation_CVPR_2021_paper.pdf) |
| Visual Graph Memory with Unsupervised Representation for Visual Navigation | ICCV | 2021 | [[Paper]](https://openaccess.thecvf.com/content/ICCV2021/papers/Kwon_Visual_Graph_Memory_With_Unsupervised_Representation_for_Visual_Navigation_ICCV_2021_paper.pdf) |
| Deep Visual Odometry With Adaptive Memory | TPAMI | 2020 | [[Paper]](https://arxiv.org/abs/2008.01655) |
| MultiON: Benchmarking Semantic Map Memory using Multi-Object Navigation | NeurIPS | 2020 | [[Paper]](https://arxiv.org/abs/2012.03912) |
| Scene Memory Transformer for Embodied Agents in Long-Horizon Tasks | CVPR | 2019 | [[Paper]](https://openaccess.thecvf.com/content_CVPR_2019/html/Fang_Scene_Memory_Transformer_for_Embodied_Agents_in_Long-Horizon_Tasks_CVPR_2019_paper.html) |
| Visual Memory for Robust Path Following | NeurIPS | 2018 | [[Paper]](https://saurabhg.web.illinois.edu/pdfs/kumar2018visual.pdf) |
| Cognitive Memory and Mapping in a Brain-like System for Robotic Navigation | Neural Networks | 2017 | [[Paper]](https://www.sciencedirect.com/science/article/pii/S0893608016301861) |
| Learning Indoor Robot Navigation using Visual and Sensorimotor Map | PMC | 2013 | [[Paper]](https://pmc.ncbi.nlm.nih.gov/articles/PMC3791472/) |
| Image-based Robot Navigation from an Image Memory | RAS | 2007 | [[Paper]](https://www.sciencedirect.com/science/article/pii/S0921889006001734) |
| 3D Navigation based on a Visual Memory | ICRA | 2006 | [[Paper]](https://ieeexplore.ieee.org/document/1642112/) |

---

## Memory for Locomotion

| Paper | Venue | Year | Links |
|-------|-------|------|-------|

---


## Spatial & Scene Memory

### 3D Scene Memory

Representing and reasoning about 3D environments.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| 3D-Mem: 3D Scene Memory for Embodied Exploration and Reasoning | CVPR | 2025 | [[Paper]](https://arxiv.org/abs/2411.17735) [[Project]](https://umass-embodied-agi.github.io/3D-Mem/) |
| What Is The Best 3D Scene Representation for Robotics? | arXiv | 2025 | [[Paper]](https://arxiv.org/html/2512.03422v1) |
| SnapMem: 3D Scene Memory for Embodied Exploration | OpenReview | 2024 | [[Paper]](https://openreview.net/forum?id=mz8unSsSsB) |
| Embodied-RAG: General Non-parametric Embodied Memory for Retrieval and Generation | arXiv | 2024 | [[Paper]](https://arxiv.org/abs/2409.18313) |
| ConceptFusion: Open-set Multimodal 3D Mapping | RSS | 2023 | [[Paper]](https://www.roboticsproceedings.org/rss19/p066.pdf) [[Project]](https://concept-fusion.github.io/) |
| Hierarchical Representations and Explicit Memory: Learning Effective Navigation Policies on 3D Scene Graphs | ICRA | 2022 | [[Paper]](https://ieeexplore.ieee.org/abstract/document/9812179/) |

### Spatial Memory & SLAM

Simultaneous Localization and Mapping(SLAM) is the most fundamental explicit type of memory. 

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| Unsupervised Online Learning for Robotic Interestingness with Visual Memory | IEEE T-RO | 2021 | [[Paper]](https://arxiv.org/abs/2111.09793) [[Code]](https://github.com/wang-chen/interestingness) |
| Probabilistic Data Association for Semantic SLAM | ICRA | 2017 | [[Paper]](https://ieeexplore.ieee.org/document/7989205) |
| SLAM-Based Spatial Memory for Behavior-Based Robots | IFAC | 2015 | [[Paper]](https://www.sciencedirect.com/science/article/pii/S2405896315026579) |
| RGB-D Mapping: Using Kinect-Style Depth Cameras for Dense 3D Modeling of Indoor Environments | IJRR | 2012 | [[Paper]](https://journals.sagepub.com/doi/10.1177/0278364911434148) |


---

## World Models & Memory

World models that incorporate memory for prediction and planning.

| Paper | Venue | Year | Links |
|-------|-------|------|-------|
| Mastering Diverse Control Tasks through World Models | Nature | 2025 | [[Paper]](https://www.nature.com/articles/s41586-025-08744-2) |
| Ctrl-World: A Controllable Generative World Model for Robot Manipulation | arXiv | 2025 | [[Paper]](https://arxiv.org/abs/2510.10125) |
| Genie 3: A New Frontier for World Models | Google DeepMind | 2025 | [[Blog]](https://deepmind.google/blog/genie-3-a-new-frontier-for-world-models/) |
| ManiGaussian: Dynamic Gaussian Splatting for Multi-task Robotic Manipulation | ECCV | 2024 | [[Paper]](https://arxiv.org/abs/2403.08321) [[Project]](https://guanxinglu.github.io/ManiGaussian/) |
| Mastering Memory Tasks with World Models (R2I) | ICLR | 2024 | [[Paper]](https://arxiv.org/abs/2403.04253) |

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


## Benchmarks & Evaluation

We care these features that actually pose challenges to memory:
- **Partial observability:** occlusions, hidden states, deferred rewards
- **Long-horizon:** requires recalling earlier observations/instructions
- **Distribution shift:** new scenes, objects, layouts
- **Recovery:** can the agent use memory to diagnose and retry?

Read more: [`docs/evaluation.md`](docs/evaluation.md)

---

## Datasets


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
  author = {Jie Wang, Siming He},
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
