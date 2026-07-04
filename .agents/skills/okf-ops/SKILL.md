---
name: okf-ops
description: Helps you ingest raw sources, query concepts, and run lint checks on the OKF Second Brain system.
---

# OKF Operations (okf-ops)

Use this skill when the user asks you to interact with, update, query, or run quality health checks (linting) on their Open Knowledge Format (OKF) Second Brain vault located in `Second Brain/`.

---

## 1. Ingestion Protocol (Interactive / Chat-Based)

When the user pastes raw notes, articles, transcripts, or brain-dumps:

1.  **Read and Analyze**:
    *   Find the key concepts embedded in the source.
    *   Classify each concept into one of the namespaces: `personal/`, `professional/`, or `projects/`.
    *   Determine the correct `type` based on the namespace (see allowed types in `AGENTS.md`).

2.  **Locate Target File**:
    *   Convert the concept name into a lowercase, kebab-case filename (e.g., `event-driven-architecture.md`).
    *   Search the vault (`Second Brain/`) using `find_path` or `grep` to see if a file with this name or concept already exists.

3.  **Synthesize Content**:
    *   **New File**: Write a comprehensive, highly-structured Markdown file. Always prefer headers, lists, and tables. Avoid verbose prose.
    *   **Existing File**: Merge the new information into the existing file. Do not discard existing information. Update the `timestamp` field in frontmatter to the current datetime.
    *   **Citations**: If the ingestion has a clear external source (e.g., a URL or book), include a `# Citations` section at the bottom of the file.

4.  **Perform Double-Bracket Linking**:
    *   Link concepts together using standard Obsidian wikilinks: `[[namespace/subdirectory/file-name|Display Name]]`.
    *   Always verify if concepts mentioned in the text already exist in the vault, and turn them into active links.

5.  **Log the Activity**:
    *   Open `Second Brain/log.md` (create it if missing).
    *   Append a new entry under the current date section using the following structure:
        ```markdown
        ## YYYY-MM-DD
        * **Ingest**: Updated / Created [[namespace/path/to/concept|Concept Title]] - Brief description of changes.
        ```

6.  **Maintain the Index**:
    *   Open `Second Brain/index.md` (create it if missing).
    *   Ensure the concept is represented under its category or namespace section.

---

## 2. Ingesting a Sample (How to write the files)

When writing a new concept file, use this exact template:

```markdown
---
type: Concept Type
title: Human Readable Title
description: A clear one-line description.
resource: https://optional-external-source.com
tags: [tag1, tag2]
timestamp: YYYY-MM-DDTHH:MM:SSZ
---

# Concept Title

[Brief introductory paragraph summarizing the concept.]

## Core Details

*   **Key Detail 1**: Detail description.
*   **Key Detail 2**: Detail description.

## Practical Examples / Applications

```javascript
// If code is relevant, add high-quality code blocks
```

## Related Concepts

*   [[other-concept-id|Related Concept Title]]

# Citations

[1] [Source Name](https://optional-external-source.com)
```

---

## 3. Linting and Health Check Protocol

When the user asks you to "lint" or "run a health check" on the Second Brain, execute these checks:

1.  **Frontmatter Validation**:
    *   Verify that every `.md` file (excluding `index.md` and `log.md`) starts with `---` YAML frontmatter.
    *   Check that each frontmatter block contains a `type` matching the permitted schema types listed in `AGENTS.md`.

2.  **Broken Wiki-link Check**:
    *   Scan all Markdown files for double-bracket links `[[some-path]]`.
    *   Verify that the target file actually exists in the workspace. Mark any missing targets as broken links.

3.  **Orphan Check**:
    *   Analyze the reference graph. Identify any concept file that has zero incoming double-bracket links from any other files.

4.  **Coverage Gaps**:
    *   Find un-linked keywords in text that match existing file titles, or locate terms in headers that are clearly important concepts but do not have a corresponding file yet.

5.  **Generate Lint Report**:
    *   Provide the user with a clean markdown report showing:
        *   🟢 No issues, or 🟡 Warnings / 🔴 Errors.
        *   List of broken links.
        *   List of orphan files.
        *   List of missing/incorrect frontmatter.
    *   Offer to automatically fix errors (like correcting timestamps or auto-creating stub files for broken links).
