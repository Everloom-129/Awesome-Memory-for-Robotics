# Awesome-Memory-for-Robotics[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)


Research summary of memory for robotics, including long-horizon manipulation, embodied agents, active perception with memory, mapping &amp; localization memory, episodic/semantic memory, retrieval-augmented policies, world models, and lifelong learning.


> 🤖 Memory is a fundamental capability to store, retrieve, and utilize past experiences for improved perception, planning, and decision-making. This mechanism enables robots to learn from experience, adapt to new situations, and operate effectively in complex, dynamic environments.

Here we organized a list of resources on **memory for robotics**, including papers, code, datasets, and benchmarks.

<p align="center">
  <img src="assets/banner.png" alt="Awesome Robotics Memory" width="800">
</p>


> Scope: **Robotics + Memory** , not generic LLM memory. We favor items with **robotic embodiment**, **closed-loop control**, **long-horizon tasks**, or **real-world evaluation**.

---

## Contents

- [Taxonomy](#taxonomy)
- [Survey & Tutorials](#survey--tutorials)
- [Core Topics](#core-topics)
  - [Episodic / Semantic Memory](#episodic--semantic-memory)
  - [Scene Memory & Spatial Representations](#scene-memory--spatial-representations)
  - [Retrieval-Augmented Policies (RAP)](#retrieval-augmented-policies-rap)
  - [World Models & Latent Dynamics](#world-models--latent-dynamics)
  - [Memory for Navigation & SLAM](#memory-for-navigation--slam)
  - [Memory for Manipulation](#memory-for-manipulation)
  - [Active Perception + Memory](#active-perception--memory)
  - [Lifelong / Continual Robot Learning](#lifelong--continual-robot-learning)
  - [Human-in-the-loop & Demonstration Memory](#human-in-the-loop--demonstration-memory)
- [Benchmarks & Evaluation](#benchmarks--evaluation)
- [Datasets](#datasets)
- [Tools & Libraries](#tools--libraries)
- [Engineering Patterns](#engineering-patterns)
- [Related Awesome Lists](#related-awesome-lists)
- [Contributing](#contributing)
- [License](#license)

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

## Survey & Tutorials

> Add surveys that explicitly discuss memory for embodied agents/robotics.

- **[Survey]** *Title* — Authors, Venue, Year. [[paper]](LINK) [[code]](LINK)
- **[Tutorial]** *Title* — Authors, Venue, Year. [[video]](LINK) [[slides]](LINK)

---

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
