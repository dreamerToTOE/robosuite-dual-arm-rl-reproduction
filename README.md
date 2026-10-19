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

## 人与 Codex 学习分工（必读）

- [职责分工与逐阶段学习验收](docs/HUMAN_CODEX_WORKFLOW.md) — 研究者主导原理、实验原则和故障判断；Codex 主导实现、实验、日志；每阶段提供核心公式/源码导读、3 道理解检查题和实验证据。
- **研究边界**：五篇小论文复现完成并获得明确恢复指令前，双 FR3 主工程不推进、不被本仓库修改。独立开源复现可以正常进行。

## Final mock interview / 项目面试验收（独立关卡）

- [正式验收标准与本项目专属问题](docs/FINAL_INTERVIEW_GATE.md)：3 分钟项目陈述、公式/控制原理、源码追踪、实验与统计、失败诊断和个人贡献。建议 100 分制，达到 80 分且各模块达标才通过，重大来源/实验真实性错误直接不通过。
- [面试原始记录与评分模板](docs/INTERVIEW_RECORD_TEMPLATE.md)：记录面试官提问、研究者本人原始回答、分项得分、弱项与补强方案；未实际面试保持 NOT_STARTED。
- **复现技术验收与求职面试验收分开记录**：Codex 可以组织材料和出题，但不能替研究者应答，也不能自动标记 PASS。项目未完成时可以进行阶段练习，不算最终验收。
