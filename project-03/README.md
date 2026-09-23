# Project 3: Compound Workflow (Drive Connector + Custom Skill)

## Overview
This project combines the power of **Project 1** (Custom Skill) and **Project 2** (Cloud Connector) into a single unified compound workflow. With the `weekly-study-notes` skill on your shelf and Google Drive connected, your entire weekly study summary ritual is triggered with a single natural sentence.

---

## The Compounding Pipeline
```text
┌─────────────────────────┐       ┌─────────────────────────┐       ┌─────────────────────────┐
│      Google Drive       │  ──>  │   weekly-study-notes    │  ──>  │    Structured Output    │
│  (Fetches live files)   │       │ (Applies custom format) │       │ (Exam-ready Markdown)   │
└─────────────────────────┘       └─────────────────────────┘       └─────────────────────────┘
```

1. **The Connector** fetches live data from your personal cloud account.
2. **The Skill** shapes the raw data according to your strict personal standards.
3. **The User** simply reviews the final artifact without copying, pasting, or re-explaining rules.

---

## Directory Structure
```text
project-03/
├── .claude/
│   └── skills/
│       └── weekly-study-notes/
│           └── SKILL.md                 # The skill formatting definition
├── inputs/
│   └── drive_source_notes.md            # The source document located in Google Drive
├── outputs/
│   └── study-notes-ai-agents-week2.md   # Final formatted output
└── README.md                            # Complete guide & documentation
```

---

## Step-by-Step Implementation Guide

### 1. Prerequisites
- **Google Drive Connector**: Authorized with read-only permissions (from Project 2).
- **Weekly Study-Notes Skill**: Installed in your Claude profile under **Customize → Skills** or in `.claude/skills/weekly-study-notes/` (from Project 1).

### 2. Setup Source File
Place your lecture notes or source notes document (e.g. `drive_source_notes.md` or `study-notes-ai-agents.md`) inside your Google Drive.

### 3. Execution Prompt
In a new chat, send the following prompt:

```text
Find this week's class notes in my Drive and make study notes from them.
```

### 4. What Happens Automatically
1. **Drive Discovery**: Claude queries Google Drive for files matching "class notes" or the most recent study document.
2. **Automatic Skill Resolution**: Detecting the phrase "make study notes", Claude invokes the `weekly-study-notes` skill without any explicit slash command or instructions.
3. **Structured Transformation**:
   - Organizes content into discrete sections:
     - `## From Generative AI to Agentic AI`
     - `## Core Architecture: The Perceive-Reason-Act Cycle`
     - `## Multi-Agent Systems (MAS)`
     - `## Ethical & Safety Guardrails`
   - Formats a dedicated `**Key terms:**` line per topic.
   - Generates exactly three high-level synthesis questions under `## Review Questions`.

### 5. Verification Checklist
- [x] Did Claude pull live data without manual copy-paste?
- [x] Did the skill fire automatically from natural phrasing?
- [x] Does the output match the strict format: 1 heading per topic, bold key-terms, exactly 3 review questions?

---

## Key Win
> **"I taught AI my monthly report once and pointed it at my files; now the whole thing runs from one sentence and I just review it."**
