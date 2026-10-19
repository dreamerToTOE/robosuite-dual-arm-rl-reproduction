# robosuite Dual-arm RL Reproduction | 双臂强化学习与约束操作

> Status: **PLANNED / 未开始复现** · Primary job target: dual-arm manipulation + contact control + RL

## Goal
Use robosuite (MuJoCo backend) to create a rigorous benchmark around **TwoArmLift**, **TwoArmPegInHole** and optionally **TwoArmHandover**, with scripted/controller baselines and a learning-based or residual-policy extension. Evaluate what can transfer conceptually to the dual FR3 Isaac Sim/ROS2 task.

Upstream: https://github.com/ARISE-Initiative/robosuite
Docs: https://robosuite.ai/docs/overview.html
Related user research: https://github.com/dreamerToTOE/dual-arm-embodied-palletizing
Related force control: https://github.com/dreamerToTOE/dual-arm-force-control-mujoco-isaacsim

## Scientific question
When do traditional impedance/operational-space controllers suffice, and when does a learned residual improve robustness against contact, pose error and friction perturbation?

**robosuite is a benchmark framework, not a claim that it ships trained PPO/SAC baselines for every task.** Identify available baselines and implement new algorithms transparently.

## Milestones
| Gate | Task | Exit criterion |
|---|---|---|
| R0 | Pin upstream/source versions | Robot models/controllers/task APIs audited |
| R1 | Reproduce deterministic environment | Fixed seed resets, action/observation schema, collision/contact sanity |
| R2 | Controller baselines | Documented OSC / impedance / scripted controllers where applicable |
| R3 | Training baseline | Pick one task, run RL or demonstration baseline with eval-only held-out seeds |
| R4 | Residual learning ablation | Compare base-only vs policy-only (if feasible) vs residual, matched evaluation |
| R5 | Robustness | Pose offset, object mass, friction, initial clearance, collision and contact-force diagnostics |
| R6 | Dual FR3 implications | Explain differences between MuJoCo benchmark and FR3 Isaac Sim; no fabricated transfer |

## Metrics
Success rate with uncertainty, time to complete, insertion error, end-effector path length, force peaks, collision/constraint violations, training environment steps and runtime.

## Integrity
No claims of genuine dual-FR3 hardware validation or real-world insertion; all baseline and extension work must be marked and reproducible.

## Documents
- [AGENTS.md](AGENTS.md)
- [docs/REPRODUCTION_PLAN.md](docs/REPRODUCTION_PLAN.md)
- [docs/EXPERIMENT_MATRIX.md](docs/EXPERIMENT_MATRIX.md)
- [docs/PAPER_CODE_ALIGNMENT.md](docs/PAPER_CODE_ALIGNMENT.md)
- [docs/FAILURE_LOG.md](docs/FAILURE_LOG.md)
- [docs/RESUME_EVIDENCE.md](docs/RESUME_EVIDENCE.md)
