# Interview Skills from This Reproduction / 项目关联面试技术栈

**Focus:** 双机械臂协调控制 + Residual RL
**Target job families:** 双臂规划控制、力控算法、RL 机器人操作岗位

## Core required skills
- IK, Jacobian, operational-space impedance
- QP constraints and collision/contact forces
- shared object relative pose and internal force
- residual u = u_base + delta
- sample efficiency
- safe action projection
- perturbation robustness

## Portfolio / interview drill
Build controller-only baseline; trace contact transition with episode logging; compare base and residual under identical perturbations; explain how force limits and closed-chain constraints interact.

## Evidence policy
- Knowledge != implemented code != verified experiment. Demonstrate the exact level using code links and logs.
- Prepare one 3-minute overview and one 15-minute whiteboard walkthrough.
- Be ready to answer: Why this algorithm? Which baselines? What are training and evaluation metrics? How do you debug failures? What is your independent contribution?
- If this remains a numerical simulation, **do not** advertise physical robot experience, Sim2Real transfer or field deployment.

## Links
See [plan](REPRODUCTION_PLAN.md), [experiment matrix](EXPERIMENT_MATRIX.md), [resume evidence](RESUME_EVIDENCE.md).
