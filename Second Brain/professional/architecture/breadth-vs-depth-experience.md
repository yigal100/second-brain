---
type: Architectural Pattern
title: Engineering Experience: Breadth vs Depth
description: Evaluating technical authority based on vertical single-company longevity versus horizontal multi-project sample sizes.
tags: [career-development, management, metrics, leadership, team-dynamics]
timestamp: 2026-07-04T13:00:00Z
---

# Engineering Experience: Breadth vs Depth

An industry-wide **appeal to authority fallacy** frequently occurs when evaluating engineers based solely on their years of experience. To make sound architectural decisions and choose the right tools, organizations must apply distinct KPIs to differentiate between **vertical/deep** experience and **horizontal/broad** experience.

## The Experience Dichotomy

```
                       [ EXPERIENCE TYPES ]
                                │
         ┌──────────────────────┴──────────────────────┐
         ▼                                             ▼
  [ VERTICAL DEPTH ]                            [ HORIZONTAL BREADTH ]
  - Single company longevity (15-20 yrs)        - Multi-enterprise / Contractor
  - Deep historical context                     - Large sample size of projects
  - Highly specialized domain expertise         - Expert at tooling trade-offs
  - Bias: Consistency/Stagnation                - Bias: Break eggs / High churn
```

### 1. Vertical Depth (Deep & Narrow)
*   **Profile**: Engineers who have spent a massive portion of their career (e.g., 15–20 years) at a single enterprise.
*   **Core Strengths**: 
    *   Intimate, unparalleled knowledge of the company's codebase history (i.e., *why* things are done in a particular fashion).
    *   Exquisite domain expertise regarding specific proprietary products.
*   **Correct KPIs**: History retention, domain troubleshooting, specialized system maintenance.
*   **Risks**: Stagnation. Maintaining absolute consistency and backward compatibility often leads to resisting modern approaches or tooling.

### 2. Horizontal Breadth (Shallow & Wide)
*   **Profile**: Engineers or contractors who have worked across multiple enterprises, clients, and projects.
*   **Core Strengths**:
    *   A large "sample size" of projects, which provides statistical insight into what works and what fails across the industry.
    *   The ability to objectively compare frameworks, languages, devops pipelines, and design approaches.
*   **Correct KPIs**: Tooling evaluation, technical risk mitigation, modern architectural bootstrap, ways-of-working modernization.
*   **Risks**: Over-engineering, creating churn, or failing to respect unique legacy constraints.

---

## Application: Choosing the Right Tool for the Job

When a vertical-depth engineer attempts to make horizontal-breadth decisions (such as selecting a task runner, framework, or cloud tool), they often rely on a **sample size of one** (their current company's history). This can lead to stagnation, such as clinging to obsolete tools (like Makefiles) under the banner of maintaining consistency.

To prevent stagnation, organizations must embrace the trade-off: **"You have to break a few eggs to make an omelette."** Breath-based decisions are best informed by individuals with wide exposure to industry lessons.

---

## Related Concepts

*   [[professional/architecture/software-craftsmanship|Software Craftsmanship Paradigm]]
*   [[professional/languages/dbt-evaluation|DBT (Data Build Tool) Evaluation]]
*   [[professional/architecture/three-musketeers-pattern|Three Musketeers Pattern and Makefiles]]
