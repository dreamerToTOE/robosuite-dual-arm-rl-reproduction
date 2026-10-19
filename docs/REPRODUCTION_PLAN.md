# Reproduction Execution Plan / 分阶段复现计划

**Project:** robosuite TwoArmLift/TwoArmPegInHole controller baselines and Residual RL
**Status:** PLANNED; no results have been executed or validated.

## Prior-learning checkpoint (required before coding)
Produce an explanation of (1) scientific/engineering problem; (2) main solution and why; (3) innovations vs baselines; (4) full published experiments; (5) which parts are reproducible from open source; (6) proposed numerical simulation scope. Do not silently omit experiments and do not claim original quantitative reproduction based on simulation visuals alone.

## Gates
- **R0** — benchmark audit: record setup and acceptance evidence in docs/PROGRESS.md; if incomplete mark BLOCKED with cause.
- **R1** — environment smoke: record setup and acceptance evidence in docs/PROGRESS.md; if incomplete mark BLOCKED with cause.
- **R2** — controller baseline: record setup and acceptance evidence in docs/PROGRESS.md; if incomplete mark BLOCKED with cause.
- **R3** — RL baseline: record setup and acceptance evidence in docs/PROGRESS.md; if incomplete mark BLOCKED with cause.
- **R4** — residual policy: record setup and acceptance evidence in docs/PROGRESS.md; if incomplete mark BLOCKED with cause.
- **R5** — robustness: record setup and acceptance evidence in docs/PROGRESS.md; if incomplete mark BLOCKED with cause.
- **R6** — FR3 implications: record setup and acceptance evidence in docs/PROGRESS.md; if incomplete mark BLOCKED with cause.

## Project-specific actions
1. Confirm exact robosuite environment names, supported controllers and task variants at the pinned release.
2. Audit TwoArmLift and TwoArmPegInHole observations/actions, controller configuration, contact parameters, reward and success definitions.
3. Establish deterministic/non-learning controller baseline first, with per-trajectory diagnostics and constraints.
4. Choose a feasible trainable baseline and implement it transparently if upstream does not ship a matching trainer; mark it as a new baseline.
5. Build residual policy u=u_base+clip(delta_u), compare base-only, learned-only where feasible, residual with matched holdout episodes.
6. Test pose offsets, friction, mass and insertion clearance; map transferable ideas to dual FR3 but never assert physical equivalence.

## Minimum acceptance
- Reproducible pinned source SHA, environment manifest and deterministic smoke test.
- Paper/baseline code map and honest difference log.
- A run manifest for **each** metric or figure; no fabricated results.
- At least 3 random seeds *if computationally feasible*; otherwise explicit budget and uncertainty.
- Held-out evaluation conditions separated from training, raw episodes and summary plots.
- Metrics: success, insertion error, contact force, collisions, time to success, perturbation robustness.
- Completion report must distinguish validated claims, partial reproductions, extra extensions, and blocked claims.

## Stop/go rules
Stop after three distinct failed attempts on the same blocker; escalate cause and proposed alternatives. Do not silently lower model/environment complexity or invent synthetic 'paper-equivalent' evidence. Prefer numerical simulation verification where physical testing unavailable, clearly labeled. No unapproved long/high-cost runs.
