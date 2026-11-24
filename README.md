# Predicting Coding-Agent Failure Before Execution

**Lead researcher:** Arshia Bajaj
**Status:** Study design (November 2026). Code, tasks, logs and results will be added here as the study runs.

## The question

AI coding agents often act on a task they have misunderstood. They proceed confidently, fail quietly, or report a task as complete when it is not.

This study asks:

> **Can disagreement among an agent's own independently sampled interpretations of a task, measured *before* it acts, predict failure better than its stated confidence or self-critique?**

If it can, the agent gets a practical signal for **when to stop and ask a human**, before it touches any code.

## How this differs from prior work

Recent work shows that coding agents are badly overconfident when asked, before acting, how likely they are to succeed. Other work measures agreement between multiple generated *programs*. This study measures something earlier: whether the agent's own *understanding of the task* is consistent across samples, before any code is written, and whether that predicts failure better than the agent's stated confidence.

## Why it matters

Human oversight does not scale if a person must review every step an agent takes. A reliable pre-execution signal lets agents work on their own when they understand the task, and hand off to a person when they likely do not. That saves review time, avoids wasted compute on runs that were doomed from the start, and catches errors before they reach a codebase.

## Design

| Component | Plan |
| --- | --- |
| Tasks | Fixed task suites on real open-source codebases |
| Signal | Before acting, the agent writes several independent interpretations of the task. A disagreement score measures how much they differ. |
| Baselines | The agent's stated confidence, and its own self-critique |
| Outcome | Whether the task actually succeeded, checked independently of the agent's claim |
| Additional conditions | Giving the agent dependency awareness before it edits, to test whether that reduces disagreement |
| Cost | Tokens and time spent on failed runs that the signal could have stopped |

## Open and reproducible

Every task, prompt, raw log and analysis script will be published in this repository, so anyone can rerun the study and check the results.

## Timeline

- **November 2026:** Study design published
- **December 2026:** First results
- **2027:** Full benchmark and write-up

## Contact

Arshia Bajaj · [LinkedIn](https://www.linkedin.com/in/arshiabajaj)
