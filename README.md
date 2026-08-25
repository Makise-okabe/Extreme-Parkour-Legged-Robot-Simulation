# Extreme Parkour Legged Robot Simulation

Undergraduate research study of **Extreme Parkour with Legged Robots (XtremeParkour)**, focusing on how end-to-end reinforcement learning enables a quadruped robot to perform agile parkour using onboard depth perception and proprioception.

This repository documents my technical understanding of the XtremeParkour framework as part of undergraduate research at the National University of Singapore (NUS). It is **not** the original XtremeParkour implementation and does not redistribute the upstream source code.

## Research Question

> How does an end-to-end reinforcement learning policy trained in Isaac Gym enable a quadruped robot to perform complex parkour behaviours using only depth input within the XtremeParkour framework?

## Project Focus

The study examines the complete perception-to-action pipeline used for agile legged locomotion:

```text
Front-facing depth camera + proprioception
                  ↓
          perception encoder
                  ↓
        learned locomotion policy
                  ↓
        12-DoF joint commands
                  ↓
          Unitree A1 robot
```

Key topics investigated include:

- reinforcement learning for quadruped locomotion
- massively parallel simulation in NVIDIA Isaac Gym
- depth-based terrain perception
- proprioceptive state feedback
- teacher/student policy training and distillation
- curriculum learning across increasingly difficult terrain
- sim-to-real deployment considerations
- reward design and locomotion stability

## System Studied

The XtremeParkour framework uses a **Unitree A1 quadruped** with 12 actuated joints and a forward-facing depth camera. The deployable policy combines visual terrain information with proprioceptive measurements to generate motor actions without relying on an external terrain map or manually designed footstep planner.

The demonstrated behaviours include:

- long jumps
- climbing and high jumps
- ramp and obstacle traversal
- rapid redirection
- handstand-style locomotion

## Training Pipeline

A simplified view of the framework studied is:

```text
1. Parallel Isaac Gym environments
           ↓
2. Privileged-information teacher policy
           ↓
3. PPO-based reinforcement learning
           ↓
4. Camera-based student policy / distillation
           ↓
5. Deployable depth + proprioception policy
```

The upstream implementation separates base-policy training from camera-policy distillation. This allows the robot to first learn strong locomotion behaviour using richer simulation information before transferring that behaviour to a policy that operates from deployable onboard sensing.

## What I Learned

Through this project I developed practical understanding of:

- Python-based robotics research workflows
- reinforcement learning for continuous control
- policy training and evaluation in Isaac Gym
- neural-network-based perception and control
- reward functions and termination conditions
- simulation environments for legged robots
- reading and reverse-engineering an academic robotics codebase

## Repository Structure

```text
.
├── README.md
└── docs/
    ├── research-question.md
    └── technical-analysis.md
```

## Original Work

This repository is a study and technical analysis of the following work:

**Extreme Parkour with Legged Robots**  
Xuxin Cheng, Kexin Shi, Ananye Agarwal, Deepak Pathak  
ICRA 2024 / arXiv:2309.14341

Original repository: https://github.com/chengxuxin/extreme-parkour

Project website: https://extreme-parkour.github.io

## Disclaimer

The original XtremeParkour code, models and intellectual property belong to their respective authors. This repository contains my own study notes and technical interpretation for educational and research purposes.
