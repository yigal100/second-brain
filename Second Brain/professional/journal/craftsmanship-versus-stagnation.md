---
type: Professional Journal
title: "Software Craftsmanship vs. Technical Stagnation: Rethinking the KPIs of Engineering Experience"
description: "A reflective article on the history of software engineering metaphors, the dichotomy of experience, and the traps of absolute consistency."
tags: [software-engineering, software-craftsmanship, career-growth, tools, devops, industry-reflection]
timestamp: 2026-07-04T13:30:00Z
---

# Software Craftsmanship vs. Technical Stagnation: Rethinking the KPIs of Engineering Experience

As computer science transitioned from a theoretical research field for mathematicians into corporate programming at scale, our industry coined the term **"Software Engineering."** I put "Engineering" in quotes because, in my view—and perhaps until the current age of generative AI—software development has never behaved like a traditional physical engineering discipline.

Over my career, I’ve watched our industry cycle through several operational paradigms. Today, we are witnessing a quiet clash between two of them: **absolute consistency** and **technological evolution**. This tension forces us to ask a crucial question: **How do we actually measure the value of a senior engineer's experience?**

---

## From Construction to Craftsmanship

In the early days of corporate software, we likened our work to civil engineering. We designed systems like bridges, giving rise to the **Waterfall Process**: design a complete spec, code the spec, test it, and ship physical CDs to clients. 

But software is malleable; unlike a bridge, we can and do evolve it dynamically. When the industry transitioned to Software as a Service (SaaS) and subscription models, this civil construction metaphor collapsed. 

I remember reading articles arguing that programming shouldn't be viewed as construction, but rather as **Authorship**. Writing code is like writing a book—style, elegance, and readability matter immensely. 

This line of thought gave rise to the [[professional/architecture/software-craftsmanship|Software Craftsmanship Paradigm]]:
*   Just as book authors rely on established structures and genres, we rely on **Design Patterns** to avoid reinventing the wheel.
*   We operate in teams as guild members—mentoring juniors, pairing on hard problems, learning from mistakes, and gradually developing the pattern-recognition needed to make high-level architectural decisions. 

---

## The Trap of Absolute Consistency

The craftsmanship model explains why we deeply value experienced engineers. However, it also introduces a severe organizational vulnerability: **Technical Stagnation disguised as Consistency**.

At many established enterprises, you find "old-hands"—highly skilled engineers who have spent 15 or 20 years at the same company. While they hold invaluable domain knowledge, they often struggle with a critical trade-off: **You cannot maintain 100% backward compatibility and full consistency without stagnating.**

Take build tools and DevOps as an example. A team of legacy C++ programmers might adopt the [[professional/architecture/three-musketeers-pattern|Three Musketeers Pattern]] (Make, Docker, Compose) and lean on **Makefiles** as the main task runner in their CI/CD pipelines simply because they are familiar with Make. 

Make is a well established tool for C++ file dependency compilation, but it is an outdated, fragile tool and ill suited for modern pipeline orchestration. Yet, because the senior engineers are comfortable with it, the team maintains "consistency" at the expense of adopting modern task runners.

---

## Redefining the KPIs of Engineering Experience

When junior and mid-level engineers blindly follow legacy decisions, it's often because the wrong KPIs are applied to technical leadership. To build a healthy, evolving platform, we must divide engineering authority into two buckets:

### 1. Vertical Depth (The Domain Expert)
Engineers with long, single-company tenure possess incredible **vertical depth**.
*   **What they know**: Company history, architectural decisions, and product edge-cases.
*   **The KPI**: Specialized troubleshooting and historical context preservation.
*   **The Trap**: Their broad tooling choices are based on a *sample size of one* (their tenure at this single company). They lack statistical evidence of what works elsewhere.

### 2. Horizontal Breadth (The Multi-Project Advisor)
Engineers or contractors who have jumped across various projects, clients, and ecosystems possess **horizontal breadth**.
*   **What they know**: Tooling comparisons, modern ways-of-working, and the actual failure rates of popular frameworks.
*   **The KPI**: Tooling modernization and architectural risk assessment.

A great example of horizontal breadth is evaluating a framework like **DBT (Data Build Tool)**. DBT’s marketing promises to free up engineers by letting Business Analysts write SQL. However, experienced contractors who have worked across dozens of data projects will tell you that [[professional/languages/dbt-evaluation|DBT often adds a redundant layer of Jinja-macro complexity]] that core engineers end up having to maintain anyway. 

---

## Conclusion: "Breaking Eggs"

The craft of software engineering requires constant balance. Longevity and legacy consistency are important, but as the old saying goes: **"You have to break a few eggs to make an omelette."** 

If we treat single-company longevity as an absolute authority on modern tooling and orchestration, we end up wrapping modern systems in outdated structures (like Makefiles). True senior leadership lies in knowing when to lean on historical depth, when to leverage horizontal breadth, and when to bravely break consistency to allow for evolution.

*The craftsmanship model has served us well, but its final test is arriving. With generative AI poised to industrialize programming at scale, our definition of the software craftsman is about to change forever.*

---

## Related Concepts

*   [[professional/architecture/software-craftsmanship|Software Craftsmanship Paradigm]]
*   [[professional/architecture/breadth-vs-depth-experience|Engineering Experience: Breadth vs Depth]]
*   [[professional/architecture/three-musketeers-pattern|Three Musketeers Pattern and Makefiles]]
*   [[professional/languages/dbt-evaluation|DBT (Data Build Tool) Evaluation]]
