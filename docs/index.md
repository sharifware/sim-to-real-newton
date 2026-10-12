# Sim-to-Real Locomotion Study with NVIDIA Newton

*In progress.* Does domain randomization change what a locomotion policy learns?

I'm training a quadruped to walk with PPO on [NVIDIA Newton](https://github.com/newton-physics/newton), a GPU-accelerated physics engine, then testing how the policy holds up when friction, mass, motor strength, and action delay change. I compare policies trained with fixed and randomized physics, and analyze their weights with [nnanalyzer](https://github.com/sharifware/Large-Scale-Design-and-Analysis-of-Neural-Networks).

## Plan

1. Control and RL baselines
2. Train a quadruped locomotion policy in Isaac Lab on the Newton backend
3. Fixed-physics vs. domain-randomization comparison, plus a sim-to-sim solver test
4. Weight-distribution analysis across seeds
5. Stretch: system identification with differentiable physics

## Results

Coming soon. This page will be updated with plots, a results table, and a demo video as experiments finish.

[Source code and full README on GitHub](https://github.com/sharifware/sim-to-real-newton)
