# Project 4: Skill Portability (Claude Code CLI Integration)

## Overview
This project demonstrates the **portability** of Claude Skills as an open standard. A skill authored in Claude.ai (the web interface) can travel directly into **Claude Code** (the developer CLI) simply by placing its `SKILL.md` inside the repository's `.claude/skills/` directory.

---

## Core Concept: Skills as Open Assets
- **Not Locked to One Interface**: A skill is not trapped in a web browser or a single chat session. It is a portable Markdown file with YAML frontmatter.
- **Portability Across Surfaces**:
  - **Claude.ai** (Web browser interface)
  - **Cowork** (Collaborative environments)
  - **Claude Code** (Developer command-line tool)
- **Zero Modification**: The exact same `SKILL.md` created in Project 1 runs in Claude Code without changing a single word.

---

## Directory Structure
```text
project-04/
├── .claude/
│   └── skills/
│       └── weekly-study-notes/
│           └── SKILL.md                 # Identical skill definition from Project 1
├── inputs/
│   └── raw_llm_notes.txt                # Lecture notes on LLMs
├── outputs/
│   └── study-notes-llms.md              # Formatted notes generated in Claude Code CLI
└── README.md                            # Documentation & walkthrough
```

---

## Step-by-Step Implementation Guide

### 1. Place the Skill in the Local Workspace
In your terminal or repository, ensure the directory structure exists:
```bash
mkdir -p .claude/skills/weekly-study-notes
```
Copy `SKILL.md` into that directory. Claude Code automatically scans `.claude/skills/` when launched in the workspace.

### 2. Launch Claude Code CLI
From your terminal inside the project folder:
```bash
claude
```

### 3. Execution Prompt
Provide your raw lecture notes along with a trigger instruction:

```text
Use this skill to make study notes from:
This week we studied Large Language Models (LLMs).
An LLM is an AI model trained on large amounts of text to understand and generate human-like language.
We learned about tokens. Text is broken into smaller pieces called tokens, and models process these tokens rather than entire sentences at once.
We also discussed prompting. A good prompt clearly describes the task, provides useful context, and specifies the desired output.
Finally, we learned that LLMs can sometimes hallucinate, meaning they may generate information that sounds correct but is actually false. Important information should therefore be verified.
```

### 4. Result
Claude Code reads the local `.claude/skills/weekly-study-notes/SKILL.md` definition, parses the raw notes, and outputs [`outputs/study-notes-llms.md`](outputs/study-notes-llms.md):
- Structured headings:
  - `## Large Language Models (LLMs)`
  - `## Tokens and Text Processing`
  - `## Prompting`
  - `## Hallucinations`
- Concise bold key-terms lists under each section.
- Exactly 3 conceptual review questions at the bottom.

---

## Key Win
> **"I handed my skill to a friend and it just worked, without me in the room. The recipe you wrote in one kitchen cooks seamlessly in another."**
