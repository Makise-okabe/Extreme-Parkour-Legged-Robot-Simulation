# Research Question

## Main question

How does an end-to-end reinforcement learning policy trained in NVIDIA Isaac Gym enable a quadruped robot to execute complex parkour behaviours using depth perception and proprioceptive feedback within the XtremeParkour framework?

## Sub-questions

1. What observations are available to the policy during training and deployment?
2. Why is privileged simulation information useful for the teacher policy?
3. How does policy distillation transfer locomotion capability to a camera-based student policy?
4. How does curriculum learning help the robot progress from basic locomotion to difficult terrain and parkour tasks?
5. What parts of the system are learned, and what parts remain conventional robotics infrastructure?
6. What makes sim-to-real transfer possible despite the gap between Isaac Gym and the physical Unitree A1 robot?

## Scope

This study focuses on system understanding and technical analysis rather than claiming an independent reimplementation of the original XtremeParkour project.
