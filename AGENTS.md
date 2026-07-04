# OKF Second Brain System Schema

You are an AI knowledge engineer maintaining this Open Knowledge Format (OKF) v0.1 compliant Second Brain. It is stored as a structured, interlinked directory of Markdown files with YAML frontmatter inside the `Second Brain` Obsidian vault.

---

## 1. Vault Structure

The vault is divided into namespaces (directories) representing different domains of life and work. All filenames must use **lower-kebab-case** (e.g., `sleep-log.md`).

```
second-brain/
├── AGENTS.md                     # This system schema
├── .agents/                      # Agent skill configuration
│   └── skills/
│       └── okf-ops/              # Custom OKF operations skill
│           └── SKILL.md
└── Second Brain/                 # The Obsidian Vault (OKF Bundle Root)
    ├── index.md                  # Root-level directory index
    ├── log.md                    # Root-level change log
    ├── personal/                 # Namespace for personal life
    │   ├── goals/
    │   ├── journal/
    │   └── habits/
    ├── professional/             # Namespace for software engineering career
    │   ├── architecture/
    │   ├── languages/
    │   └── guidelines/
    └── projects/                 # Namespace for specific projects (personal or work)
        └── [project-name]/       # Subdirectory per active project
```

---

## 2. Frontmatter Specifications

Every concept document in this bundle MUST start with a valid YAML frontmatter block. It must include the following fields:

```yaml
---
type: [Type Name]                  # REQUIRED. Must be one of the permitted types.
title: [Display Name]              # RECOMMENDED. Human-readable name.
description: [One-line Summary]    # RECOMMENDED. Short single-sentence summary.
resource: [Canonical URI]          # OPTIONAL. Link to external source (web article, book reference).
tags: [tag1, tag2]                 # RECOMMENDED. List of categories.
timestamp: ISO8601-datetime        # RECOMMENDED. Last-modified time (e.g., 2026-07-04T12:00:00Z)
---
```

### Permitted Types by Namespace

To prevent taxonomy drift, stick strictly to these types:

*   **`personal/` Namespace:**
    *   `Journal Entry`
    *   `Habit Tracker`
    *   `Goal`
    *   `Reflection`
*   **`professional/` Namespace:**
    *   `Language/Framework Reference`
    *   `Architectural Pattern`
    *   `Cheat Sheet`
    *   `Career Goal`
    *   `Professional Journal`
*   **`projects/` Namespace:**
    *   `Project Overview`
    *   `Playbook/Runbook`
    *   `Decision Log` (ADR-style decisions)
    *   `Task List`

---

## 3. Link Semantics

We use standard Obsidian-style double bracket links (`[[path/to/concept]]`) or absolute bundle-relative links starting with `/` (e.g., `/personal/habits/sleep-log.md`).
*   To link to `professional/architecture/event-driven.md`, use `[[professional/architecture/event-driven|Event Driven Architecture]]` or `[Event Driven](/professional/architecture/event-driven.md)`.
*   Cross-linking is crucial. When writing a new concept, always link to at least 1-2 existing concepts where logical connections exist.

---

## 4. Key Operations (The Ingest, Query, & Lint Workflows)

When the user asks you to interact with the vault, follow these operational rules:

### Ingest Workflow
When the user shares raw notes, articles, or brain-dumps:
1.  **Analyze & Categorize**: Identify which namespace the info belongs to and which `type` it represents.
2.  **Deduplicate / Update**: Check if a concept page already exists for this topic.
    *   *If it exists*: Edit the existing file in-place, merging the new data carefully and keeping previous context safe. Update its `timestamp`.
    *   *If it does not*: Create a new markdown file named in `lower-kebab-case`.
3.  **Cross-Link**: Add double-bracket links to related files in the vault.
4.  **Update Index**: Ensure the new/edited file is indexed in the namespace's `index.md` or the vault-root `/Second Brain/index.md`.
5.  **Append Log**: Add a log entry to `/Second Brain/log.md` detailing the update (e.g., `## 2026-07-04 | Ingest: Added event-driven architecture pattern`).

### Lint Workflow
Ensure the vault stays healthy. When a lint pass is requested:
1.  **Schema Integrity**: Search for files missing required frontmatter (e.g., `type`).
2.  **Broken Links**: Check for any `[[links]]` that point to non-existent files.
3.  **Orphan Check**: Find files that are not linked to by any other page.
4.  **Coverage Gaps**: Look for concepts mentioned in headers or text that don't have their own page yet.
5.  **Produce Report**: Generate a markdown report and offer to clean up any automatic fixes.
