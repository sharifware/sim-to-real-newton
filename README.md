# Sim-to-Real Locomotion Study with NVIDIA Newton

**Status: in progress** · Started Oct 2026 · Python · NVIDIA Newton / Warp · Isaac Lab · PPO

Does domain randomization change what a locomotion policy learns? This project trains a quadruped to walk in simulation with reinforcement learning on the GPU-accelerated [Newton](https://github.com/newton-physics/newton) physics engine, tests how well the policy holds up when the physics changes, and compares the trained networks with [nnanalyzer](https://github.com/sharifware/Large-Scale-Design-and-Analysis-of-Neural-Networks).

<!-- Add a demo GIF or video link here once you have one:
![demo](results/demo.gif) -->

## Research question

When a policy is trained with randomized physics (friction, mass, motor strength, action delay), is it more robust to unseen physics than one trained with fixed physics, and do the two networks differ in their weight distributions?

## Approach

1. **Foundations.** PID and LQR baselines on a cartpole in MuJoCo, PPO basics, and an intro to NVIDIA Warp.
2. **Train a walking policy.** PPO on a quadruped locomotion task in Isaac Lab using the Newton backend, across many parallel environments.
3. **Sim-to-real gap study.** Policy A (fixed physics) vs. policy B (domain randomization), both evaluated on perturbed physics they never saw. A sim-to-sim test trains under one Newton solver and evaluates under another.
4. **Weight analysis.** Run nnanalyzer on policies from several seeds and compare distributions with and without randomization.
5. **Stretch.** System identification with Newton's differentiable physics: recover hidden friction and mass values from observed trajectories.

## Repository layout

```
configs/    training and randomization configs
scripts/    train, evaluate, and sim-to-sim scripts
analysis/   nnanalyzer runs and plotting notebooks
results/    plots, tables, and videos
docs/       project site (GitHub Pages)
```

## Setup

- **Hardware:** NVIDIA RTX 5080 (16 GB VRAM). Start with roughly 1,000-2,000 parallel environments and scale up while watching memory.
- **Software:** [Newton](https://github.com/newton-physics/newton) and [Isaac Lab](https://developer.nvidia.com/newton-physics) with the Newton backend. Isaac Lab's Newton support was experimental in the 3.0 Beta as of NVIDIA's July 2026 documentation, so follow the current install docs and note your exact versions below.

| Component | Version |
| --- | --- |
| OS | TODO |
| NVIDIA driver / CUDA | TODO |
| Newton | TODO |
| Isaac Lab | TODO |
| Python | TODO |

## Results

Results will be added as experiments finish. Nothing below is measured yet.

| Policy | Training physics | Success rate (nominal) | Success rate (shifted physics) |
| --- | --- | --- | --- |
| A | Fixed | TBD | TBD |
| B | Domain randomization | TBD | TBD |

## Roadmap

- [ ] Environment setup (Newton + Isaac Lab on RTX 5080)
- [ ] Control and RL baselines
- [ ] Quadruped locomotion policy trained
- [ ] Fixed-physics vs. domain-randomization comparison
- [ ] Sim-to-sim solver test
- [ ] nnanalyzer weight-distribution comparison
- [ ] Stretch: system identification with differentiable physics

## References

- [Newton physics engine](https://github.com/newton-physics/newton)
- [Isaac Lab: A GPU-Accelerated Simulation Framework for Multi-Modal Robot Learning](https://arxiv.org/abs/2511.04831)
- [LeCAR Lab research](https://lecar-lab.github.io/research.html), the source of the sim-to-real framing
- [nnanalyzer](https://github.com/sharifware/Large-Scale-Design-and-Analysis-of-Neural-Networks)

## Author

Sharif Adepetu · [GitHub](https://github.com/sharifware) · sharifadepetu@gmail.com

## License

MIT
