---
type: Architectural Pattern
title: Three Musketeers Pattern and Makefiles
description: DevOps task execution pattern using Make, Docker, and Compose, and the modern limitations of Makefile task runners.
tags: [devops, build-tools, task-runners, make, docker, pipelines]
timestamp: 2026-07-04T13:00:00Z
---

# Three Musketeers Pattern and Makefiles

The **Three Musketeers Pattern** is a DevOps methodology based on the principle: **"Test, build, and deploy your app using the same tools locally and in CI."** It utilizes **Make** (the first musketeer), **Docker** (the second), and **Docker Compose** (the third) to achieve environment consistency across development and pipeline environments.

```
┌────────────────────────────────────────────────────────┐
│               THE THREE MUSKETEERS                     │
│                                                        │
│  ┌──────────────┐   ┌───────────────┐   ┌───────────┐  │
│  │   1. MAKE    │   │   2. DOCKER   │   │3. COMPOSE │  │
│  │ (Task Entry) │   │ (Environment) │   │ (Services)│  │
│  └──────┬───────┘   └───────┬───────┘   └─────┬─────┘  │
└─────────┼───────────────────┼─────────────────┼────────┘
          └─────────┬─────────┴─────────────────┘
                    ▼
       Consistent Execution (Local & CI)
```

## Makefile Adoption and "Old-Hand" Familiarity

In many legacy environments (especially C++ heavy teams), **Make** is chosen as the central task runner.
*   **The Assumption**: Legacy "old-hand" C++ developers are intimately familiar with Make. Utilizing a Makefile to abstract DevOps and Docker operations makes them comfortable.
*   **The Problem**: While Make is a file-dependency compilation tool for C/C++, it is a **terribly outdated task runner** for modern CI pipelines and service orchestration.

## Modern Task Runner Critique

Clinging to Make for pipeline automation introduces significant drawbacks:
1.  **Syntax Limitations**: Make's syntax is fragile, relying on strict tab formatting, arcane variable substitutions, and idiosyncratic error handling.
2.  **Lacking modern features**: Make is not built to act as a task execution dashboard or structured pipeline orchestrator.
3.  **Stagnation vs. Consistency**: Relying on Make under the assumption that developers cannot or will not adapt to modern devops task runners (like Taskfile, Just, or native pipeline steps) is a classic example of prioritizing consistency over technical modernization.

---

## Related Concepts

*   [[professional/architecture/software-craftsmanship|Software Craftsmanship Paradigm]]
*   [[professional/architecture/breadth-vs-depth-experience|Engineering Experience: Breadth vs Depth]]
